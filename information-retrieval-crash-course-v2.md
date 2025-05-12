# Pubky‑Centric Information Retrieval Crash‑Course  
*A battle‑ready syllabus*

---

## Chapter 1 – Instant Inverted Index
**Purpose** Build a bare‑bones search service that ingests Pubky posts, produces an [inverted index](https://en.wikipedia.org/wiki/Inverted_index), and returns top‑k hits in < 50 ms.  
**Why it matters** Every later stage—[BM25](https://en.wikipedia.org/wiki/Okapi_BM25) tuning, [embeddings](https://en.wikipedia.org/wiki/Word_embedding), and graph re‑ranking—rests on solid lexical plumbing.

### Key concepts
* **Tokenisation**, **stop‑word removal**, **postings list**  
* **Incremental indexing** – merge new posts without nightly downtime  

### Lab
1. Consume the real‑time Pubky feed (`/stream/posts`) into SQLite.
2. Build an inverted index with on‑disk skip pointers.  
3. Serve `GET /search?q=` that returns top‑k doc IDs under 50 ms.

---

## Chapter 2 – Smart Weighting
**Purpose** Replace raw term‑frequency scoring with [BM25](https://en.wikipedia.org/wiki/Okapi_BM25) tuned for Pubky’s short, tag‑rich posts.

### New concepts
* **[TF](https://en.wikipedia.org/wiki/Term_frequency) / [DF](https://en.wikipedia.org/wiki/Inverted_index#Document_frequency) / [IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)**  
* **Average document length (`avgdl`)** – roll‑up nightly; don’t hard‑code.  
* Tag boost: don’t duplicate tags in the postings list—apply `score += λ_tag · tag_hit` at query time.

### Lab
* Tune `k1`, `b`, and `λ_tag` on a validation set; measure [P@10](https://en.wikipedia.org/wiki/Information_retrieval#Evaluation_metrics).

---

## Chapter 3 – Semantic Embeddings at Production Speed
**Purpose** Catch lexical misses with transformer embeddings and [approximate‑nearest‑neighbour (ANN)](https://en.wikipedia.org/wiki/Nearest_neighbor_search#Approximate_nearest_neighbor_(ANN)_search) search.

### New concepts
* **[Sentence‑BERT](https://www.sbert.net/)** / **[MiniLM](https://huggingface.co/transformers/model_doc/minilm.html)**  
* **HNSW** & **Faiss** ANN indices  
* Footnote: fine‑tuning MiniLM yields +12 % recall but costs days of GPU—safe to skip for MVP.

### Lab
* Embed post text + tags → 384‑dim vectors; index 1 M vectors (~1.5 GB).  
* Fallback to ANN results when BM25 < τ.

---

## Chapter 4 – Graph‑Aware Re‑ranking
**Purpose** Leverage Pubky’s Semantic Social Graph to amplify results from high‑trust peers.

### New concepts
* **[PageRank](https://en.wikipedia.org/wiki/PageRank)**‑style trust propagation  
* Trust radius parameter (`?radius=`) – default **2 hops**, configurable per query.

### Lab
* Export user↔tag↔post edges nightly (MsgPack, not GraphML).
* Compute trust scores; rerank `score_final = score_bm25 · (1 + α·trust)`.

---

## Chapter 5 – Tag Signals & Recommendation
*(formerly “Signed Tags” – signatures removed)*

**Purpose** Exploit tag metadata (namespace, scope, co‑occurrence) for discovery and recommendation.

### New concepts
* **Folksonomy** & controlled vocabulary  
* **Pointwise Mutual Information (PMI)** for tag co‑occurrence  
* **Cold‑start mitigation** with default tag suggestions

### Lab
* Nightly Spark job – build tag × tag PMI table.  
* `/tags/suggest` endpoint returns top‑n recommended tags for a post.

---

## Chapter 6 – Distributed Indexing with Nexus
**Purpose** Shard and replicate the index across Nexus nodes, discovered via PKARR on the Mainline [DHT](https://en.wikipedia.org/wiki/Distributed_hash_table).

### New concepts
* **Consistent hashing**, replication factor **RF = 3** (one per region)  
* Cold PKARR lookup can hit 200‑400 ms – prefetch on app‑launch.  
* **Gossip protocol** for shard freshness

### Lab
* Deploy three Nexus indexers; verify lookups survive a region outage.  
* Instrument Prometheus for QPS, p95 latency, error rate.

---

## Chapter 7 – Contextual Query Expansion
**Purpose** Improve recall by adding synonyms & co‑occurring tags drawn from the searcher’s Web‑of‑Trust.

### New concepts
* **[Pseudo‑relevance feedback](https://en.wikipedia.org/wiki/Information_retrieval#Relevance_feedback)** & **[Rocchio algorithm](https://en.wikipedia.org/wiki/Rocchio_algorithm)**  
* **Query‑likelihood model**

### Lab
* Nightly job builds synonym table.
* Feature flag `/search?expand=1`; A/B test recall vs. latency hit.

---

## Chapter 8 – Full Pipeline & A/B Test
**Purpose** Orchestrate ingest → index → rank → rerank → serve in < 300 ms and prove the uplift online.

| Stage | Tech |
|-------|------|
| Ingest | [Kafka](https://en.wikipedia.org/wiki/Apache_Kafka) (or [NATS](https://nats.io/)) |
| Index | BM25 + embeddings + trust scores |
| Router | Consistent hashing, shard fan‑out |
| API | FastAPI behind an edge [API gateway](https://en.wikipedia.org/wiki/API_management) |
| Observability | [Prometheus](https://prometheus.io/), [Grafana](https://grafana.com/) |

### Checklist
- Dockerise every service; provide `docker-compose.yml`.  
- Add `/metrics` endpoints; set alerts p95 ≥ 300 ms.  
- Canary release 5 % traffic; rollback plan in runbook.  
- Measure click‑through rate (CTR) to statistical significance (χ²).

---

## Appendix A – Operational Hardening

### Abuse‑resistance
* **Sybil / tag‑spam detection** – heuristic + proof‑of‑work quotas.  
* Rate‑limit tag events; homeserver ACLs.

### Privacy & encrypted content
* Index only headers for locked posts; decrypt after ACL check.

### Real‑time ops
* Support *incremental* posting‑list merges & `faiss.add_without_ids`.

### Compliance & takedown
* Include GDPR “delete document” flow; CSAM hash‑list scan.

### Observability for trust graph
* Metric: percent of edges from high‑trust keys; tag‑duplication entropy.

### Capacity notes
* Vector index ~1.5 GB per 1 M posts (384‑d float32).  
* Consider TTL pruning or mixed precision.

---

## Glossary (linked once per term)
| Term | Definition |
|------|------------|
| [Inverted Index](https://en.wikipedia.org/wiki/Inverted_index) | Term → list(postID). |
| [TF‑IDF](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) | Weighting scheme. |
| BM25 | See Chapter 2. |
| [Sentence‑BERT](https://www.sbert.net/) | Transformer embedder. |
| [HNSW](https://github.com/nmslib/hnswlib) | Graph‑based ANN structure. |
| [Faiss](https://github.com/facebookresearch/faiss) | Vector search library. |
| [PageRank](https://en.wikipedia.org/wiki/PageRank) | Graph centrality measure. |
| PMI | Pointwise Mutual Information (Chapter 5). |
| [DHT](https://en.wikipedia.org/wiki/Distributed_hash_table) | Peer‑to‑peer key‑value overlay. |
| Consistent hashing | Technique to assign shards. |
| [Kafka](https://en.wikipedia.org/wiki/Apache_Kafka) | Log‑based message broker. |
| [Prometheus](https://prometheus.io/) | Metrics / monitoring. |

