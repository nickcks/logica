# Acquiring Strategy Diagnostic

**Part of the Logica Payments series** · [Issuer P&L Diagnostic](../issuer-economics/) · [Co-Brand Strategy](../cobrand-strategy/) · [Portfolio Conversion](../portfolio-conversion/) · Acquiring Playbook · [SME Payments](../sme-payments/)

---

## Problem

Acquiring looks simple from the outside: charge merchants a fee, pass through interchange and scheme costs, keep the residual. In practice, the residual margin is structurally compressed — interchange (set by issuers) and scheme fees (set by networks) are non-negotiable, and what remains for the acquirer is typically 20–50 basis points before operating costs. An acquirer can grow transaction volume 30% year-over-year while net profit declines, because the growth is coming from enterprise merchants negotiating IC++ rates to the bone while processing costs scale linearly.

The acquiring market is simultaneously consolidating at the top and fragmenting at the bottom. Traditional bank acquirers are losing SME merchants to PayFacs and ISVs that embed payments into vertical software. The four-party model has evolved into an 18+ party ecosystem where gateways, processors, ISOs, PayFacs, ISVs, and marketplaces all compete and cooperate in shifting configurations. Every participant on the value chain has structural incentive to migrate upward — ISVs become ISOs, ISOs become PayFacs, PayFacs apply for acquiring licenses — creating a permanent erosion pressure on incumbent acquirers.

This tool diagnoses an acquiring business across three layers: P&L economics, distribution model, and strategic positioning. It makes explicit the failure modes that aggregate volume reporting obscures — so you can see where value is being created and where it is leaking before the quarterly results tell you.

---

## Framework

### The Acquiring P&L: A Residual Margin Business

Unlike issuer economics (driven by interest income and rewards), acquirer economics are driven by the spread between what the merchant pays and what the acquirer cannot control.

| Component | Role | Controllable? |
|---|---|---|
| **MSC (Merchant Service Charge)** | Total fee charged to merchant (% of transaction value) | Partially — constrained by competition and merchant bargaining power |
| **Interchange** | Paid to the issuing bank; largest single cost line | No — set by card networks, varies by MCC, card type, and region |
| **Scheme fees** | Paid to the card network (volume fees, transaction fees, assessment) | No — set by the network; varies by market and transaction type |
| **Net acquirer margin** | MSC minus interchange minus scheme fees | This is the residual — typically 20–50 bps in competitive markets |
| **Processing + overhead** | Authorization, clearing, settlement, fraud ops, compliance | Yes — the primary lever for margin improvement |
| **VAS revenue** | DCC, data analytics, terminal software, fraud tools, reporting | Yes — the primary lever for revenue diversification |

**Core insight:** An acquirer's profit is not the MSC. It is the residual after two layers of uncontrollable cost — and even that residual must cover processing, fraud losses, and overhead before anything reaches the bottom line. The only strategic levers are: (1) merchant mix management, (2) processing cost efficiency, (3) value-added services revenue, and (4) risk loss control.

---

### Three Pricing Models — Determined by Merchant Size, Not Choice

| Model | Mechanism | Merchant segment | Acquirer margin profile |
|---|---|---|---|
| **IC++ (Interchange Plus Plus)** | Interchange + scheme fee + acquirer markup, each line visible | Enterprise / large merchants | Transparent, thin, stable — acquirer markup typically 5–15 bps |
| **Blended** | Single rate covering all costs; merchant sees one number | SME / mid-market | Opaque, higher margin — some transactions subsidize others |
| **Subscription / flat** | Fixed monthly fee + low per-transaction rate | Micro / nano merchants | Predictable for merchant; margin depends on volume per merchant |

Pricing model is not a commercial strategy decision. It is a structural pairing dictated by the merchant's information processing capacity: enterprise merchants have teams to audit IC++ invoices; SMEs need simplicity; micro merchants need predictability. An acquirer's margin is therefore a function of its merchant size distribution — heavy enterprise means thin transparent margins; heavy SME means blended pricing with information asymmetry premium.

---

### The Partnership Spectrum — Upward Migration Is the Default

The acquiring ecosystem is a spectrum of control, from gateway (technology layer only) to licensed acquirer (full stack). Every participant has structural incentive to migrate upward because upward movement = more control = more margin.

| Model | What they control | Typical margin | Migration pressure |
|---|---|---|---|
| **Gateway** | API layer, routing, payment data schema | Thin per-txn fees | → Wants to add processing |
| **ISO (Independent Sales Organization)** | Merchant sales relationships | Commission / residual share | → Wants PayFac economics |
| **PayFac (Payment Facilitator)** | Sub-merchant onboarding, first-layer risk, settlement | Higher — controls onboarding + risk | → Wants acquiring license |
| **Licensed Acquirer** | Full stack: licensing, settlement, compliance, capital | Full residual | Defending against upward migration of partners |

**Key dynamic:** A successful PayFac partner is a temporary ally. As it accumulates volume, it sees the margin it is sharing with its sponsoring acquirer and calculates that a license of its own would be more profitable. The acquirer's PayFac portfolio follows a predictable lifecycle: recruit → grow → graduate → replace. This is not a failure — it is the structural reality of the partnership model, and must be managed as such.

---

### The Fragmentation Opportunity

The four-party model (cardholder → merchant → acquirer → issuer) has evolved into an 18+ party system with gateways, processors, ISOs, PayFacs, ISVs, marketplaces, orchestration layers, and fraud vendors all participating. For merchants, this fragmentation creates pain: multiple vendors, multiple contracts, multiple points of failure. For acquirers and integrators, fragmentation creates opportunity — whoever can consolidate the merchant's payment stack captures both switching cost and pricing power.

Market entry timing should be assessed not by market size, but by fragmentation index: how many vendors does the average merchant need to complete the payment chain? Above three, an integrator has a structural entry point.

---

## Decision Rules

Nine rules across three diagnostic layers. Each rule tests a specific failure mode observable in acquiring businesses across markets.

> **On thresholds:** Values below are portfolio-level heuristics informed by publicly available industry benchmarks and the author's experience across Asia Pacific, Middle East, and European payment markets. They serve as triage indicators — specific market conditions (regulatory regime, interchange regulation, digital maturity) will shift the applicable ranges.

### Layer 1 — Economics

**Rule 1 — Residual Margin Viability**
IF (MSC rate − interchange rate − scheme fee rate) ≤ 15 bps
THEN: FAIL — residual margin is structurally insufficient to cover operating costs in most market structures; the business is effectively a pass-through with no value capture
IF ≤ 25 bps: WARN — margin exists but is thin; vulnerable to interchange increases, scheme fee adjustments, or competitive MSC compression
ACTION: Re-examine merchant mix — shift toward SME segments with blended pricing; negotiate scheme fee optimization with network; if margin is fundamentally unrecoverable, evaluate whether the acquiring business should be restructured as a distribution channel for cross-sell rather than a standalone profit center.

**Rule 2 — Net Profit Margin**
IF (MSC − interchange − scheme fee − processing/overhead cost) ≤ 3 bps of transaction volume
THEN: FAIL — the business generates volume but not profit; processing costs are consuming the residual
IF ≤ 10 bps: WARN — operating margin exists but provides minimal buffer against cost increases or volume shocks
ACTION: Audit processing cost per transaction by channel (POS vs. e-commerce vs. MOTO); benchmark against industry processing cost ranges; evaluate make-vs-buy on processing infrastructure — self-built processing has higher fixed cost but lower marginal cost at scale, while outsourced processing has the reverse profile.

**Rule 3 — Risk Cost Control**
IF fraud and chargeback losses > 20 bps of transaction volume
THEN: FAIL — risk costs are consuming a disproportionate share of the already-thin residual margin; indicates either merchant quality issues, inadequate fraud tooling, or insufficient monitoring
IF > 12 bps: WARN — elevated risk costs; review merchant onboarding criteria and transaction monitoring thresholds
ACTION: Segment fraud losses by merchant category and channel; implement tiered monitoring (real-time for high-risk MCCs, batch for low-risk); evaluate AI-based fraud scoring if not already deployed; consider whether high-risk merchant categories are worth the volume given the loss profile.

### Layer 2 — Distribution

**Rule 4 — Merchant Mix Profitability**
IF SME merchant revenue share < 25% of total acquiring revenue
THEN: FAIL — the portfolio is structurally dependent on enterprise merchants who negotiate margins to near-zero; SME merchants (with blended pricing and lower bargaining power) are the actual profit engine in acquiring
IF < 40%: WARN — enterprise-heavy portfolio; margin pressure will intensify as large merchants continuously renegotiate
ACTION: Build or acquire SME distribution capability — either through ISV/PayFac partnerships, embedded payment integrations, or direct digital onboarding. The transition from enterprise-dependent to SME-balanced is typically a 2–3 year strategic shift, not a tactical adjustment.

**Rule 5 — Partner Concentration**
IF top 2 partners (PayFac/ISO/ISV) account for > 60% of total merchant volume
THEN: FAIL — the acquiring business is structurally exposed to partner graduation or exit; a single partner's decision to obtain its own acquiring license can eliminate a majority of the volume base within 12–18 months
IF > 40%: WARN — concentration risk is elevated; begin pipeline diversification
ACTION: Establish a "partner portfolio management" discipline: continuously recruit mid-size PayFacs/ISVs to build pipeline; model the graduation timeline for each major partner (indicatively, large PayFacs tend to evaluate self-licensing within 3–5 years of reaching significant volume); contractually secure minimum notice periods for partner exit.

**Rule 6 — Channel Modernization**
IF partner-channel (ISV + PayFac + digital) share of newly signed merchants ≤ 20%
THEN: FAIL — merchant acquisition is still dependent on direct sales or legacy bank referral channels, which cannot reach the long tail of SME merchants cost-effectively; in developed markets, ISVs and PSPs often account for a significant share of new SME merchant sign-ups
IF < 35%: WARN — channel mix is lagging market evolution; competitors with stronger partner/digital channels will capture SME growth
ACTION: Define target ISV verticals (e.g., restaurant POS, retail management, hospitality) and build integration partnerships; assess whether a PayFac enablement strategy (making it easy for ISVs to embed your acquiring under their brand) would accelerate distribution.

### Layer 3 — Strategic Position

**Rule 7 — VAS Revenue Diversification**
IF value-added services revenue ≤ 5% of total acquiring revenue
THEN: FAIL — the business competes solely on MSC in a market where MSC is commoditizing; without VAS (DCC, data analytics, fraud tools, terminal software, reporting), there is no differentiation and no margin buffer
IF < 15%: WARN — VAS exists but is not yet a meaningful profit contributor
ACTION: Audit which VAS capabilities exist and their attach rates; prioritize DCC (immediate revenue for cross-border merchants), data/analytics products (high margin, creates switching cost), and integrated fraud tools (defensive — reduces Rule 3 risk while generating revenue).

**Rule 8 — E-Commerce Readiness**
IF e-commerce share of total acquiring volume < 15%
THEN: FAIL — the business is structurally concentrated in POS, the slower-growing channel; e-commerce acquiring has generally outpaced POS growth in most markets, and merchants increasingly expect omnichannel acceptance from a single provider
IF < 30%: WARN — e-commerce presence exists but is underweight relative to market direction
ACTION: Assess gateway/e-commerce technical capabilities; evaluate whether current processing infrastructure supports CNP (card-not-present) transactions efficiently; consider partnership or acquisition to close the digital gap.

**Rule 9 — Margin Sustainability (Composite)**
IF residual margin ≤ 25 bps AND VAS revenue < 10% AND SME share < 35%
THEN: FAIL — the business has thin economics, no revenue diversification, and an enterprise-heavy merchant base; this combination is structurally unsustainable as competitive and regulatory pressures intensify
IF 2 of the 3 conditions are met: WARN — the business has one structural weakness buffer remaining; address the weakest dimension before it compounds
ACTION: This is a strategic-level finding, not an operational fix. The recommended action depends on which two conditions are triggering: if margin + VAS are weak, the path is aggressive VAS buildout; if margin + SME are weak, the path is merchant mix rebalancing; if VAS + SME are weak, the business may be viable in the near term but is competitively fragile.

---

## Worked Example

**Scenario A:** A traditional bank acquirer in a developed Asia Pacific market with regulated interchange, serving primarily large retailers and hotel chains through direct sales relationships.

| Parameter | Value |
|---|---|
| Average MSC rate | 120 bps |
| Blended interchange | 85 bps |
| Scheme fee rate | 10 bps |
| Processing + overhead | 15 bps |
| SME revenue share | 30% |
| Top-2 partner share | 55% |
| Digital/partner acquisition share | 20% |
| VAS revenue share | 5% |
| E-commerce volume | 20% |
| Fraud + chargeback rate | 6 bps |

**Diagnostic results:**

| Rule | Status | Detail |
|---|---|---|
| R1 — Residual Margin | ⚠️ Warn | 25 bps residual (120 − 85 − 10) — at the boundary; thin but positive |
| R2 — Net Profit | ⚠️ Warn | 10 bps net (25 − 15) — at the boundary; minimal buffer |
| R3 — Risk Cost | ✅ Pass | 6 bps — well controlled |
| R4 — Merchant Mix | ⚠️ Warn | 30% SME — enterprise-heavy, margin pressure rising |
| R5 — Partner Concentration | ⚠️ Warn | 55% in top-2 — graduation risk is real |
| R6 — Channel Modernization | ❌ Fail | 20% partner channel — relying on legacy direct sales |
| R7 — VAS Revenue | ❌ Fail | 5% VAS — no revenue diversification |
| R8 — E-Commerce | ⚠️ Warn | 20% e-commerce — underweight |
| R9 — Margin Sustainability | ❌ Fail | 3 of 3 conditions met (thin margin ≤ 25 + low VAS + enterprise-heavy) |

**Overall diagnosis: Critical — structural overhaul required.** This profile captures the classic incumbent bank acquirer trap: every individual metric looks "survivable" in isolation, but the compound effect is structural fragility. The margin is at the boundary (25 bps), the distribution is legacy-dependent, VAS is nearly absent, and R9 confirms all three sustainability risks are present simultaneously. The recommended sequence: (1) build ISV/PayFac partnership capability to access SME merchants through embedded channels, (2) launch VAS products (DCC and data analytics) to diversify revenue, (3) develop e-commerce processing capability. This is a 2–3 year transformation requiring board-level commitment, not a quarterly optimization.

**Scenario B:** A fintech-integrated acquirer in a European market with strong ISV partnerships, digital-first onboarding, and an SME-heavy merchant base.

| Parameter | Value |
|---|---|
| Average MSC rate | 180 bps |
| Blended interchange | 100 bps |
| Scheme fee rate | 12 bps |
| Processing + overhead | 20 bps |
| SME revenue share | 70% |
| Top-2 partner share | 25% |
| Digital/partner acquisition share | 65% |
| VAS revenue share | 20% |
| E-commerce volume | 60% |
| Fraud + chargeback rate | 10 bps |

**Diagnostic results:**

| Rule | Status | Detail |
|---|---|---|
| R1 — Residual Margin | ✅ Pass | 68 bps residual — healthy, driven by blended SME pricing |
| R2 — Net Profit | ✅ Pass | 48 bps net — strong |
| R3 — Risk Cost | ✅ Pass | 10 bps — acceptable |
| R4 — Merchant Mix | ✅ Pass | 70% SME — profit engine engaged |
| R5 — Partner Concentration | ✅ Pass | 25% — diversified |
| R6 — Channel Modernization | ✅ Pass | 65% — digital-first |
| R7 — VAS Revenue | ✅ Pass | 20% — meaningful diversification |
| R8 — E-Commerce | ✅ Pass | 60% — digital-native |
| R9 — Margin Sustainability | ✅ Pass | All conditions clear |

**Overall diagnosis: Healthy — optimize and scale.** This profile demonstrates why embedded, SME-focused acquiring generates structurally superior economics: blended pricing preserves the information asymmetry premium, ISV partnerships provide low-cost distribution, and VAS creates switching cost. The risk to monitor: as SME merchants become more sophisticated (exposed to transparent pricing through fintech competitors), the blended pricing premium may compress — maintain VAS value to defend stickiness.

**Scenario C:** An emerging market new entrant with high MSC but high costs, strong SME base but concentrated partnerships and no VAS revenue.

| Parameter | Value |
|---|---|
| Average MSC rate | 220 bps |
| Blended interchange | 140 bps |
| Scheme fee rate | 15 bps |
| Processing + overhead | 35 bps |
| SME revenue share | 55% |
| Top-2 partner share | 70% |
| Digital/partner acquisition share | 45% |
| VAS revenue share | 3% |
| E-commerce volume | 35% |
| Fraud + chargeback rate | 18 bps |

**Diagnostic results:**

| Rule | Status | Detail |
|---|---|---|
| R1 — Residual Margin | ✅ Pass | 65 bps residual (220 − 140 − 15) — healthy headline margin |
| R2 — Net Profit | ✅ Pass | 30 bps net (65 − 35) — adequate but high processing cost |
| R3 — Risk Cost | ⚠️ Warn | 18 bps — elevated; needs MCC-level monitoring |
| R4 — Merchant Mix | ✅ Pass | 55% SME — profit engine engaged |
| R5 — Partner Concentration | ❌ Fail | 70% in top-2 — extreme graduation/exit risk |
| R6 — Channel Modernization | ✅ Pass | 45% digital/partner channel — modern |
| R7 — VAS Revenue | ❌ Fail | 3% VAS — competing purely on MSC |
| R8 — E-Commerce | ✅ Pass | 35% e-commerce — adequate |
| R9 — Margin Sustainability | ✅ Pass | 1 of 3 conditions met — residual is healthy |

**Overall diagnosis: Caution — structural weakness detected.** The emerging market entrant demonstrates a common trap: high headline MSC creates the illusion of health, but two structural vulnerabilities undermine it. First, 70% partner concentration means a single PayFac graduation could eliminate the majority of volume within 12–18 months. Second, 3% VAS means zero differentiation — when MSC inevitably compresses as the market matures, there is no margin buffer. The priority sequence: (1) diversify the partner portfolio by recruiting mid-size ISVs across multiple verticals, (2) build VAS capability (DCC is immediately monetizable in cross-border-heavy emerging markets), (3) monitor fraud costs as the portfolio scales.

---

## What This Demonstrates

This diagnostic operationalizes the central strategic question facing every acquiring business: not "how much volume do we process?" but "where is the profit, and is the structure that generates it defensible?" The nine rules deliberately separate economics (Rules 1–3), distribution (Rules 4–6), and strategic positioning (Rules 7–9) because the most common failure mode in acquiring strategy is a viable P&L built on an obsolete distribution model — or a modern distribution model that leaks all margin through processing inefficiency. The framework is informed by publicly available industry benchmarks and the author's experience across Asia Pacific, Middle East, and European payment markets.

---

*Built by Nick Chang · Strategy consultant · Payments & financial services · [Logica](https://nickchang.dev/)*
