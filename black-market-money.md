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

# Part I – Foundations

## Chapter 2 — What Is Bitcoin? A Money Secured by Principles

### 2.1  Working definition

**Bitcoin is the set of principles that let any group of people define, issue, and transfer a fixed‑supply digital money without asking permission from a third party.** [^voskuil]

Because the name *Bitcoin* originally described those principles—not a ticker or trademark—any system that preserves them is “Bitcoin‑like,” while anything that drops a principle is not.

---

### 2.2  The three “cryptodynamic” forces [^voskuil]

| Force | Function | Take‑away |
|-------|----------|-----------|
| **Risk‑Sharing** | Many independent actors validate and spend the coin. | *Security is social:* each self‑custody user is a shield node. |
| **Energy Sinking** | Proof‑of‑work attaches real‑world cost to rewriting history. | “Waste” is the attack price‑tag. |
| **Power Regulating** | Fee market gives honest hash‑power a revenue edge over censors. | Attacks must outbid legitimate demand. |

Remove any one force—e.g., swap PoW for PoS—and the result is **not Bitcoin**.

---

### 2.3  Core traits that flow from those forces

1. **Fixed supply** – 21 million coins ever; erases [**seigniorage**](#glossary) incentives.  
2. **Permissionless access** – Anyone may run a node or mine; protocol assumes the [**Axiom of Resistance**](#glossary).  
3. **Censorship resistance** – Fees reward inclusion; excluding transactions sacrifices revenue.  
4. **Non‑custodial ownership (“Real Control”)** – Private keys, not institutions, guard coins; claims without keys are IOUs.

---

### 2.4  Where Bitcoin fits in the “money taxonomy”

| Class | Example | Supply control |
|-------|---------|----------------|
| Commodity | Gold | Market mining expands supply when price > cost |
| Monopoly fiat | USD | Central bank issues at will |
| **Fixed‑supply digital** | **Bitcoin** | No new units after genesis block |

Bitcoin sits in a novel third category—fiat in use‑value, but commodity‑like in issuance cost.

---

### 2.5  Why Bitcoin ≠ “a blockchain”

A blockchain is merely an append‑only log. Bitcoin’s value comes from **who** may append (any miner), **why** they cannot cheat (Energy Sinking), and **who** checks the rules (all full nodes). Recording custodian IOUs on a chain re‑introduces third‑party risk—the [**Blockchain Fallacy**](#glossary).

---

### 2.6  Mental model checkpoint

* **Technology ≠ security.** People following incentives *are* the security layer.  
* **Rules endure only while users self‑custody and verify.**  
* Every “inefficiency” (energy cost, capped throughput) is a trade‑off keeping the three forces in balance.

With that foundation we’re ready to explore why scarcity alone doesn’t guarantee value in Chapter 3.

---

## Glossary (excerpt)

| Term | Definition |
|------|------------|
| **Risk‑Sharing** | Security grows as more independent actors validate, mine, and self‑custody. |
| **Energy Sinking** | PoW burns external energy, tying cost to attack. |
| **Power Regulating** | Fee market rewards honest miners more than censors. |
| **Blockchain Fallacy** | Belief that putting IOUs on‑chain removes custodial risk. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^voskuil | Voskuil, Eric. *Cryptoeconomics* (2020). | — |

# Part I – Foundations

## Chapter 3 — Scarcity & Value · Re-examining the Inflation Principle

### 3.1  Absolute scarcity ≠ automatic value

Bitcoin’s 21 million cap is often touted as the reason it “must” appreciate.  
Yet scarcity is only **half** a price equation. Voskuil’s **Scarcity Fallacy** [^scarcity] notes there is only one *Mona Lisa*, yet countless equally scarce paintings fetch no bid.  
A good becomes *property*—and therefore valuable—only when **demand** meets limited supply.

### 3.2  The Inflation Principle — why supply alone doesn’t move purchasing power

Voskuil’s **Inflation Principle** [^inflationprinciple] formalises it:

> “Purchasing power varies with both the goods a money chases **and** the units in circulation.”

| Monetary species | Supply behaviour | Typical price effect |
|------------------|------------------|----------------------|
| Commodity money (gold) | Mining rises when price > cost | Dampened volatility: new supply absorbs price spikes |
| Monopoly fiat (USD) | State prints at negligible cost | Structural inflation as supply outruns demand |
| **Fixed-supply digital (Bitcoin)** | No new units after subsidy | **Deflationary only if demand keeps expanding** |

Thus late-era Bitcoin can deflate, but only when real demand grows faster than economic output.

### 3.3  Feedback dampers that tame volatility

| Money type | Negative-feedback brake | Effect |
|------------|------------------------|--------|
| Gold | High price → more mining → extra supply | Softens upward spikes |
| Fiat | High inflation → capital flight → FX controls | Politically damped—citizens pay |
| **Bitcoin** | High demand → higher on-chain fees → low-value traffic migrates | Caps congestion before meltdown |

Bitcoin substitutes **fee pressure** for the physical mining brake of gold.

### 3.4  Meme-busting

* **“21 million guarantees price.”** Scarcity without demand is worthless; value flows from Bitcoin’s utility as [**black-market money**](#glossary).  
* **“Stock-to-flow proves number go up.”** Flow reacts *to* expected price; using the ratio as a driver flips cause and effect [^stf].  
* **“Any issuance debases holders.”** Early Bitcoin inflation did *not* debase owners: miners expended real capital equal to coins earned.

### 3.5  Lessons for educators & investors

1. **Teach utility first, scarcity second.**  Bitcoin’s usefulness (censorship resistance, borderless settlement) *creates* demand; scarcity amplifies it into price.  
2. **Expect plateaus.**  With fixed supply, price gains stall if adoption stalls.  
3. **Understand fees as a safety valve.**  They ration scarce block-space, preventing congestion spirals.  
4. **Model > meme.**  Replace magic-number charts with incentive analysis.

---

## Glossary (excerpt) <a name="glossary"></a>

| Term | Brief definition |
|------|------------------|
| **Scarcity Fallacy** | Belief that rarity alone guarantees value; ignores demand side. |
| **Inflation Principle** | Purchasing power changes with both supply of units and demand for goods. |
| **Black-market money** | Currency usable where it is not allowed—permissionless & censorship-resistant. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^scarcity | Voskuil, E., *Cryptoeconomics*, “Scarcity Fallacy” chapter. | — |
| ^inflationprinciple | Voskuil, E., *Cryptoeconomics*, “Inflation Principle” chapter. | — |
| ^stf | Critique of Stock-to-Flow, see e.g., <https://witteman.medium.com/why-s2f-fails>. |

# Part I – Foundations

## Chapter 4 — Security Without Trust · The Risk-Sharing Principle

### 4.1  Why “many small risks” beat “one big vault”

Traditional finance defends funds by **concentrating** them—banks, vaults, payment processors.  
That buys convenience but also creates *single points of failure*: compromise the vault and you capture everything.

Bitcoin **inverts** the strategy. Voskuil’s **Risk-Sharing Principle** [^risksharing]:

> “Bitcoin is secure only while many independent individuals are willing **and able** to accept its risks and shoulder its defence.”

Every self-custody user and every honest miner carries a *sliver* of total danger.  
To steal or censor, an attacker must conquer thousands of tiny fortresses worldwide.

### 4.2  How risk is spread in practice

| Layer | Who bears it? | What an attacker must do |
|-------|---------------|--------------------------|
| **Full nodes** | Anyone running validation software | Partition or out-broadcast every node |
| **Miners** | Businesses & hobbyists racing for fees | Gain majority hash-power; pay real energy cost |
| **Key-holders** | End-users spending or holding coins | Seize each private key via coercion or hack |

No single layer suffices; together they form a mesh where the cheapest attack on one layer is frustrated by another.

### 4.3  Permissionlessness enables risk-sharing

If a cartel could decide *who* may run a node or mine, the mesh collapses.  
Hence Bitcoin’s rules embed the **Permissionless Principle** [^permissionless]: validation and mining are open by design.

Two norms make that work:

1. **Public rules, private identities.** Consensus code is open, but miners can remain pseudonymous, frustrating targeted coercion.  
2. **No protocol-level KYC.** A transaction is valid if it satisfies script & signature checks—period.

### 4.4  Centralisation pressures, and Bitcoin’s counter-moves

Voskuil flags two economic tugs [^centralrisk]:

* **Difficulty-of-use discount** → coins parked on exchanges.  
* **On-chain fee discount** → businesses batch internally instead of on-chain.

Bitcoin’s cultural and technical answers:

* “**Not your keys, not your coins**.”  
* User-friendly hardware wallets, descriptor standards.  
* Layer-2 tools (Lightning, Fedimint) that let casual users spend off-chain **without** surrendering unilateral exit.

### 4.5  Bitcoin as a social network of risk-takers

Baran’s 1964 research showed distributed networks survive partial failure.  
Voskuil’s **Social Network Principle** maps that to money: each Bitcoiner who self-custodies and validates is a node reinforcing the mesh.

> Lose a data center, the Web lives; lose a custodian, fiat users panic; lose 10 000 Bitcoiners? The chain keeps ticking—rules, not people, decide validity.

### 4.6  Checklist for readers

1. **Run a node.** It’s self-interest: you validate *your* money.  
2. **Treat miners as peers, not servants.** They trade confirmation for fees; either side can walk.  
3. **Self-custody is your insurance premium.** Outsource keys, and you exit the shield.  
4. **Reject whitelists.** Any rule requiring pre-approval re-creates a single target.

With risk-sharing clear, we next explore **Real Control**—why holding your own keys is not optional but foundational.

---

## Glossary (excerpt)

| Term | Definition |
|------|------------|
| **Risk-Sharing Principle** | Security grows as more independent actors validate, mine, and self-custody—spreading attack surface. |
| **Permissionless Principle** | No gatekeeper decides who may mine, validate, or transact. |
| **Centralisation Risk** | Security loss when mining, validation, or custody aggregates into a few coercible hubs. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^risksharing | Voskuil, E., *Cryptoeconomics*, “Risk Sharing Principle”. | — |
| ^permissionless | Voskuil, E., *Cryptoeconomics*, “Permissionless Principle”. | — |
| ^centralrisk | Voskuil, E., *Cryptoeconomics*, “Centralisation Risk”. | — |

# Part I – Foundations

## Chapter 5 — Real Control · Why Self-Custody Defines Bitcoin Ownership

### 5.1  From “has an account” to **owns the asset**

A century of bank culture taught us to equate a statement balance with possession.  
Bitcoin revives a harsher rule:

> **Real control = the ability to spend *or irreversibly destroy* the asset without anyone’s permission.** — Carvalho

If you cannot burn it, you don’t fully own it.  
This “burn test” cuts through every custody promise, staking pool, or side-chain peg.

### 5.2  Voskuil’s Custodial-Risk Principle, plain-spoken

In *Cryptoeconomics* Voskuil writes: a claim (bank IOU, token) is only as good as the custodian’s future honesty. Markets discount the claim by:

* **Exchange cost** – withdrawal fees & friction.  
* **Enforcement cost** – legal time, political risk.  [^custody]

Bitcoin sidesteps that discount by making the **owner** the custodian: hold the keys, hold the coins. Any re-intermediation simply re-creates the risk Bitcoin deletes.

### 5.3  The **Blockchain Fallacy**

Stamping an IOU on a chain does *not* fix custody; the issuer can still default or be coerced.  
Tokenised gold, stable-coins, or exchange balances all flunk the burn test:

| Asset type | Can holder burn? | Who can block redemption? | Real control? |
|------------|------------------|---------------------------|---------------|
| Exchange balance | **No** | Exchange / KYC gate | ✗ |
| Gold-backed token | No | Warehouse + regulators | ✗ |
| Lightning channel (you hold both keys) | Yes (force-close) | None | ✓ |
| On-chain bitcoin self-custodied | Yes | None | ✓ |

### 5.4  Economic consequences of widespread self-custody

1. **Censorship resistance scales with key-holders.** A state must battle millions of owners, not storm a vault.  
2. **Fee honesty.** Large custodians can mask true on-chain costs; self-custody keeps users price-aware.  
3. **Bad memes die quicker.** Schemes that fail the burn test suffer rapid “bank-runs,” purging weak designs.

### 5.5  Common objections, answered

| Objection | Clarification |
|-----------|---------------|
| “Most users won’t secure keys.” | Tools like hardware wallets, multisig collaboratives, and Lightning let non-experts *share* risk without surrendering exit. |
| “Regulation & insurance replace keys.” | They re-introduce enforcement cost and jurisdictional risk—useful for firms, not as a base-layer substitute. |
| “Smart-contract vaults still give me control.” | Only if you can unilaterally withdraw; upgradeable admin keys or delegated staking often break that guarantee. |

### 5.6  Practical literacy checkpoint

1. **Perform the burn thought-experiment.** Could *you* send the asset to `OP_RETURN` without help?  
2. **Default to native multisig over third-party insurance.** Distribute risk *without* restoring single points of failure.  
3. **Audit layer-2 exits.** A Lightning or Fedimint wallet must document unilateral close; if absent, control is illusion.

---

## Glossary (excerpt)

| Term | Definition |
|------|------------|
| **Real Control** | Ownership criterion: holder can spend or irreversibly destroy the asset without third-party approval. |
| **Custodial-Risk Principle** | Claims rely on a custodian; market discounts them by exchange & enforcement cost. |
| **Blockchain Fallacy** | Belief that recording IOUs on-chain removes custodial risk. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^custody | Voskuil, E., *Cryptoeconomics*, “Custodial Risk Principle”. | — |

# Part II – Dynamics of the Bitcoin Economy

## Chapter 6 — The Fee-Market Flywheel · From Utility Threshold to Stability

### 6.1  Why a “perfectly non-scalable” ledger must charge rent

Voskuil’s **Scalability Principle** states that *no amount of hardware can raise Bitcoin’s on-chain throughput*; bigger blocks only trade decentralisation for marginal capacity [^scalability].  
Every ten minutes the network must choose a **finite** set of transactions. That scarce commodity—block-space—is rationed by an auction. **Fees are its price.**

### 6.2  Birth and mechanics of the fee market

Early blocks were mostly empty; the 50 BTC subsidy paid miners.  
As usage grew, users attached tips to jump the queue. By 2013, fees mattered; by 2025 they often exceed 15 % of miner revenue during congestion.

Fees simultaneously:

1. **Allocate space.** Bidders reveal urgency.  
2. **Fund security.** Higher demand → higher fees → more hash-power.  
3. **Signal congestion.** Rising curve tells wallets to batch, route via Lightning, or delay.

### 6.3  The Utility Threshold Property—Bitcoin’s automatic toll-gate [^utility]

> “As fees rise, low-value uses migrate to substitutes; utility sets its own threshold.”

A coffee payment might justify 2 sat/vB but not 200 sat/vB.  
Instead of collapsing, the network **pushes** marginal traffic to cheaper rails while safeguarding high-value settlement.

| Mempool state | Typical median fee | On-chain use case |
|---------------|--------------------|-------------------|
| Calm | ≤2 sat/vB | Pocket change, sweeping dust |
| Busy | 5-20 sat/vB | Exchange withdrawals, LN opens |
| Congested | 50-300 sat/vB | Treasury moves, batched payouts |

### 6.4  Stability through price, not supply

Gold dampens volatility by expanding supply; fiat hides it via stealth inflation.  
Bitcoin, with fixed supply, can only damp **through price**: fees rise until excess demand backs off. This is Voskuil’s **Stability Property** [^stability].

### 6.5  Meme-busting

| Meme | Reality via Utility Threshold |
|------|------------------------------|
| “High fees kill adoption.” | Layers & batching absorb low-value traffic; base-layer remains premium settlement. |
| “Just raise the block size to keep fees low.” | Any size eventually fills; congestion re-emerges, with worse centralisation. |
| “Miners exploit users with fees.” | Fees are voluntary bids; competition drives margins toward cost. |

### 6.6  Teaching & builder take-aways

1. **Visualise the auction.** Tools like mempool.space let students watch fee lanes clear block by block.  
2. **Compare substitutes.** Show cost of Lightning, wrapped BTC, or even PayPal to illustrate the [**Substitution Principle**](#glossary).  
3. **Frame fees as security spend.** Complaining about “expensive blocks” is like complaining about a good lock on a vault.  
4. **Kill “fee fallacies.”** Side-fee and fee-recovery schemes ignore opportunity cost.

### 6.7  Bridge to consolidation vs substitution

Fee pressure nudges marginal users to cheaper rails—raising a strategic question:  
Do we embrace multiple monies (“many Bitcoins”) or scale via layers anchored to **one** chain?  
Chapter 7 weighs Voskuil’s **Consolidation Principle** against real-world substitution and sets up Carvalho’s counter-case.

---

## Glossary (excerpt)

| Term | Definition |
|------|------------|
| **Utility Threshold Property** | Minimum value a transfer must have to justify the current fee; rises with demand, pushing low-value uses to substitutes. |
| **Stability Property** | Bitcoin remains usable because rising fees damp excess demand instead of expanding supply. |
| **Substitution Principle** | Users migrate to cheaper substitutes when on-chain fees exceed their utility. |
| **Scalability Principle** | Base-layer throughput cannot be increased without sacrificing decentralisation. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^scalability | Voskuil, E., *Cryptoeconomics*, “Scalability Principle”. | — |
| ^utility | Voskuil, E., *Cryptoeconomics*, “Utility Threshold Property”. | — |
| ^stability | Voskuil, E., *Cryptoeconomics*, “Stability Property”. | — |

# Part II – Dynamics of the Bitcoin Economy

## Chapter 7 — One Money or Many? · Consolidation vs Substitution

### 7.1 Economic gravity toward a single coin

Voskuil’s **Consolidation Principle** [^consolidation]:

> “One coin is always ‘better’—higher utility—than two, so long as the resulting coin itself doesn’t price users out through on-chain fees.”

Every cross-currency trade pays real costs: spread, delay, compliance.  
In free markets, higher-quality money (harder to debase, cheaper to verify) tends to displace weaker ones (Thiers’ Law).  
Bitcoin’s censorship-resistant settlement gives it a quality edge over alt-coins and fiat; exchange-cost gravity thus pulls commerce toward **one** dominant money.

### 7.2 The counter-force: Substitution

Bitcoin’s own fee market creates the opposing **Substitution Principle** [^substitution]:

> “When on-chain fees exceed a user’s utility, they migrate to cheaper substitutes; effective money supply expands through migration, not issuance.”

High fees push low-value traffic to Lightning, wrapped BTC, alt-coins, or even PayPal—often *before* consolidation completes.

### 7.3 Visualising the tug-of-war

| Force | Mechanism | Favours… | Limiting factor |
|-------|-----------|----------|-----------------|
| **Consolidation** | Exchange-cost drag on multi-currency trade | One hard money | Only holds if on-chain fees < swap friction |
| **Substitution** | Fee pressure on small transfers | Multiple monies / layers | Substitutes must still be trusted and useful |

At low demand, Bitcoin’s quality edge dominates.  
At high demand, block-space scarcity triggers substitution.

### 7.4 Forks and the Network-Effect Fallacy

Maximalists sometimes claim any fork “halves network value” (Metcalfe’s Law).  
Voskuil’s **Network-Effect Fallacy** [^nefallacy] notes: once exchanges exist, two forks form a hybrid economy; utility loss equals conversion cost, **not** network-size squared.  
In practice, most economic weight sticks to the chain with superior security and depth—consolidation again.

### 7.5 Empirical clues (2017-2024)

| Cycle | Trigger | Predominant reaction | Result 1 yr later |
|-------|---------|----------------------|------------------|
| 2017 bull | \$30+ fees | Alt-coin migration (BCH, LTC) | BCH hash-rate collapses; BTC > 85 % settlement value |
| 2019 | Mild fees | Lightning growth ×10 | Sub-cent payments return on LN |
| 2021 NFT mania | \$50+ fees | ERC-20 & Solana detour | High-value NFTs migrate to wrapped-BTC / L2 |
| 2023–24 Ordinals | 400 sat/vB peaks | Wallet filters; batching | Mempool clears daily; no durable BTC fork |

Data suggest a *dynamic equilibrium*: gravity pulls activity back whenever layer tech lowers fee pain.

### 7.6 Strategic implications

1. **Exchange cost is an ally.** More merchants settling in BTC raise the penalty for alt-coins.  
2. **Fee management matters.** Batching & Lightning delay leakage.  
3. **Competition isn’t defeat.** Temporary substitution is fee pressure doing its job.  
4. **Narrative shapes outcomes.** Teaching “scaling = other chains” normalises fragmentation; teaching fee-layer literacy reinforces consolidation.

### 7.7 Bridge to Chapter 8

Now that we see the economic seesaw, we enter engineering strategy:  
Accept parallel “Bitcoins” for overflow, or scale via layers anchored to **one** chain?  
Chapter 8 pits Voskuil’s *many-Bitcoins* forecast against Carvalho’s **sweet-spot scaling**.

---

## Glossary (excerpt)

| Term | Definition |
|------|------------|
| **Consolidation Principle** | Market pressure toward a single dominant money to minimise conversion friction. |
| **Substitution Principle** | Users migrate to cheaper substitutes when fees exceed their utility. |
| **Network-Effect Fallacy** | Mistaking exchange-enabled hybrids for quadratic utility loss after a fork. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^consolidation | Voskuil, E., *Cryptoeconomics*, “Consolidation Principle”. | — |
| ^substitution | Voskuil, E., *Cryptoeconomics*, “Substitution Principle”. | — |
| ^nefallacy | Voskuil, E., *Cryptoeconomics*, “Network Effect Fallacy”. | — |

# Part II – Dynamics of the Bitcoin Economy

## Chapter 8 — Scaling Bitcoin · Layers vs “Many Bitcoins”

### 8.1 Why scaling is **not** “just add hardware”

Voskuil’s **Scalability Principle** [^scalability]:

> “Bitcoin transaction throughput is perfectly non-scalable; no amount of hardware raises it.”

Throughput hinges on two consensus dials—block size and block interval.  
* Raising either enlarges CPU, bandwidth, and archival burdens, thinning out grassroots validators and amplifying [**Centralisation Risk**](#glossary).  
* Keeping them small conserves decentralisation—at the cost of permanent block-space scarcity.

Every “scale-up” proposal is thus a *trade-off* between capacity and security; there is no free multiplier.

---

### 8.2 Voskuil’s forecast · *parallel coins will carry the overflow*

Since the base layer cannot grow safely, Voskuil predicts **Substitution** (Chapter 7) will mature into outright **multiplication**:

> Many independent chains replicating the Bitcoin design pattern will service lower-value tiers.  Creating such a chain is virtually free; users migrate when main-chain fees exceed their tolerance. [^substitution]

Outcome: a constellation of “Bitcoins,” each with lighter rules, smaller fees, and its own security budget.

---

### 8.3 Carvalho’s critique · substitution ≠ scaling

John Carvalho accepts substitution exists but argues:

*Separate chains are **competing monies**, not scaling.*

If each carries weaker hash-rate and thinner validation, users must constantly ask, “Is this coin still safe for my savings?”—the very cognitive load Bitcoin relieved.

**Sweet-spot thesis**

| Principle | Implementation |
|-----------|----------------|
| **Security first** | Keep **one** global settlement ledger with maximal decentralisation the world can afford. |
| **Economic throughput next** | Tune block size *within safety margin* **and** off-load routine traffic to Layer-2 protocols *anchored* to that ledger (Lightning, channel factories, Fedimint). |
| **Minimise escape velocity** | Layers permit unilateral exit to L1; a side-chain or alt-coin exit requires an FX trade and new trust assumptions. |

Thus “many Bitcoins” fragment network effects *and* dilute hash-power, whereas layered scaling preserves both.

---

### 8.4 Evidence in the wild (2017-2024)

| Event | Fee spike | Predominant reaction | One-year result |
|-------|-----------|----------------------|-----------------|
| 2017 bull | \$30+ | Alt-coin migration (BCH, LTC) | BCH hash-rate collapses; BTC > 85 % settlement share |
| 2019 | Mild | Lightning node count ×10 | Micro-payments return via LN |
| 2021 NFT mania | \$50+ | ERC-20 & Solana detour | High-value NFTs bridge back via wrapped-BTC & L2 |
| 2023-24 Ordinals | 400 sat/vB peaks | Wallet inscription filters, Taproot batching | Mempool clears daily; no durable BTC fork |

Empirically, **fee spikes do push traffic to substitutes**, yet consolidation re-asserts once layer tech improves. No parallel “Bitcoin” has retained meaningful economic weight.

---

### 8.5 Engineering the sweet spot

1. **Block-size governance**  
   *Target*: home validation on commodity hardware for a decade.  
   *Lever*: ultra-slow adjustments (e.g., +300-500 kB per decade) if node count and orphan rate still show margin.

2. **Layer-2 priority**  
   Incentivise channel factories, PTLC Lightning, communal mints—these settle *back* to L1, reinforcing its fee market instead of siphoning it.

3. **Fee-market literacy**  
   Wallets should surface sat/vB, default to batching, and recommend LN—normalising “different layers for different jobs” while preserving Bitcoin’s security umbrella.

---

### 8.6 Decision matrix for builders & educators

| Question | Layer-2 answer | Parallel-chain answer |
|----------|----------------|-----------------------|
| **Unilateral exit to L1?** | Yes (channel close, peg-out) | No (must trade or bridge) |
| **Unified hash-rate?** | Yes | Splits security budget |
| **Exchange-rate risk?** | None (BTC/BTC) | Yes (BTC/alt) |
| **Adds to L1 fee budget?** | Yes – channels open/close | No – fees accrue elsewhere |

Teaching this contrast helps newcomers see why “just more TPS on another chain” is not neutral to Bitcoin’s integrity.

---

### 8.7 Where Voskuil & Carvalho still agree

* Layers are inevitable; on-chain coffee is never coming back.  
* Massive block hikes are a **permanent** decentralisation hit, whereas layers are an **optional** compromise.  
* Fee pressure is the honest signal telling markets when to graduate traffic upwards.

The dispute is strategic, not mathematical: should overflow form loosely coupled side-ledgers anchored to BTC, or spawn sovereign “Bitcoins” vying for attention?

---

### 8.8 Key take-aways

* **Scaling is governance.** Every tweak reallocates costs among miners, node-runners, and users.  
* **Layers preserve economic gravity; parallel coins forfeit it.**  
* **Your role**: favour tools that keep unilateral exit and L1 anchoring; vote with your transactions for secure scaling.

Next, Chapter 9 synthesises the entire model—showing how sound economics, risk-sharing, real control, and pragmatic layering converge to keep Bitcoin the premier black-market-to-global-market money.

---

## Glossary (excerpt)

| Term | Definition |
|------|------------|
| **Scalability Principle** | Base-layer throughput cannot be raised without centralisation trade-offs. |
| **Sweet-spot scaling** | Carvalho’s view: maximise secure throughput on one chain; use layers for overflow. |
| **Centralisation Risk** | Security loss when mining, validation, or custody aggregates into few coercible hubs. |

---

## References

| Anchor | Source | URL |
|---|---|---|
| ^scalability | Voskuil, E., *Cryptoeconomics*, “Scalability Principle”. | — |
| ^substitution | Voskuil, E., *Cryptoeconomics*, “Substitution Principle”. | — |

# Part III – Synthesis

## Chapter 9 — Putting It All Together · A Cohesive Bitcoin Mental Model

### 9.1 Eight building blocks, one structure

| Step | Statement | Where proved |
|------|-----------|--------------|
| **1 Problem** | State monies monetise power via inflation & censorship. | Ch. 1 |
| **2 Design** | Bitcoin deletes those levers with fixed supply + permissionless PoW. | Ch. 2 |
| **3 Value** | Scarcity alone is inert; demand flows from censorship-resistant utility. | Ch. 3 |
| **4 Defence** | Risk-Sharing + Energy Sinking convert demand into a distributed shield. | Ch. 4 |
| **5 Ownership** | Self-custody (“Real Control”) makes every user a defender. | Ch. 5 |
| **6 Throughput** | Fees ration block-space, funding security while off-loading overflow. | Ch. 6 |
| **7 Macro game** | Exchange-cost gravity pulls to one money; high fees push marginal traffic out. | Ch. 7 |
| **8 Strategy** | Layers keep gravity centred; many-Bitcoin proliferation dilutes it. | Ch. 8 |

Remove any block—fixed supply, risk sharing, fee market, or self-custody—and the edifice collapses.

### 9.2 Four-axis rubric for future proposals

| Axis | Ask yourself… | If **no** → action |
|------|---------------|--------------------|
| **Security** | Does it preserve open validation & proof-of-work incentives? | Weakens shield → redesign |
| **Control** | Can every user still unilaterally exit to L1 (burn test)? | Custodial risk → migrate |
| **Economics** | Do fees ultimately return to Bitcoin miners? | Hash-rate fragments → reject |
| **Utility** | Does it lower total friction *without* centralising nodes? | Cosmetic / harmful → ignore |

Use this checklist before endorsing any BIP, fork, or “scaling” pitch.

### 9.3 Teaching priorities

1. **Concept first, tech second.** Wallet UX will change; consensus axioms won’t.  
2. **Self-custody as curriculum.** A hardware-wallet demo beats an hour of slides.  
3. **Fee-literacy.** Show batching/LN turning “high fees” into an operating cost, not a crisis.  
4. **Trade-offs, not slogans.** Present both Voskuil’s and Carvalho’s views; let students model outcomes with the rubric.

### 9.4 Open questions for the 2030s

| Frontier | Key uncertainty |
|----------|-----------------|
| **Hash-rate geography** | Can home-miner & renewable tech blunt mega-farm dominance? |
| **Layer sovereignty** | Will federated mints & channel factories keep unilateral exit cheap, or will custodial “crypto-banks” creep back? |
| **Regulatory escalation** | Does the fee-driven “Other Means” war reach Phase 3 (state mining) or stall at capital-control skirmishes? |
| **Hardware curve** | Will ASIC commoditisation outpace subsidy decline? |

The mental model lets us reason about each without crystal-ball guessing: trace incentives, then run the rubric.

### 9.5 Closing thought

Bitcoin is not inevitable; it is an ongoing **social contract enforced by mathematics and incentive**.  
Its strength grows every time someone:

1. **Learns the principles** outlined here,  
2. **Holds Real Control** over their keys, and  
3. **Pays an honest fee** to settle value on-chain.

Do that, teach the next person to do the same, and the black-market cash that began as a cypherpunk hobby matures into a global, censorship-resistant standard—one block at a time.

---

### Glossary of Key Terms  

| Term | Definition (as used in **Black Market Money**) |
|------|-------------|
| **Axiom of Resistance** | Foundational assumption that a money can, in practice, operate despite state hostility; without it Bitcoin’s security model is incoherent. |
| **Bitcoin** | The set of cryptodynamic principles that secure a fixed-supply digital money without permission from any authority; not merely one chain or ticker. |
| **Black-market money** | A currency designed to work where it is *not* allowed—permissionless, censorship-resistant, and non-custodial. |
| **Block space** | The scarce commodity of bytes available in each block; miners auction it via transaction fees. |
| **Censorship-Resistance Property** | Economic feedback in which fee premiums attract non-censoring miners until attempts at transaction filtering become unprofitable. |
| **Centralisation Risk** | Security loss that arises when mining, validation, or custody aggregates into a few coercible hubs. |
| **Consolidation Principle** | Market pressure toward a single dominant money to minimise exchange friction. |
| **Custodial Risk Principle** | Any claim that depends on a third-party custodian carries default risk and is discounted by the market. |
| **Energy Sinking** | Proof-of-work’s requirement that miners burn external resources, attaching real cost to reversal of history. |
| **Fee market** | Continuous auction where users bid sat/vB for block space; funds both miner revenue and chain security. |
| **Hash-power** | Aggregate SHA-256 throughput committed to mining; proportional to the cost of rewriting blocks. |
| **Hoarding** | Holding money idle; affects price but not utility unless demand to *spend* changes. |
| **Layer-2** | Protocols (e.g. Lightning, Fedimint) that move transactions off-chain while retaining unilateral settlement back to L1. |
| **Mining** | Competitive process of assembling valid blocks under proof-of-work to earn subsidy + fees. |
| **Permissionless Principle** | No gatekeeper decides who may mine, validate, or transact; openness is itself a security requirement. |
| **Proof-of-Work (PoW)** | Probabilistic mechanism that ties each valid block to a measurable expenditure of computational energy. |
| **Real Control** | Ownership criterion: the holder can *spend or irreversibly destroy* the asset without third-party approval. |
| **Risk-Sharing Principle** | Security grows as more independent actors validate, mine, and self-custody—spreading attack surface. |
| **Scalability Principle** | Transaction throughput on the base layer is *perfectly non-scalable*; larger blocks only trade security for capacity. |
| **Seigniorage** | Profit a money issuer earns by creating new units below market value; eliminated in Bitcoin by the fixed cap. |
| **Self-custody** | Direct control of private keys; prerequisite for real control and full participation in risk-sharing. |
| **Stability Property** | Bitcoin remains usable because rising fees damp excess demand instead of expanding supply (contrasts with gold & fiat). |
| **Substitution Principle** | When on-chain fees rise above a user’s utility, they migrate to cheaper substitutes (layers, alt-coins, fiat). |
| **Sweet-spot scaling** | Carvalho’s thesis that Bitcoin should maximise *secure* throughput on one chain, with layers to absorb overflow—opposing the “many Bitcoins” view. |
| **Utility Threshold Property** | Minimum value a transfer must have to justify current fees; rises with demand, pushing low-value uses to substitutes. |
| **Value Proposition** | Bitcoin’s core promise: eliminate seigniorage and censorship at the cost of proof-of-work and limited block space. |
| **“Many Bitcoins”** | Voskuil’s forecast that separate Bitcoin-like chains will carry lower-value traffic as fees price them off the main chain. |
| **Node (full)** | Software that validates every rule from genesis, enforcing consensus and broadcasting transactions/blocks. |
| **Confirmation depth** | Number of blocks buried atop a transaction; deeper = costlier to reverse, traded against time and fee. |

*Use this glossary as a quick reference while reading; each term is unpacked in detail within the corresponding chapters.*

### References

---

## 1.  Primary Texts  

| Label | Bibliographic note | URL |
|-------|--------------------|-----|
| **Voskuil 2020** | Voskuil, Eric. *Cryptoeconomics: Fundamental Principles of Bitcoin*, 2nd Edition, Version 1.2.1 (PDF). | — (contained in uploaded file) |
| **Satoshi 2008** | Nakamoto, S. “Bitcoin: A Peer-to-Peer Electronic Cash System.” | https://bitcoin.org/bitcoin.pdf |

---

## 2.  Economics, Money & Banking  

| Source | URL |
|--------|-----|
| Austrian School (Wikipedia) | https://en.wikipedia.org/wiki/Austrian_School |
| Barter | https://en.wikipedia.org/wiki/Barter |
| Capital flight | https://en.wikipedia.org/wiki/Capital_flight |
| Commodity | https://en.wikipedia.org/wiki/Commodity |
| Demurrage (currency) | https://en.wikipedia.org/wiki/Demurrage_(currency) |
| Exchange controls (FX) | https://en.wikipedia.org/wiki/Foreign_exchange_controls |
| Gresham’s / Thiers’ Law | https://en.wikipedia.org/wiki/Gresham%27s_law#Reverse_of_Gresham's_law_(Thiers'_law) |
| Inflation | https://en.wikipedia.org/wiki/Inflation |
| Marginal utility | https://en.wikipedia.org/wiki/Marginal_utility |
| Money supply & demand | https://en.m.wikipedia.org/wiki/Supply_and_demand |
| Opportunity cost | https://en.wikipedia.org/wiki/Opportunity_cost |
| Reserve currency | https://en.wikipedia.org/wiki/Reserve_currency |
| Seigniorage | https://en.wikipedia.org/wiki/Seigniorage |
| Substitute good | https://en.m.wikipedia.org/wiki/Substitute_good |
| Thiers’ Law (reverse-Gresham) | same as Gresham/Tiers’ link above |

---

## 3.  Bitcoin, Mining & Cryptography  

| Source | URL |
|--------|-----|
| Bitcoin.org “Choose your wallet” (web wallets) | https://bitcoin.org/en/wallets/web |
| Proof-of-Stake (Wikipedia) | https://en.wikipedia.org/wiki/Proof-of-stake |

---

## 4.  Governance, Law & State Power  

| Source | URL |
|--------|-----|
| Executive Order 6102 (US gold seizure) | https://en.m.wikipedia.org/wiki/Executive_Order_6102 |
| IMF home page | https://www.imf.org |
| Sovereignty (Wikipedia) | https://en.wikipedia.org/wiki/Sovereignty |

---

## 5.  Game Theory & Social Science  

| Source | URL |
|--------|-----|
| Prisoner’s dilemma | https://en.wikipedia.org/wiki/Prisoner%27s_dilemma |
| Metcalfe’s Law | https://en.wikipedia.org/wiki/Metcalfe%27s_law |

---

## 6.  Classical & Modern Writings Referenced  

| Source | URL |
|--------|-----|
| Rothbard, M. *Man, Economy, and State* (Mises Institute) | https://mises.org/library/man-economy-and-state-power-and-market |
| Mises, L. — Biography page | https://en.wikipedia.org/wiki/Ludwig_von_Mises |
| Murray Rothbard (Wikipedia) | https://en.wikipedia.org/wiki/Murray_Rothbard |

---

## 7.  Miscellaneous Technical & Financial Links  

| Source | URL |
|--------|-----|
| Fedwire fee table (Wikipedia) | https://en.wikipedia.org/wiki/Fedwire |
| Fedwire quotation in outline (same page) | (see above) |
| Standard deviation | https://en.wikipedia.org/wiki/Standard_deviation |
| Proof-of-memory (concept overview) | https://en.wikipedia.org/wiki/Proof-of-stake#Proof_of_memory (anchor used in pdf) |

---

## 8.  Original Outline / Book-Specific Concepts (no external URLs)  

These items came entirely from Voskuil’s *Cryptoeconomics* or John Carvalho’s additions and therefore have no separate public link:

- Axiom of Resistance  
- Risk-Sharing Principle  
- Energy Sinking  
- Power Regulating (Fee-driven censorship resistance)  
- Custodial-Risk Principle  
- Consolidation Principle  
- Utility Threshold Property  
- Stability Property  
- Sweet-Spot Scaling (Carvalho)  
- Real Control (Carvalho)

---
