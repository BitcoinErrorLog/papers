# **Black Market Money** – *A Pedagogical Rewrite of Voskuil’s “Cryptoeconomics”*

### Table of Contents — *Black Market Money*  

| Part / Chapter | Title | One-Sentence Summary |
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
| **References** | — | Categorized list of all relevant links. |

*Each chapter builds logically on the previous, guiding readers from first principles to contested frontiers while preserving Voskuil’s rigor and adding fresh, practice-oriented context.*

## Author’s Introduction  
### John Carvalho ( aka BitcoinErrorLog )  

I’ve spent the last decade building, breaking, and defending Bitcoin tools—first as a curious node-runner, later as CEO of Synonym, and always as that loud guy on Twitter poking holes in half-baked narratives. In that time one book has stood apart as a genuine attempt to model *how* Bitcoin actually works, economically and technically: **Eric Voskuil’s *Cryptoeconomics***.

Eric didn’t write a beach read; he wrote a dense constellation of essays. Each gem is rigorous, but newcomers often bounce off the asteroid field long before they reach the core. This project—**Black Market Money**—is my effort to turn those scattered insights into a single navigable map.

### What stays

* **Rational economics** – Eric’s method never hand-waves; every claim reduces to incentives and human action. That integrity is non-negotiable.  
* **Core principles** – Risk-sharing, energy sinking, permissionlessness, utility thresholds—the pillars remain intact.  
* **Fallacy hunting** – The original book’s best moments expose cherished memes as sloppy thinking; we keep that spirit of myth-busting.

### What changes

* **Narrative thread** – Instead of standalone essays, chapters now build from first principles to advanced debates, so readers can climb step-wise rather than teleport.  
* **Pedagogical tone** – Academic, yes, but in the sense of a good seminar: clear definitions, worked examples, and constant reality-checks.  
* **My own lenses** – I introduce two recurring motifs: **real control** (ownership measured by the power to destroy) and a **sweet-spot approach to scaling** that challenges Eric’s “many Bitcoins” forecast.

### Who this is for

* **Bitcoin podcasters & their audiences** – People who already *care*, but want tighter arguments than “number go up.”  
* **Educators** – Curriculum builders at Plan B, KUDOS, or any university econ course brave enough for honest monetary theory.  
* **Builders & policy wonks** – Engineers, lawyers, and regulators who need a rigorous map before they redraw the territory.

### How to read it

1. **Start at Part I** even if you mine blocks for breakfast. The terminology is sharpened and will save us both headaches later.  
2. **Argue margin-notes** – disagreeing is the whole point; use the rubric in Chapter 9 to stress-test new ideas.  
3. **Teach someone else** when you’re done. Bitcoin’s security budget ultimately rests on informed humans who choose self-custody and pay honest fees.

Bitcoin began as black-market money—digital cash that works even where it’s *not allowed* to. If this book does its job, you’ll finish with the mental model to keep it that way, and the vocabulary to explain *why* it matters to anyone who’ll listen.

— **John Carvalho**  
Lisbon, 2025

## Part I – Foundations  
### Chapter 1 — The Monetary Dilemma: State Money vs. Black-Market Money  

> *“The value of Bitcoin over its alternatives derives directly from **removing the state from control over both monetary supply and transaction censorship**.”* — Voskuil citeturn0file0  

---

### 1. Why Money Becomes a State Target  

1. **Seigniorage — the silent tax**  
   * When a central bank issues new units, it acquires real resources in exchange for paper or database entries.  
   * The profit (face value – production cost) is seigniorage, a direct revenue stream for the state and its privileged banking partners. citeturn0file19  

2. **Censorship & surveillance**  
   * By monopolising payment rails the state can freeze or reverse transactions, enforce capital controls, and mine personal data for taxation or social control. citeturn0file0  

3. **Reserve-currency politics**  
   * States hoard “hard” assets (gold yesterday, government-bonds or foreign currency today) while issuing a softer domestic currency to citizens, maximising their taxing latitude through inflation and controls. citeturn0file8  

These incentives make any money that resists dilution and censorship an existential threat to the modern fiscal state.

---

### 2. State Solutions: From Gold Standard to “Fedcoin”  

| Era | Technique | Result |
|-----|-----------|--------|
| **Classical gold standard** | Redeemable bank notes backed 100 % in gold | Political crises → suspension of redemption, devaluation, eventual fiat takeover citeturn0file8 |
| **Fiat & central banking** | Unlimited note issue + lender-of-last-resort credit | Permanent inflation, recurrent boom-bust cycles, and growing financial surveillance citeturn0file3 |
| **Projected “Fedcoin”** | A state-branded crypto-look-alike with inflation & censorship levers re-inserted (hard-fork subsidies, soft-fork whitelist) | Cosmetic modernisation that preserves seigniorage and control; marketed as a “safer” Bitcoin citeturn0file15 |

Thus, every historical reform has sought to **re-secure the same two powers**—issue at will, approve transfers at will—just in new technological clothing.

---

### 3. Bitcoin’s Counter-Design — Black-Market Money  

* **Fixed supply** eliminates seigniorage: 21 million coins, issued once and never politically expanded.  
* **Permissionless settlement** (risk-sharing miners + public validation) denies central censorship levers. citeturn0file3  
* **Self-custody = real control** (see Chapter 5): anyone who holds keys can use, save, or even burn their coins without approval.  

Because these properties are inseparable from Bitcoin’s architecture, **any attempt to turn it into “white-market” money necessarily breaks it**. The protocol assumes a hostile environment—what Voskuil calls the *Axiom of Resistance*—and is secured precisely by operating beyond permission. citeturn0file18

---

### 4. Economic Consequences of Choosing Black-Market Money  

| Feature | State Money | Bitcoin |
|---------|-------------|---------|
| Monetary inflation | Discretionary, opaque | Impossible (supply cap) |
| Transaction policy | Politically determined; accounts can be blocked | Market fee-driven; anyone can broadcast |
| Privacy by default | No – KYC/AML requirements | Partial – improves with proper usage |
| Custodial risk | Central bank & banks can default or bail-in | Optional; self-custody removes counter-party |
| Tax visibility | Hidden in inflation | Taxes must be explicit, making them politically costly |

This **cost-reallocation** is what creates Bitcoin’s value proposition: people voluntarily incur the higher “hard” costs of energy and bandwidth precisely to *avoid the invisible tax and veto power* embedded in monopoly money citeturn0file11.

---

### 5. Why Education Matters  

Voskuil’s original *Cryptoeconomics* presented these ideas as stand-alone essays; here we embed them into a single narrative:  

1. Understand the state’s dual incentive (inflate & censor).  
2. Recognise how every historical reform has preserved that incentive.  
3. See Bitcoin’s architecture as a deliberate break with that pattern.  

With this framing, newcomers can judge claims like “CBDCs will be like Bitcoin” or “Bitcoin should back government notes” against first principles rather than headlines.

---

### Key Take-aways  

* **State money is a revenue engine first, medium of exchange second.**  
* **Bitcoin’s design removes both revenue streams—seigniorage and censorship—by invariant code, not by political promise.**  
* **Any “upgrade” that re-introduces those streams is a regression to past monopolies.**  

In the next chapter we formalise *what* Bitcoin is and *how* its properties achieve this break, laying the groundwork for later debates on custody, fees, and scaling.

---

## Part I – Foundations  
### Chapter 2 — *What Is Bitcoin?* A Money Secured by Principles  

---

### 2.1 A working definition  

**Bitcoin is the set of principles that let any group of people define, issue, and transfer a fixed-supply digital money without asking permission from a third party.**  
Because the word *Bitcoin* was first applied to the concepts, not to one specific chain or implementation, it rightly names any system that preserves those principles citeturn1file5.

---

### 2.2 The three “cryptodynamic” forces  

Eric Voskuil groups Bitcoin’s essential security forces under *Cryptodynamic Principles* citeturn1file0  

| Force | What it does | Take-away for the reader |
|-------|--------------|--------------------------|
| **Risk-Sharing** | Many independent actors validate and spend the coin, so no single coercion point exists. | *Security is social*: every self-custody user is part of the shield. citeturn1file11 |
| **Energy Sinking** | Miners burn real-world resources to attach cost to rewriting history. | *Proof-of-work* is not waste—it prices attacks. |
| **Power Regulating** | The fee market gives honest hash-power a financial edge over censors. | If a censor spends more, fees rise until resistance is profitable. citeturn1file4 |

If any one of these forces is removed—e.g., by replacing proof-of-work with proof-of-stake or by requiring permission to run a node—the result is **not Bitcoin** citeturn1file2.

---

### 2.3 Core traits that flow from those forces  

1. **Fixed supply**  
   *21 million coins, ever.*  Bitcoin sits in the “fixed-supply” category of the monetary spectrum (commodity, monopoly, fixed) citeturn1file19.  
   The cap removes seigniorage incentives that plague state money.  

2. **Permissionless access**  
   Any person may validate blocks, relay transactions, or mine because the protocol assumes the *Axiom of Resistance*—it must survive hostile states citeturn1file4.  Thus Bitcoin can only exist as *black-market money*; moving it wholly into the “white market” would break its model citeturn1file17.

3. **Censorship resistance**  
   Fees make it costly to exclude transactions; honest miners earn more by including them. Over time, fee pressure drives hash-power toward non-censors citeturn1file13.

4. **Non-custodial ownership (real control)**  
   A unit is secured by a private key, not by an institution.  Custodial promises re-introduce default risk, whereas widespread self-custody spreads that risk across the entire economy citeturn1file14.  
   The “blockchain technology” claim—that one can secure outside assets merely by recording claims—fails because custody, not data, determines control citeturn1file9.

---

### 2.4 Placing Bitcoin in the “money taxonomy”  

Voskuil’s taxonomy separates monies by **use-value**:  

| Class | Example | Supply control |
|-------|---------|----------------|
| Commodity money | Gold | Market-driven mining |
| Monopoly money  | USD | Central-bank issuance |
| **Fiat, fixed-supply digital** | **Bitcoin** | None after genesis citeturn1file16 |

Although Bitcoin shares fiat’s lack of industrial use, its **fixed supply and permissionless security push it into a unique third category**—neither commodity nor state monopoly.

---

### 2.5 Why Bitcoin ≠ “a blockchain”  

A blockchain is just an append-only data structure.  What makes Bitcoin valuable is *who* can write to it (any miner), *why* they can’t cheat (proof-of-work cost), and *who* enforces the rules (every spending user).  Stripping those elements to repurpose the ledger for custodial assets brings back the very trusted third party risk Bitcoin was designed to remove citeturn1file9.

---

### 2.6 Mental model checkpoint  

* **Technology ≠ security** – People, acting in economic self-interest, are the security layer.  
* **Bitcoin’s rules hold only as long as users self-custody and verify.**  
* **Every feature that seems “inefficient” (energy expenditure, capped throughput) is a deliberate trade-off that keeps the three cryptodynamic forces in balance.**

With this foundation we are ready to explore—with far less confusion—why scarcity alone does not guarantee value (Chapter 3) and how Bitcoin’s risk-sharing fee market establishes long-term stability (Chapter 6).

## Part I – Foundations  
### Chapter 3 — *Scarcity & Value* Re-examining the Inflation Principle  

---

#### 3.1 Absolute scarcity ≠ automatic value  

Bitcoin’s fixed 21 million cap is often touted as the single reason it “must” appreciate.  
Yet *scarcity is only half of a price equation*. Voskuil’s **Scarcity Fallacy** points out that there is one *Mona Lisa* too, but countless equally scarce paintings have no bidders at all citeturn2file0.  
A good becomes *property*—and therefore valuable—only when *demand* meets limited supply. If nobody wants it, zero price prevails regardless of how rare it is.

---

#### 3.2 The Inflation Principle—why supply alone doesn’t move purchasing power  

Voskuil’s **Inflation Principle** formalises the relationship:

> *“A money changes in purchasing power in proportion to both the goods it chases **and** the units in circulation.”* citeturn2file11  

He distinguishes three monetary species:

| Species | Supply behaviour | Typical price effect |
|---------|------------------|----------------------|
| **Commodity money** (gold) | Market mining rises when price > cost | *Stable*: new units absorb equivalent resources |
| **Monopoly money** (fiat) | State expands supply at low cost | *Inflationary*: extra units outpace demand |
| **Fixed-supply digital** (late-stage Bitcoin) | No new units after subsidy epoch | *Deflationary* **only if** demand keeps growing |

Thus Bitcoin’s later era can *deflate*—but only when real demand expands faster than economic output.

---

#### 3.3 Negative-feedback dampers that keep prices in check  

| Money type | Feedback loop | Effect on volatility |
|------------|--------------|----------------------|
| Commodity | High price ⇒ more mining ⇒ extra supply | Dampens upward spikes |
| Monopoly  | High inflation ⇒ capital flight ⇒ FX controls/tax resistance | Politically damped—but at citizens’ expense citeturn2file16 |
| **Bitcoin** | High demand ⇒ higher on-chain fees ⇒ pushes marginal use to layers/substitutes | Caps demand before congestion spirals citeturn2file12 |

Bitcoin’s built-in fee market substitutes the physical mining brake that gold has: as blocks fill, only higher-value transfers remain economical, limiting further fee growth and stabilising price.

---

#### 3.4 Debunking popular memes  

* **“21 million makes Bitcoin valuable.”**  
  Absolute scarcity without demand is worthless; value arises from the network’s usefulness and the security it buys citeturn2file6.

* **“Stock-to-flow proves number go up.”**  
  Flow (new production) itself reacts to expected price; treating the ratio as a causal driver of hardness reverses cause and effect citeturn2file16.

* **“Any issuance = loss of purchasing power.”**  
  Early Bitcoin inflation did **not** debase holders, because miners consumed real capital equal to the units they earned citeturn2file17.

---

#### 3.5 Implications for Bitcoiners & educators  

1. **Focus on utility, not mystique.** Teach newcomers that Bitcoin’s usefulness in resisting censorship and seigniorage drives demand; scarcity merely *amplifies* that demand into price.  
2. **Expect periods of flat or falling price if demand stalls.** Fixed supply is a double-edged sword: absent growth, deflation stops.  
3. **Understand fees as a stability valve.** Rising fees are not a bug but the economic brake that keeps Bitcoin from over-extension.  
4. **Model, don’t myth-make.** Popular tropes like “digital gold automatically moons” ignore the bid side of the market and the feedback mechanisms above.

With supply–demand dynamics clarified, readers can now appreciate why Bitcoin’s **decentralised security, not mere rarity, underpins its value**—a foundation we deepen in Chapter 4, where we unpack how risk-sharing and permissionlessness protect the system that people actually demand.

## Part I – Foundations  
### Chapter 4 — *Security Without Trust* Decentralisation & the Risk-Sharing Principle  

---

#### 4.1 Why “many small risks” beat “one big vault”  

Banks, bullion vaults, and payment processors protect money by **concentrating** it behind walls, passwords, or laws.  That buys convenience, but it creates *single points of failure*: whoever coerces or compromises the vault controls the funds.

Bitcoin flips that logic.  Voskuil calls the cornerstone the **Risk-Sharing Principle**:

> *“Bitcoin is secure only while many independent individuals are willing **and able** to accept its risks and shoulder its defence.”* citeturn1file11  

Instead of one fortress, every self-custody user and every honest miner carries *a sliver* of the total danger.  To steal or censor, an attacker must conquer thousands of tiny fortresses spread across the globe.

---

#### 4.2 How the system spreads risk in practice  

| Layer | Who holds the risk? | What the attacker must do |
|-------|--------------------|---------------------------|
| **Full nodes** | Anyone running validation software | Rewrite local copy ⇒ must out-broadcast or partition every other node |
| **Miners** | Businesses or hobbyists racing for block reward | Gain majority hash-power ⇒ pay real energy & hardware cost |
| **Users** | Key-holders spending or receiving coins | Seize every private key ⇒ physically or legally coerce each owner |

No single layer is sufficient; together they produce a *mesh* in which the cheapest attack on one layer is frustrated by another.

---

#### 4.3 Permissionlessness makes risk-sharing possible  

If a cartel or regulator could decide *who* may run a node or mine, the entire mesh would collapse into a licensing regime.  That is why Bitcoin’s ruleset embeds the **Permissionless Principle**—validation and mining are open to all by design citeturn1file7.  

This openness depends on two concrete norms:  

1. **Public rules, private identities.**  Consensus logic is published in code, but miners are free to remain pseudonymous, frustrating targeted coercion (see **Public Data Principle**) citeturn1file4.  
2. **No protocol-level KYC.**  Transactions are valid if they satisfy the script & signature checks—nothing more.  Governments can still police *exits* (exchanges), but they cannot choke the protocol itself.

---

#### 4.4 Centralisation pressures & how Bitcoin counters them  

Voskuil warns that usability shortcuts tug risk back toward a few custodians—*centralisation pressures* citeturn1file8:

- **Difficulty-of-use discount** → people park coins on exchanges.  
- **On-chain fee discount** → businesses settle internally instead of on the ledger.  

Bitcoin’s answer is cultural as much as technical:

* **“Not your keys, not your coins”**—an ethic derived from the *Custodial Risk Principle* citeturn1file14.  
* Wallet standards (PSBT, descriptors) and small, cheap hardware devices lower the bar to self-custody without re-introducing super-nodes.  
* Layer-2 protocols (Lightning, Fedimint) keep day-to-day payments off-chain *without* forfeiting on-chain exit rights—risk is reduced *relatively*, not recentralised absolutely.

---

#### 4.5 Bitcoin as a social network of risk-takers  

Baran’s 1964 paper on resilient networks showed that survival probability rises as nodes become *distributed* rather than *central* citeturn1file11.  Voskuil’s **Social Network Principle** maps that idea onto money: every human who chooses to hold or accept Bitcoin is a node in the monetary mesh.  

*Lose a data center, the Web survives; lose a custodian, fiat users panic; lose 10 000 Bitcoiners?*—the chain keeps ticking because rules, not people, decide validity.

---

#### 4.6 Key lessons for readers & students  

1. **Running a node isn’t altruism—it’s self-interest.**  You validate *your* money, and in doing so, you strengthen the whole.  
2. **Miners don’t “serve” users; they *trade* confirmation for fees.**  That market clears only because either side can walk away.  
3. **Self-custody is the insurance premium for censorship resistance.**  Outsource custody and you opt out of the risk-sharing dividend.  
4. **Any proposal that requires whitelisting, identity, or privileged mining is a regression to single-point risk.**  

With a clear grasp of *how* Bitcoin distributes danger, we can understand *why* fees, hoarding, and scaling debates matter.  In Chapter 5 we sharpen this perspective with the concept of **Real Control**—showing that holding keys is not merely recommended but *foundational* to Bitcoin’s economics.

## Part I – Foundations  
### Chapter 5 — *Real Control* Why Self-Custody Defines Bitcoin Ownership  

---

#### 5.1 From “has an account” to **owns the asset**  

A century of bank culture taught people to equate a statement balance with possession.  
But Bitcoin’s design resurrects a sharper distinction, captured in John Carvalho’s rule of thumb:

> **Real control = the power to spend *or irreversibly destroy* an asset at will.**

If you can’t burn it, you don’t truly own it.  
That brutal test cuts through every custody arrangement, “crypto bank,” or layer-2 promise.

---

#### 5.2 Voskuil’s Custodial-Risk Principle, in plain language  

In *Cryptoeconomics*, Eric Voskuil notes that a “claim” (bank IOU or token) is only as good as the custodian’s future honesty.  The market discounts such claims by the:

- **Exchange cost** (fees + withdrawal friction)  
- **Enforcement cost** (time, lawyers, political risk) citeturn1file14  

Bitcoin sidesteps that discount by making the *owner* the sole custodian: keys in hand, no IOU required.  Any re-intermediation simply re-creates the very risk the protocol eliminated.

---

#### 5.3 Why blockchain entries ≠ real control  

Voskuil’s **Blockchain Fallacy** warns that stamping a claim onto a ledger does **nothing** to fix custody; the issuer can still default or be coerced citeturn1file9.  
Tokenised gold, fiat-backed stablecoins, or exchange balances all fail Carvalho’s “destroy test”:

| Asset type | Can holder burn it? | Who stops redemption? | Real control? |
|------------|--------------------|-----------------------|---------------|
| Exchange balance | **No** | Exchange/KYC gate | ✗ |
| Gold-backed token | No | Warehouse + regulators | ✗ |
| Lightning channel (if you keep both keys) | Yes (can close on-chain) | None | ✓ |
| On-chain bitcoin in your hardware wallet | Yes | None | ✓ |

---

#### 5.4 Economic consequences of widespread self-custody  

1. **Risk distribution fuels censorship resistance.**  
   When millions hold keys, a state must fight a hydra, not storm a vault (Chapter 4).  

2. **Fee sensitivity stays honest.**  
   Large custodians might under-price withdrawals for growth, masking true on-chain costs. Self-custody keeps users *price-aware*.

3. **BS narratives die faster.**  
   Projects that cannot survive the “burn it” test eventually suffer bank-run-like exits; Bitcoin’s ecology learns and hardens.

---

#### 5.5 Counter-arguments & clarifications  

| Objection | Clarification |
|-----------|---------------|
| “Most users won’t secure keys; we need custodians for mass adoption.” | Layers like Lightning, Fedi-mints, or multisig collaboratives let non-experts *share* custody without surrendering unilateral exit rights.  Convenience need not equal absolute trust. |
| “Insurance / regulations can replace self-custody.” | They re-introduce enforcement cost and jurisdictional risk.  Good for some enterprises, but no substitute for permissionless money. |
| “A smart-contract vault (staking, DeFi) still gives me control.” | Only if you alone can *unilaterally* withdraw or burn.  Delegated staking keys or upgrade-able contracts often flunk the test.  Always ask: **who can freeze or upgrade me out?** |

---

#### 5.6 Practical literacy for the reader  

1. **Perform the burn thought-experiment.**  
   Could *you* broadcast a transaction sending the asset to an unspendable address without anyone’s help? If not, learn or reconsider custody.  
2. **Prefer native multisig to third-party “insurance.”**  
   Splitting keys among friends/family or reputable cosigners preserves exit rights while mitigating single-point loss.  
3. **Audit Layer-2 promises.**  
   Lightning, Aqua, or Cashu wallets must document how a user can unilaterally close or peg-out.  If documentation is absent, so is real control.

---

#### 5.7 Bridge to Part II  

With **Real Control** established, the reader now sees *why* private keys are sacred and *how* Bitcoin’s security model collapses if widespread custodial shortcuts take over.  
Part II begins by zooming out to the *fee market and scaling debate*—showing how control, cost, and capacity interlock as Bitcoin grows.

## Part II – Dynamics of the Bitcoin Economy  
### Chapter 6 — *The Fee-Market Flywheel* From Utility Threshold to Stability  

---

#### 6.1 Why a “perfectly non-scalable” ledger must charge rent  

The **Scalability Principle** states that *no amount of hardware can raise Bitcoin’s on-chain throughput*; bigger blocks only trade some decentralisation for a marginal gain in space citeturn3file4.  
Every ten minutes the system must choose a *finite* set of transactions. Because that space is scarce, miners naturally auction it to the highest bidders. That auction **is** the fee market.

*Key idea*: **Block space is a scarce commodity; fees are its price.**

---

#### 6.2 The birth of the fee market  

Early Bitcoin blocks were mostly empty, so Satoshi hard-coded a nominal 50 BTC subsidy to pay miners. As usage grew, users began attaching tips to jump the queue. By 2013 the subsidy-only era was over; by 2024, fees already make up a double-digit share of miner revenue in busy epochs.  

Economically, fees:  

1. **Allocate space** – Users reveal how urgently they need their payment cleared.  
2. **Fund security** – Higher demand → higher fees → more hash-power defending the chain.  
3. **Signal congestion** – A rising fee curve tells wallets it is time to batch, open channels, or defer low-value transfers.

---

#### 6.3 The Utility Threshold Property—Bitcoin’s automatic toll-gate  

Voskuil formalises the feedback loop:

> *“Increasing utility implies a rising fee level… At some point the cost of transfer exceeds the value transferred; low-value uses migrate to substitutes.”* citeturn3file1  

That break-even line is the **utility threshold**. A coffee payment may work at 2 sat/vB, but if fees spike to 150 sat/vB the same user will swipe a debit card or route through Lightning instead. In effect, *Bitcoin self-regulates*: the chain keeps high-value settlements while cheaper layers or monies absorb minor traffic.  

| Demand state | Median fee | Typical on-chain use-case |
|--------------|-----------|---------------------------|
| Low | ≤2 sat/vB | Pocket money, sweeping change |
| Moderate | 5-30 sat/vB | Exchange withdrawals, LN channel opens |
| Congested | 50-300 sat/vB | Large settlements, batched treasury moves |

---

#### 6.4 Stability through price, not supply  

Gold dampens price swings by **adding supply** when it becomes lucrative to mine; fiat dampens them by **hiding supply growth** (inflation). Bitcoin, with a fixed supply, can only damp through **demand rationing**—fees rise until some activity waits or leaves. That is Voskuil’s **Stability Property**: the money stays usable because fee pressure limits congestion citeturn3file2.  

*Observation*: a higher fee era does **not** mean Bitcoin “breaks.” It means block space is clearing at market price.

---

#### 6.5 Common misunderstandings  

| Meme | Reality explained by Utility Threshold |
|------|----------------------------------------|
| “Fees make Bitcoin useless for the masses.” | Layers and batching push small payments off-chain while preserving base-layer security for settlement. |
| “We must raise the block size to keep fees low forever.” | Any size fills eventually; the threshold re-emerges because demand grows faster than linear blockspace citeturn3file4. |
| “High fees enrich miners at users’ expense.” | Fees are a *bid*: users voluntarily pay what the confirmation is worth; competition among miners keeps margins near cost. |

---

#### 6.6 Teaching & policy take-aways  

1. **Show learners the auction** – visualisers like mempool.space let students watch fees self-adjust block by block.  
2. **Highlight substitution** – compare on-chain cost to Lightning, wrapped BTC on side-chains, or even fiat, illustrating Voskuil’s **Substitution Principle** citeturn3file0.  
3. **Frame fees as security spending** – they are cap-ex for censorship resistance; complaining about “expensive blocks” is like complaining about good locks on a vault.  
4. **Discourage fee fallacies** – “fee recovery,” “side-fee attacks,” and similar notions ignore opportunity cost and market clearing citeturn3file6.  

---

#### 6.7 Bridge to the consolidation vs. substitution debate  

Once we see how fees nudge marginal users toward cheaper rails, a strategic question arises:  
Should Bitcoiners *embrace* multiple monies (“many Bitcoins”), or *internalise* scaling via layers anchored to one chain?  

Chapter 7 tackles that tug-of-war, examining Voskuil’s **Consolidation Principle** against real-world substitution pressures—and sets the stage for John Carvalho’s counter-argument that true scaling must keep economic gravity centred on *one* highly secure Bitcoin.

## Part II – Dynamics of the Bitcoin Economy  
### Chapter 7 — *One Money or Many?* Consolidation vs Substitution  

---

#### 7.1 The economic gravity toward a single coin  

Voskuil’s **Consolidation Principle** starts with a mundane observation: every time two traders must swap currencies before closing a deal they pay a *real* cost—spread, slippage, delay. Therefore,  
> *“One coin is always ‘better’ (higher utility) than two, so long as the resulting coin itself doesn’t price users out through on-chain fees.”* citeturn3file2  

That exchange friction acts like gravity: merchants gradually converge on the *most useful* money because doing so shrinks overhead. In free markets Thiers’ Law (the *reverse* of Gresham’s) predicts the “better” money—harder to debase, cheaper to verify—swallows the rest. Historically gold out-competed silver once global trade made purity testing easier; Bitcoin might do the same to weaker digital monies.  

---

#### 7.2 But scarcity of block space pulls the other way  

The same book that champions consolidation also introduces its counter-force, the **Substitution Principle**:  

> *“As confirmation fees rise, some users switch to substitutes or stop transacting; rising cost effectively *increases* the practical supply of monies.”* citeturn3file0  

High fees are not hypothetical—they are the logical outcome of the **Utility Threshold Property** (Chapter 6). When the threshold climbs, small or time-flexible payments migrate to anything cheaper: Lightning, alt-coins, even PayPal. Thus demand *leaks* before a single-money ideal is reached.  

---

#### 7.3 The tug-of-war visualised  

| Force | Mechanism | Favours… | Limiting factor |
|-------|-----------|----------|-----------------|
| **Consolidation** | Exchange-cost drag on multi-currency trade | One dominant money | Only holds if base-layer fees < swap cost |
| **Substitution** | Rising on-chain fees make alternatives attractive | Multiple monies / layers | Alternatives must still *work* & be trusted |

At low demand, consolidation wins—Bitcoin is strictly better than scattering value across thinly traded coins. At very high demand, substitution sparks: users save satoshis by moving minor activity elsewhere.  

---

#### 7.4 Splits, forks, and the myth of quadratic loss  

Maximalists sometimes claim that *any* fork “halves network value” by Metcalfe’s Law. Voskuil’s **Network Effect Fallacy** corrects this: once an exchange market exists, the two forks blend into a *hybrid* economy whose utility is reduced only by conversion cost, **not** by the square of lost peers citeturn3file10. In practice most economic weight sticks to the chain with superior security and market depth—the gravity picture again.  

---

#### 7.5 Real-world evidence to date  

*2011–2016*: Bitcoin dominated >90 % of crypto market cap; fees were low, so consolidation reigned.  
*2017 bull run*: fees spiked over \$30; ERC-20 tokens and BCH lured retail users—substitution moment.  
*2020–2024*: Lightning adoption plus batched exchange withdrawals lowered effective costs; BTC’s share of *settlement value* rebounded even as on-chain fees remained volatile.  

The data suggest a dynamic equilibrium: Bitcoin’s economic mass keeps pulling activity back whenever layer-2 or batching tech catches up with demand.

---

#### 7.6 Strategic implications for Bitcoiners  

1. **Exchange cost is our ally.**  Every additional merchant who settles in BTC raises the penalty for using a fringe coin.  
2. **Fee management is critical.**  Wallet batching, Lightning, and side-channel techniques delay the point where substitution kicks in.  
3. **Competition isn’t defeat.**  Temporary leakage to alt-coins may simply reflect fee pressure doing its job; gravity returns if alternatives can’t match Bitcoin’s assurance level.  
4. **Narrative matters.**  If educators equate “scaling” with “just use another chain,” they unintentionally promote permanent fragmentation. Teaching *why* consolidation benefits everyone sets a higher bar for substitutes.

---

#### 7.7 Bridge to Chapter 8  

We now see the economic seesaw between *one big money* and *many smaller substitutes*. In Chapter 8 we enter the engineering arena: **Should Bitcoiners accept a future of parallel “Bitcoins,” or focus on layered throughput that keeps settlement gravity anchored to a single, maximally secure chain?** John Carvalho’s “sweet-spot” thesis confronts Voskuil’s “many-Bitcoins” prediction head-on.

## Part II – Dynamics of the Bitcoin Economy  
### Chapter 8 — *Scaling Bitcoin* Layers vs. “Many Bitcoins”  

---

#### 8.1 Why scaling is not “just add hardware”  

Voskuil’s **Scalability Principle** is blunt:

> *“Bitcoin transaction throughput is perfectly non-scalable; no amount of hardware raises it.”* citeturn3file4  

Throughput is fixed by two consensus dials—**block size** and **block interval**.  
• Raise either and you enlarge each node’s processing, bandwidth, and archival load, thinning out grassroots validators and boosting **Centralisation Risk**.  
• Keep them small and you conserve decentralisation—at the cost of permanent congestion pressure.  

Hence every “scale-up” proposal is a *trade-off* between capacity and security; there is no free multiplier.

---

#### 8.2 Voskuil’s forecast: *parallel coins will carry the overflow*  

Because the base layer cannot grow without weakening itself, Voskuil predicts that over time **substitution** (Chapter 7) evolves into outright **multiplication**: many independent chains implementing the *Bitcoin design pattern* for different price tiers. He reasons that:

1. **Utility Threshold** permanently prices small transfers off the main chain.  
2. **Layer-2s are local compromises; parallel chains are systemic additions.**  
3. **Economic actors prefer cheaper substitutes once fees exceed their tolerance**—and creating a Bitcoin-like chain is virtually free citeturn3file0.

Result: a constellation of “Bitcoins” with similar rules but lighter blocks, each defending its own smaller economy and fee market.

---

#### 8.3 Carvalho’s critique: substitution ≠ scaling  

John Carvalho accepts points 1 and 2—fees rise, layers compromise—but contests point 3:

*Separate chains aren’t “scaling”; they’re **competing monies**.*  
If each has weaker hash-rate and thinner validation, users must constantly ask, *“Is this coin still secure enough for my savings?”*—the very burden Bitcoin relieved them from.

Carvalho’s **sweet-spot thesis**:

| Principle | Application |
|-----------|-------------|
| **Security first** | Keep **one** global settlement ledger with the highest decentralisation tolerance the planet can afford. |
| **Economic throughput next** | Tune block size **within** safety margins *and* push routine traffic to Layer-2 protocols *anchored* by that ledger (Lightning, channel factories, Fedimint). |
| **Minimise escape velocity** | Layers let users exit back to L1 at will; a side-chain or alt-coin exit requires an FX trade and new trust assumptions. |

Thus “many Bitcoins” fragment network effects *and* dilute hash-power, while layered scaling preserves both.

---

#### 8.4 Evidence from the field (2017-2025)  

| Year | Fee crisis? | Reaction dominated by | Outcome |
|------|-------------|-----------------------|---------|
| 2017 | Yes (>$30) | **Alt-coin migration** (BCH, LTC) + batching | BCH hash-rate fizzles; BTC share of settlement value remains >85 % |
| 2019 | Mild | Lightning growth 10× | Sub-cent payments re-enter BTC ecosystem |
| 2021 | NFT mania ($50+) | ERC-20 & Solana detour | High-value NFTs migrate to wrapped-BTC or ETH L2 by 2024 |
| 2023-24 | Ordinals fees peaks | Wallet-level inscription filters & Taproot batching | BTC mempool clears daily; no durable fork emerges |

Empirically, **temporary fee spikes do push traffic to substitutes**, yet gravity (Chapter 7) reasserts once layer tech or batching improves. No parallel “Bitcoin” has retained significant economic weight.

---

#### 8.5 Engineering the sweet spot  

1. **Block-size governance**  
   *Target*: keep home validation viable on commodity hardware with multi-year bandwidth buffers.  
   *Practical lever*: slow, conservative increases (e.g., an adaptive 300 k-500 kB hike per decade) if empirical node-count and orphan-rate data show margin.

2. **Layer-2 priority**  
   *Incentives*: encourage channel factories, PTLC-enabled Lightning, and communal mints; these settle *back* to L1, reinforcing its fee market instead of siphoning it.

3. **Fee-market literacy**  
   Wallets should surface *sat/vB* cost in native units, default to batch sends, and recommend LN where suitable—normalising the idea that **different layers suit different payment types** without leaving Bitcoin’s security umbrella.

---

#### 8.6 Decision matrix for educators & builders  

| Question | Layer-2 answer | Parallel-chain answer |
|----------|----------------|----------------------|
| *Can users exit to L1 unilaterally?* | Yes (channel close, peg-out) | No (must trade or bridge) |
| *Does hash-rate stay unified?* | Yes | Splits |
| *Is exchange-rate risk introduced?* | Minimal (BTC/BTC) | Yes (BTC/alt) |
| *Does adoption increase L1 security budget?* | Yes – channels open/close | No – fees accrue to other chain |

Educators should highlight these contrasts so newcomers grasp **why “more TPS on another chain” is not neutral** to Bitcoin’s monetary integrity.

---

#### 8.7 Where Voskuil & Carvalho still agree  

* Layers are unavoidable; on-chain coffee is never coming back.  
* Larger blocks are a *permanent* decentralisation hit, whereas layers are an *optional* one.  
* Fee pressure is the honest signal that tells the market when to graduate traffic upward.

The dispute is strategic, not mathematical: *should the overflow form loosely coupled side-ledgers under BTC’s anchor, or spawn sovereign “Bitcoins” competing for attention?*

---

#### 8.8 Key take-aways for readers  

* **Scaling is governance**: every change reallocates costs between miners, node-runners, and users.  
* **Layers keep economic gravity centred on one money.** Parallel coins forfeit that advantage.  
* **Your role**: choose wallets and services that respect unilateral exit and settlement back to Bitcoin; vote with your transactions for secure scaling.

With the engineering debate framed, Chapter 9 will synthesise the entire mental model—showing how sound economics, risk-sharing security, real control, and pragmatic layering converge to keep Bitcoin the premier black-market-to-global-market money.

## Part III – Synthesis  
### Chapter 9 — *Putting It All Together* A Cohesive Bitcoin Mental Model  

---

#### 9.1 From the monetary dilemma to a living economy  

1. **Problem** – State monies monetise power through inflation and censorship (Chapter 1).  
2. **Design** – Bitcoin deletes those levers via fixed supply, permissionless validation, and proof-of-work (Chapter 2).  
3. **Value** – Scarcity alone means nothing; demand flows from the security and utility of *black-market money* (Chapter 3).  
4. **Defense** – Risk-sharing plus energy sinking turn that demand into a distributed shield (Chapter 4).  
5. **Ownership** – Self-custody (“real control”) ensures every user is both beneficiary and defender (Chapter 5).  
6. **Throughput** – Fees ration block-space, funding security while pushing overflow to cheaper rails (Chapter 6).  
7. **Macro game** – Exchange-cost gravity pulls toward one money; high fees push marginal traffic to substitutes (Chapter 7).  
8. **Strategy** – Carvalho vs Voskuil: layer-centric scaling keeps gravity centred; spawning parallel “Bitcoins” dilutes it (Chapter 8).

Each layer of logic builds on the last.  Remove any piece—fixed supply, risk sharing, fee market, or self-custody—and the structure collapses.

---

#### 9.2 Mental map for future debates  

| Axis | Ask yourself… | If answer is **no** |
|------|---------------|--------------------|
| **Security** | Does this proposal preserve open validation and proof-of-work incentives? | It weakens the shield; discard or redesign. |
| **Control** | Can every user still unilaterally exit to L1 and, if needed, burn their coins? | Custodial risk re-enters; educate or migrate. |
| **Economics** | Does fee revenue ultimately return to Bitcoin’s miners? | Hash-power fragments; expect weaker finality. |
| **Utility** | Does the change lower *total* exchange friction without centralising nodes? | Odds are it’s cosmetic at best, harmful at worst. |

This four-question rubric turns a sprawling discourse into a checklist any Bitcoiner, podcaster, or student can apply.

---

#### 9.3 What educators should emphasise  

* **Concept first, tech second** – Wallet UX changes, consensus maths does not.  
* **Self-custody as curriculum** – A hardware-wallet demo imparts more understanding than an hour of theory.  
* **Fee-market literacy** – Show learners how batching and Lightning convert “high fees” from a crisis into an operating cost.  
* **Scaling trade-offs, not slogans** – Present both Voskuil’s and Carvalho’s views; let students model outcomes with the rubric above.

---

#### 9.4 Open questions for the next decade  

| Frontier | Key uncertainty |
|----------|-----------------|
| **Hash-rate centralisation** | Can renewable baseload and home-miner tech curb geographic or corporate clustering? |
| **Layer sovereignty** | Will federated mints and channel factories keep unilateral exit cheap, or will custodial “crypto banks” creep back? |
| **Regulatory pressure** | Does the fee-driven “Other Means” war (Voskuil) reach Phase 3 (state mining) or stall at capital-controls skirmishes? |
| **Hardware cost curve** | Does ASIC commoditisation continue, stabilising security budget as subsidy wanes? |

Our mental model lets us reason about each without crystal-ball guessing: trace the incentives, check them against the rubric.

---

#### 9.5 Closing thought  

Bitcoin is not inevitable; it is an ongoing **social contract enforced by mathematics and incentive**.  Its strength grows every time an individual:  

1. **Learns the principles** outlined here,  
2. **Holds real control** over their keys, and  
3. **Pays an honest fee** to settle value on-chain.  

Do that, teach the next person to do the same, and the black-market money that began as a cypherpunk experiment matures into a global, censorship-resistant standard—one block at a time.

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
