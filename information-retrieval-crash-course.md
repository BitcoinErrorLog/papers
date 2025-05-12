### Chapter 1 – Instant Inverted Index

**Purpose**  Build a bare‑bones search service that ingests Pubky posts, produces an [inverted index](https://en.wikipedia.org/wiki/Inverted_index), and returns top‑k hits in <50 ms.

**Why it matters**  Every later stage—[BM25](https://en.wikipedia.org/wiki/Okapi_BM25) tuning, [embeddings](https://en.wikipedia.org/wiki/Word_embedding), and graph reranking ([learning to rank](https://en.wikipedia.org/wiki/Learning_to_rank))—rests on a solid lexical index. Master this and you control the basic plumbing of Pubky Search.

---

\#### 1. Concepts you must own — in 30 min

* **[Tokenisation](https://en.wikipedia.org/wiki/Lexical_analysis#Tokenization)** – splitting post bodies, titles and `tags[]` into lower‑cased terms.
* **[Stop‑word removal](https://en.wikipedia.org/wiki/Stop_words)** – filter high‑frequency noise (e.g. “the”, “and”).
* **[Posting list](https://en.wikipedia.org/wiki/Inverted_index#Postings_lists)** – map `term → [(docID, tf),…]`.
* **Top‑k retrieval** – intersect posting lists, rank by term‑frequency, return first k.

---

\#### 2. Pubky specifics

* **Post source** – stream JSON posts from your homeserver’s `/posts?since=` endpoint.
* **DocID scheme** – use `<pubkey>:<postHash>`.
* **Tags are terms** – treat each signed tag as a high‑weight term; you will boost them later.

---

\#### 3. Lab #1 – Ship a working index

1. **Fetch corpus**  `npx pubky-cli fetch --limit 10000 > corpus.json`
2. **Build index**  Node/TypeScript:

   ```ts
   for (const post of corpus) {
     for (const term of tokenize(post.body + ' ' + post.tags.join(' '))) {
       addToInverted(term, post.id);
     }
   }
   ```
3. **Serve search**  Fastify route `GET /search?q=` parses query → intersects lists → responds JSON.
4. **Benchmark**  Aim for P50 latency <50 ms, memory <300 MB @ 10 k docs.

---

\#### 4. Deliverable checklist

* `index.ts`, `server.ts`, `README.md` with run instructions.
* Demo: `curl "localhost:3000/search?q=bitcoin+tag:lightning"` returns IDs and snippet.

---

\#### 5. Quick look‑ups

| Term               | One‑line definition              |
| ------------------ | -------------------------------- |
| **Inverted index** | Hash‑map from term → docIDs      |
| **Posting list**   | The array `[docID, tf]` per term |
| **Stop‑word**      | Super‑common term you drop       |

### Chapter 2 – Smart Weighting

**Purpose**  Replace raw term‑frequency scoring with BM25 tuned for Pubky’s short, tag‑rich posts, boosting retrieval precision without extra latency.

**Prerequisite**  Running inverted‑index service from Chapter 1.

---

#### 1. Concepts you need today

* **[TF](https://en.wikipedia.org/wiki/Term_frequency), [DF](https://en.wikipedia.org/wiki/Inverted_index#Document_frequency), [IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf#Inverse_document_frequency)** – recap the three signals behind BM25.
* **BM25 hyper‑parameters** – `k1` controls term‑frequency saturation; `b` controls length normalisation.
* **Document length distribution** – Pubky posts average 140 chars; set `b≈0.25` to avoid over‑penalising short notes.

#### 2. Pubky‑specific insights

* Tags appear as first‑class strings—index them **twice** (field‑boost) so tag matches outrank body matches.
* Use Pubky SDK stream to collect average post length each night; auto‑adjust `avgdl`.

#### 3. Lab – Tune and benchmark

1. Integrate BM25 into `rank.ts`.
2. Grid‑search `k1 ∈ {0.9, 1.1, 1.3}` and `b ∈ {0.15, 0.25, 0.35}` on a 500‑query test set curated from Pubky App beta logs.
3. Compute **[P@10](https://en.wikipedia.org/wiki/Information_retrieval#Evaluation_metrics)** and **[nDCG](https://en.wikipedia.org/wiki/DCG)**; choose best.
4. Commit param file `bm25.json` for later stages.

#### 4. Success criteria

* ≥ +8 % P\@10 vs. Chapter 1 baseline.
* 95‑th percentile latency still <60 ms.

---

**Take‑home**  Congratulations—you now have an industrial‑strength lexical ranker ready for semantic add‑ons.

### Chapter 3 – Semantic Embeddings at Production Speed

**Purpose**  Catch lexical misses by embedding content & queries into a shared vector space and retrieving via an [approximate‑nearest‑neighbour (ANN)](https://en.wikipedia.org/wiki/Nearest_neighbor_search#Approximate_nearest_neighbor_%28ANN%29_search) index.

**Builds on**  BM25‑backed search API from Chapter 2.

---

#### 1. Key take‑aways

* **[Sentence‑BERT](https://www.sbert.net/) / [MiniLM](https://huggingface.co/transformers/model_doc/minilm.html)** – ready‑to‑use models that fit in <100 MB and return 384‑dim vectors.
* **ANN search ([HNSW](https://en.wikipedia.org/wiki/Hierarchical_navigable_small_world_graph))** – small‑world graph structure delivering sub‑100 ms recalls at million‑scale.
* **Hybrid search pattern** – lexical first; if max BM25 < τ, fall back to semantic results.

---

#### 2. Pubky deployment specifics

* Store the 384‑vec for each post alongside its inverted‑index entry.
* Tags are concatenated to body text before embedding to preserve user intent.
* Persist vectors in **[Faiss](https://github.com/facebookresearch/faiss)** on disk; load at start‑up.

---

#### 3. Hands‑on lab steps

1. **Fine‑tune** MiniLM on a 50 k post–tag parallel corpus (optional but yields +12 % recall).
2. Embed all posts: `embedder.encode([title + " " + tags + " " + body])` → `vectors.bin`.
3. Build HNSW: `faiss.IndexHNSWFlat(d=384, M=32)`; add vectors.
4. Modify `/search` endpoint:

   * Compute BM25; if top score ≥ τ (default 2.0) serve lexical ranking.
   * Else embed query and fetch 100 nearest neighbours; merge results with BM25 list, dedup.
5. Measure latency and recall vs. Chapter 2 baseline.

---

#### 4. Success criteria

* <150 ms p95 latency for hybrid path
* ≥20 % relative recall gain on manual relevance judgements.


### Chapter 4 – Graph‑Aware Reranking

**Purpose**  Leverage Pubky’s Semantic Social Graph to rerank search results by trust and social proximity, turning a good lexical/semantic match into a great personalised hit list.

**Builds on**  Hybrid lexical + semantic engine from Chapter 3.

---

#### 1. Core ideas

* **Tripartite graph** – users ↔ tags ↔ posts citeturn2file3.
* **Trust propagation** – compute a [PageRank](https://en.wikipedia.org/wiki/PageRank)-style centrality score, seeded by the searcher’s Web‑of‑Trust (WoT) peers.
* **Edge weighting** – strength derives from signature trust + tag relevance.

#### 2. Minimal theory (15 min)

1. Random walks on graphs converge to a stationary distribution proportional to node centrality.
2. PageRank with a personalised restart vector becomes **TrustRank**—higher weight for edges originating from trusted users, damped by α ≈ 0.85.
3. Reranking rule: `score_final = score_lexsem × (1 + λ × trust_rank)` where λ is tuned on click‑through.

#### 3. Hands‑on lab

1. **Export graph** – From your Chapter 3 index, emit `(user_id, tag, post_id, weight)` triples in GraphML.
2. **Compute TrustRank** – Run power‑iteration or GraphX with a personalised seed vector.
3. **Plug into reranker** – Multiply BM25/embedding score by trust factor; compare P\@10 lift on held‑out queries.

#### 4. What to ship

* `trust_rank.py` – script that ingests GraphML, outputs numpy array of trust scores.
* Modified search microservice that injects trust scores during ranking stage.
* A quick dashboard showing before/after metrics (precision, click‑through).

---

**You now have personalised, trust‑boosted search that outperforms lexical+semantic alone.**

Next up: harness Pubky’s signed tags for even deeper relevance signals.

### Chapter 5 – Signed Social Tags as Ranking Signals

**Purpose**  Exploit cryptographically signed tags as first‑class IR features for discovery, recommendation, moderation, and personalised ranking.

**Builds on**  Graph trust scores and reranker from Chapter 4.

---

#### 1. Must‑know primitives (new since previous chapters)

* **Tag namespace & scope** – tags are relative to the signer and context citeturn2file4.
* **Signature payload** – public‑key, tag, target, timestamp (enables cryptographic provenance).
* **[Co‑occurrence matrix](https://en.wikipedia.org/wiki/Co-occurrence)** – counts how often two tags appear together across posts; foundation for measuring association strength.
* **[Folksonomy](https://en.wikipedia.org/wiki/Folksonomy)** – a user‑generated tagging system rather than a controlled taxonomy.
* **[Controlled vocabulary](https://en.wikipedia.org/wiki/Controlled_vocabulary)** – a curated set of allowed terms; contrasts with free‑form folksonomy and helps disambiguate tags.
* **[Cold‑start problem](https://en.wikipedia.org/wiki/Cold_start_problem)** – difficulty recommending or ranking items that have few interactions or tags.
* **[Pointwise Mutual Information (PMI)](https://en.wikipedia.org/wiki/Pointwise_mutual_information)** – statistic for measuring association between two discrete events; used to weight tag pairs.

---

#### 2. What to implement

1. **Signed‑Tag Ingest** – extend your ingest worker to parse `sig`, `tag`, `target`, `pubkey`, `ts` fields and persist them in a `tags` table keyed by `(tag, target)`.
2. **Tag Co‑occurrence Job** – daily Spark / DuckDB job that outputs a tag×tag PMI matrix for later query expansion (used in Chapter 7).
3. **Tag‑Aware Scoring** – during ranking, add a bonus weight when a post contains a tag issued by a user inside the searcher’s Web‑of‑Trust.
4. **Tag Recommendation Endpoint** – `GET /tags/suggest?u=<pubkey>&k=10` returns k candidate tags based on co‑occurrence + trust weights.

---

#### 3. Lab

> **Goal:** Ship a tag recommender that suggests five new tags to any Pubky user based on their historical tagging behaviour and co‑signers.

*Step A*  Run the co‑occurrence job on a 1‑week post dump.
*Step B*  Compute PMI scores and keep the top 1 000 tag pairs.
*Step C*  For a test user, merge their personal tag history with PMI‑suggested tags; boost suggestions from signers within two hops of their trust graph.
*Step D*  Evaluate coverage and precision offline; aim for >40 % acceptance rate in a simulated "accept/reject" user study.

---

#### 4. Quick checklist

* &#x20;Parse and verify tag signatures (Ed25519).
* Materialise tag co-occurrence & PMI.
* Integrate trust-weighted bonus into your BM25 score.
* Expose /tags/suggest API.\\

  Complete these steps and you’ll feed richer, high-precision tag signals into the ranking pipeline you already have.

### Chapter 6 – Distributed Indexing with Nexus

**Purpose**  Shard and replicate your search index across Nexus nodes, announced and discovered through PKARR on the Mainline DHT, so Pubky Search keeps working when a single box—or an entire data‑centre—drops offline.

**Builds on**  Local index pipeline from Chapters 1‑5.

---

#### 1. Concepts in one sitting

* **[Distributed hash table (DHT)](https://en.wikipedia.org/wiki/Distributed_hash_table)** – key→value overlay network enabling lookups without a central registry.
* **Mainline DHT & PKARR** – Pubky’s flavour of Mainline; PKARR stores a "resource record" that maps a logical shard‑ID to `multiaddr`s where it lives citeturn2file7.
* **Shard key** – result of hashing `postID` (or a tag, depending on index) and applying **[consistent hashing](https://en.wikipedia.org/wiki/Consistent_hashing)** to divvy the space evenly.
* **Replica factor** – how many nodes store the same shard; drives durability and read availability. See **[replication factor](https://en.wikipedia.org/wiki/Replication_%28computing%29)**.
* **[CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem)** – why perfect consistency, availability, and partition tolerance can’t all be guaranteed at once.
* **[Gossip protocol](https://en.wikipedia.org/wiki/Gossip_protocol)** – how Nexus nodes share routing tables and freshness metadata.

---

#### 2. Architecture snapshot

```
 client ➜ gateway ➜ query‑router ┐
                         shard‑A 🗂️  ──┐
                         shard‑B 🗂️  ──┼─▶ BM25 + embedding + graph rerank
                         shard‑C 🗂️  ──┘
                 (each shard served by ≥ replica‑factor nodes)

 shards announce  ➜ Mainline DHT/PKARR ➜ discovery cache in gateway
```

*The gateway keeps a 30 s cache of shard‑ID → node addresses to avoid DHT round‑trips per query.*

---

#### 3. Lab – Spin up your first Nexus swarm

1. **Bootstrap two nodes** on different ports; run the `nexus-indexer` container with env `REPLICA_FACTOR=2`.
2. **Shard the index** produced in Chapter 5 with consistent hashing (e.g. 64 shards).
3. **Announce** each shard‑ID via PKARR (`nexus announce --shard 17 --multiaddr /ip4/…`).
4. **Query router**: modify your Chapter‑3 search API so it can resolve a shard‑ID ➜ node list via PKARR, pick the fastest replica (basic RTT probe) and failover after 150 ms.
5. **Chaos test**: kill one node; confirm queries still succeed (albeit a little slower) via the surviving replica.

Expected outcome: latency budget rises only \~30 ms due to network hop + cache miss; uptime ≥ 99.9 % under one‑node failure.

---

#### 4. Quick checklist

* Pick a shard count (power of two) and seed the consistent-hashing ring.
* Set REPLICA\_FACTOR ≥ 2; monitor disk-usage growth.
* Enable shard-freshness gossip every 60 s.
* Add retry/back-off logic in the router before surfacing 5XX to the client.
* Record per-shard QPS, tail latency, and error rate in Prometheus.

  Complete these bullets and your index can now survive node churn and geographic splits without users noticing a thing.

### Chapter 7 – Contextual Query Expansion

**Purpose**  Recover otherwise‑missed results when lexical + semantic matches fail by automatically expanding the user’s query with contextually relevant tags, synonyms, and entities drawn from their Web‑of‑Trust.

**Builds on**  Graph analytics (Chapter 4), signed‑tag signals (Chapter 5), and the distributed Nexus index (Chapter 6).

---

#### 1. Fast‑track theory (new concepts only)

* **Local synonym table** – offline map from tag ↔ term co‑occurrences in the Pubky corpus (PMI ≥ 1.5).
* **[Pseudo‑relevance feedback](https://en.wikipedia.org/wiki/Pseudo-relevance_feedback)** – assume top‑k initial results are relevant; mine expansion terms from them.
* **[Rocchio algorithm](https://en.wikipedia.org/wiki/Rocchio_algorithm)** – classic vector‑space method to re‑weight query vectors after feedback.
* **[Query‑likelihood model](https://en.wikipedia.org/wiki/Language_model_for_information_retrieval)** – probabilistic approach that scores docs by the likelihood they would generate the query; useful baseline for comparing expansion gains.

---

#### 2. Practical algorithm (5‑step loop)

1. **Initial pass** → run existing lexical + semantic search; collect top k=20.
2. **Candidate terms** → extract high‑PMI tags & nouns from those 20 docs.
3. **Filter by trust** → keep terms seen in content tagged by peers within the asker’s WoT radius ≤ 2 hops.
4. **Rocchio re‑weight** → α=1.0 original query, β=0.75 feedback vector.
5. **Re‑issue query** → merge results, dedupe, rerank via trust‑weighted scorer.

Latency budget: <30 ms extra; cache expansion terms per user × hour.

---

#### 3. Lab – Build & benchmark expansion

* **Dataset**  Use 10 k Pubky posts with ground‑truth relevance judgements.
* **Task**  Compare MRR and nDCG\@10 for baseline vs. expanded queries.
* **Goal**  ≥ 10 % MRR uplift without >5 % latency hit.

*Code stub*: `expander.py` that wraps your Chapter 6 router; flag `--expand` toggles logic.

---

#### 4. Quick checklist

* Generate synonym table nightly; store in Redis (< 50 MB).
* Implement pseudo-relevance feedback path behind feature flag.
* Tune Rocchio (α, β) on validation set.
* Expose /search?expand=1 for A/B testing.
* Log added terms & latency to Prometheus.


  Knock out these tasks and you’ll surface long‑tail content that BM25 + embeddings alone would miss—without overwhelming your latency budget.

### Chapter 8 – Full Pipeline & A/B Test

**Purpose**  Orchestrate ingest → index → rank → rerank → serve under a 300 ms budget—and prove the uplift with a statistically solid online experiment.

**Builds on**  Everything you shipped in Chapters 1‑7.

---

#### 1. Integration blueprint

| Stage               | Tech / Responsibility                                                                                                            |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **Ingest workers**  | Stream posts & tags from Pubky homeservers into [Kafka](https://en.wikipedia.org/wiki/Apache_Kafka) or [NATS](https://nats.io/). |
| **Indexer service** | Update lexical index (BM25), embedding store, trust graph per shard.                                                             |
| **Query router**    | Fan‑out query to shards, combine lexical + semantic results, send to graph reranker.                                             |
| **API gateway**     | Front‑door [microservice](https://en.wikipedia.org/wiki/Microservices) that enforces auth, rate‑limits, and canary routing.      |
| **Result cache**    | 95‑percentile hits served from Redis/Memcached to shave 30 ms.                                                                   |

Target latency budget:
\* Ingest path ≤ 1 s from post to searchable.
\* 95‑pctl query latency ≤ 300 ms, 99‑pctl ≤ 500 ms.

---

#### 2. Metrics & observability

* **Query per second (QPS)**, **tail latency** (95 / 99 pctl).
* **[Click‑through rate (CTR)](https://en.wikipedia.org/wiki/Click-through_rate)** & **nDCG** from implicit feedback.
* **Error budget** = 1 – (successful queries ÷ total queries).
* Instrument with [Prometheus](https://prometheus.io/) + Grafana, send alerts to PagerDuty.

---

#### 3. Online experiment playbook

1. **Define hypothesis** – e.g. "Graph rerank increases CTR by ≥ 5 %."
2. **Bucket traffic** – 50 / 50 split via feature flag at API gateway.
3. **Run for exposure** – compute sample size with [p‑value](https://en.wikipedia.org/wiki/P-value) 0.05, power = 0.8.
4. **Analyse** – two‑tailed z‑test on CTR; monitor guard‑rail metrics (latency, errors).
5. **Roll‑out** – if significant, push to 100 % with a [canary release](https://en.wikipedia.org/wiki/Canary_release) window.

---

#### 4. Hands‑on lab

* Spin up `docker‑compose up` stack (Kafka/NATS, indexer, router, gateway).
* Replay a one‑day Pubky feed through ingest; verify document count parity.
* Launch `/search` A/B flags, run synthetic load (locust, k6) to reach 200 QPS.
* Capture metrics in Prometheus and plot CTR over time in Grafana.

---

#### 5. Quick checklist

* Ship Dockerfiles & \`docker-compose.yml\` for every service.
* Add Prometheus \`/metrics\` endpoint to each service.
* Set latency-budget alerts ( ≥ 300 ms p95 ) in Grafana.
* Implement feature-flag toggle and canary ramp-up script.
* Document rollback plan in the runbook.\\

  You now have a production‑grade, empirically‑verified Pubky Search pipeline ready for real‑world traffic.

### Glossary – Pubky‑Centric IR Terms

| Term                                                                                                                           | Plain‑English Definition                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| [Inverted Index](https://en.wikipedia.org/wiki/Inverted_index)                                                                 | Dictionary mapping each term to every post where it appears, plus positions. Foundation of lexical search. |
| [TF‑IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)                                                                         | Weight = (term frequency) × log(total docs / docs with term). First‑cut relevance score.                   |
| [BM25](https://en.wikipedia.org/wiki/Okapi_BM25) (`k1`, `b`)                                                                   | Pragmatic scoring that limits term‑frequency saturation (`k1`) and normalises for post length (`b`).       |
| [Sentence‑BERT](https://www.sbert.net/)                                                                                        | Transformer model that encodes a text snippet to a 384‑ or 768‑dim vector suitable for similarity search.  |
| [HNSW](https://en.wikipedia.org/wiki/Approximate_nearest_neighbor_search#Hierarchical_navigable_small_world_graphs_%28HNSW%29) | “Hierarchical Navigable Small‑World” graph; ANN structure for <100 ms nearest‑vector look‑ups.             |
| [Semantic Social Graph](https://pubky.org)                                                                  | Pubky’s tripartite graph of users ↔ tags ↔ posts, enriched with weighted trust edges.                      |
| [PageRank](https://en.wikipedia.org/wiki/PageRank) / [TrustRank](https://en.wikipedia.org/wiki/TrustRank)                      | Random‑walk based centrality score. In Pubky we seed walks from the searcher’s trust circle.               |
| [Signed Tag](https://github.com/synonym-dev/pubky)                                                                             | Cryptographically signed label attaching meaning (and trust weight) to a post, user, or file.              |
| [Co‑occurrence Matrix](https://en.wikipedia.org/wiki/Co-occurrence)                                                            | Table counting how often two tags appear together; informs recommendation & query expansion.               |
| [Mainline DHT](https://en.wikipedia.org/wiki/Mainline_DHT)                                                                     | Peer‑to‑peer hash table underlying PKARR; stores key→value pairs for discovery without servers.            |
| [PKARR](https://github.com/pubky/pkarr)                                                                                  | "DNS for keys" – maps a public key to resource records (homeserver URL, index shards, etc.).               |
| [Nexus Indexer](https://github.com/pubky/pubky-nexus)                                                                    | Pubky micro‑service that shards, replicates, and announces search indexes over PKARR.                      |
| [Latency Budget](https://sre.google/sre-book/monitoring-distributed-systems/#latency)                                          | Hard limit (300 ms) for serving a query; each pipeline stage gets a slice.                                 |
| [A/B Test](https://en.wikipedia.org/wiki/A/B_testing)                                                                          | Controlled experiment splitting traffic (e.g., 50/50) to measure CTR or dwell‑time lift.                   |
| [ANN](https://en.wikipedia.org/wiki/Nearest_neighbor_search#Approximate_nearest_neighbor_search)                               | Approximate Nearest Neighbour search; trades tiny accuracy loss for huge speed gains on vector search.     |
| [PMI](https://en.wikipedia.org/wiki/Pointwise_mutual_information)                                                              | Pointwise Mutual Information; measures strength of association between two tags or terms.                  |
| [Web‑of‑Trust](https://en.wikipedia.org/wiki/Web_of_trust)                                                                     | Directed, weighted graph of trust edges between pubkeys, maintained by tagging.                            |
| [Tag Namespace](https://en.wikipedia.org/wiki/Tag_%28metadata%29)                                                              | Logical domain for a tag (e.g., `topic:`, `trust:`), allowing collisions to coexist.                       |
| [Edge Weight](https://en.wikipedia.org/wiki/Graph_%28discrete_mathematics%29#Weighted_graph)                                   | Numeric strength on a graph edge; in Pubky often `trust` or `relevance` scores.                            |
| [Microservice](https://en.wikipedia.org/wiki/Microservices)                                                                    | Small, single‑purpose network process; how we deploy each stage of the IR pipeline.                        |
