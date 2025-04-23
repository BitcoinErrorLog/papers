# Black Market Money – *A Pedagogical Rewrite of Voskuil’s “Cryptoeconomics”*

[TOC]

---

### Table of Contents

| Part&nbsp;/ Chapter | Title | One-Sentence Summary |
|---|---|---|
| **Author’s Introduction** | *Why This Rewrite?* – John Carvalho | Explains the aim of turning Voskuil’s dense essays into a stepped learning path and adds Carvalho’s own lenses of **real control** and layer-centric scaling. |
| **Part I – Foundations** |
| 1 | **The Monetary Dilemma: State Money vs Black-Market Money** | Shows how seigniorage and censorship make state currencies adversarial, motivating Bitcoin’s permissionless design. |
| 2 | **What Is Bitcoin? A Money Secured by Principles** | Defines Bitcoin through risk-sharing, energy sinking, and permissionlessness—distinguishing it from “blockchain tech.” |
| 3 | **Scarcity & Value – Re-examining the Inflation Principle** | Debunks “21 million guarantees price” and links purchasing power to demand and fee-driven stability. |
| 4 | **Security Without Trust – Decentralisation & the Risk-Sharing Principle** | Details how full nodes, miners, and self-custody distribute attack surface and keep the system sovereign. |
| 5 | **Real Control – Why Self-Custody Defines Ownership** | Introduces Carvalho’s burn-test criterion for true ownership and warns against custodial regressions. |
| **Part II – Dynamics of the Bitcoin Economy** |
| 6 | **The Fee-Market Flywheel – From Utility Threshold to Stability** | Explains why block-space auctions fund security, cap low-value spam, and stabilise demand. |
| 7 | **One Money or Many? – Consolidation vs Substitution** | Weighs exchange-cost gravity toward one coin against fee-driven migration to cheaper substitutes. |
| 8 | **Scaling Bitcoin – Layers vs “Many Bitcoins”** | Pits Voskuil’s forecast of parallel chains against Carvalho’s case for a single, layer-anchored Bitcoin ‘sweet spot.’ |
| **Part III – Synthesis** |
| 9 | **Putting It All Together – A Cohesive Bitcoin Mental Model** | Integrates the prior concepts into a practical rubric for evaluating future proposals and teaching newcomers. |
| **Glossary** | — | Concise definitions of core terms (risk-sharing, utility threshold, sweet-spot scaling, etc.) for quick reference. |
| **References** | — | Categorised list of all relevant links. |

---

## Author’s Introduction <a name="intro"></a>

I’ve spent the last decade building, breaking, and defending Bitcoin tools—first as a curious node-runner, later as CEO of Synonym, and always as that loud guy on Twitter poking holes in half-baked narratives. In that time one book has stood apart as a genuine attempt to model *how* Bitcoin actually works, economically and technically: **Eric Voskuil’s *Cryptoeconomics*** [^voskuil].

Eric didn’t write a beach read; he wrote a dense constellation of essays. Each gem is rigorous, but newcomers often bounce off the asteroid field long before they reach the core. This project—**Black Market Money**—is my effort to turn those scattered insights into a single navigable map.

### What stays

* **Rational economics** – Eric’s method never hand-waves; every claim reduces to incentives and human action.  
* **Core principles** – [**Risk-Sharing**](#glossary "Security grows as more independent actors validate, mine, and self-custody—spreading attack surface."), [**Energy Sinking**](#glossary "Proof-of-work’s requirement that miners burn external resources, attaching real cost to reversal of history."), permissionlessness, utility thresholds—the pillars remain intact.  
* **Fallacy hunting** – The original book’s best moments expose cherished memes as sloppy thinking; we keep that spirit of myth-busting.

### What changes

* **Narrative thread** – Instead of standalone essays, chapters now build from first principles to advanced debates, so readers can climb step-wise rather than teleport.  
* **Pedagogical tone** – Academic, yes, but in the sense of a good seminar: clear definitions, worked examples, and constant reality-checks.  
* **My own lenses** – I introduce two recurring motifs: [**Real Control**](#glossary "Ownership criterion: the holder can spend or irreversibly destroy the asset without third-party approval.") and a **sweet-spot approach to scaling** that challenges Eric’s “many Bitcoins” forecast.

### Who this is for

* **Educators** – Curriculum builders at any program or university course brave enough for honest monetary theory.  
* **Bitcoin podcasters & their audiences** – People who already *care*, but want tighter arguments than “number go up.”  
* **Builders & policy wonks** – Engineers, lawyers, and regulators who need a rigorous map before they redraw the territory.

### How to read it

1. **Start at Part I** even if you mine blocks for breakfast. The terminology is sharpened and will save us both headaches later.  
2. **Argue margin-notes** – disagreeing is the whole point; use the rubric in Chapter 9 to stress-test new ideas.  
3. **Teach someone else** when you’re done. Bitcoin’s security budget ultimately rests on informed humans who choose self-custody and pay honest fees.

Bitcoin began as [**Black-Market Money**](#glossary "A currency designed to work where it is not allowed—permissionless, censorship-resistant, and non-custodial.")—digital cash that works even where it’s *not allowed* to. If this book does its job, you’ll finish with the mental model to keep it that way, and the vocabulary to explain *why* it matters to anyone who’ll listen.

— **John Carvalho**  
Lisbon, 2025

---

# Part I – Foundations

## Chapter 1 — The Monetary Dilemma: State Money vs Black‑Market Money

> “The value of Bitcoin over its alternatives derives directly from removing the state from control over both monetary supply and transaction censorship.” — Voskuil[^voskuil]

### 1 · Why Money Becomes a State Target

1. **Seigniorage — the silent tax**  
   A central bank can create new units at near‑zero cost and acquire real resources; that margin is [**seigniorage**](#glossary "Profit a money issuer earns by creating new units below market value; eliminated in Bitcoin by the fixed cap.") [^seigniorage].  
2. **Censorship & surveillance**  
   Monopoly payment rails let the state freeze or reverse transfers and mine personal data for taxation or social control [^sovereignty].  
3. **Reserve‑currency politics**  
   States hoard “hard” assets while issuing softer domestic notes, maximising hidden‑inflation latitude [^reserve].

These incentives make any currency that resists dilution and censorship an existential threat to the modern fiscal state.

### 2 · State Solutions: From Gold Standard to “Fedcoin”

| Era | Technique | Outcome |
|-----|-----------|---------|
| Classical gold standard | Redeemable notes 100 % backed by gold | Crises suspend redemption → fiat takeover [^eo6102] |
| Fiat & central banking | Unlimited note issue & lender‑of‑last‑resort credit | Structural inflation and system‑wide surveillance [^imf] |
| “Fedcoin” / CBDC | State‑branded crypto with whitelist & inflation lever | Seigniorage preserved under digital veneer [^fedwire] |

Every reform ultimately re‑secures the same two powers: to **inflate** and to **approve or deny** transfers.

### 3 · Bitcoin’s Counter‑Design — Black‑Market Money

* **Fixed supply** removes seigniorage.
* **Permissionless settlement** via the [**Risk‑Sharing Principle**](#glossary "Security grows as more independent actors validate, mine, and self‑custody—spreading attack surface.") denies censorship.
* **Self‑custody** yields [**Real Control**](#glossary "Ownership criterion: the holder can spend or irreversibly destroy the asset without third‑party approval.").

Any attempt to “whitelist” Bitcoin violates the [**Axiom of Resistance**](#glossary "Foundational assumption that a money can, in practice, operate despite state hostility; without it Bitcoin’s security model is incoherent.") and breaks its security model.

---

## Glossary <a name="glossary"></a>

*(excerpt – full glossary appears at end of book)*

| Term | Brief definition |
|------|------------------|
| **Risk‑Sharing Principle** | Security grows as more independent actors validate, mine, and self‑custody—spreading attack surface. |
| **Real Control** | Ownership criterion: the holder can spend or irreversibly destroy the asset without third‑party approval. |
| **Axiom of Resistance** | Assumption a money can operate despite state hostility; basis of Bitcoin’s design. |
| **Black‑market money** | Currency that works where it is not allowed—permissionless, censorship‑resistant, non‑custodial. |
| **Seigniorage** | Profit from issuing money below market value. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^voskuil | Voskuil, Eric. *Cryptoeconomics: Fundamental Principles of Bitcoin* (2020). | — (PDF) |
| ^seigniorage | “Seigniorage.” Wikipedia. | https://en.wikipedia.org/wiki/Seigniorage |
| ^sovereignty | “Sovereignty.” Wikipedia. | https://en.wikipedia.org/wiki/Sovereignty |
| ^reserve | “Reserve currency.” Wikipedia. | https://en.wikipedia.org/wiki/Reserve_currency |
| ^eo6102 | Executive Order 6102 (US gold seizure). | https://en.wikipedia.org/wiki/Executive_Order_6102 |
| ^imf | International Monetary Fund. | https://www.imf.org |
| ^fedwire | “Fedwire.” Wikipedia. | https://en.wikipedia.org/wiki/Fedwire |

