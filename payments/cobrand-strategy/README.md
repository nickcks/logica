---
Title: README
Created: 2026-03-20
Modified: 2026-03-21
---
# Co-Brand Partnership Decision System

**Part of the Logica Payments series** · [Issuer P&L Diagnostic](../issuer-economics/) · Co-Brand Strategy · Portfolio Conversion · Acquiring Playbook · SME Payments

---

## Problem

A co-brand credit card partnership is not a product launch. It is a multi-party contract that binds an issuer, a partner brand, and a network into a shared P&L — with misaligned incentives baked in from day one. The partner wants acquisition revenue and customer data. The issuer wants incremental volume and NII. The network wants spend. When the deal is designed well, co-brand cardholders spend 2.5–3x more at the partner than non-cardholders, and the partner's acquisition channel reduces the issuer's cost per new customer significantly. When the deal is designed poorly, the issuer ends up running a high-cost rewards program that cannibalizes its own premium cards, funds the partner's loyalty liability, and surrenders customer data rights at contract expiry.

Most issuer evaluations of co-brand opportunities fail at the same points: they model volume without stress-testing reward cost sustainability; they select revenue sharing structures that look attractive in a base case but are loss-making under realistic attrition; and they sign contracts that give the partner brand leverage over the cardholder relationship long after acquisition. This tool makes those failure modes explicit — before the deal is signed.

---

## Framework

### The Three-Party Value Exchange

Every co-brand is a negotiation between three parties with different assets, different risk tolerances, and different definitions of "success."

| Party | What they contribute | What they want | Primary risk |
|---|---|---|---|
| **Issuer** | Capital, credit underwriting, infrastructure | Incremental spend volume, NII, portfolio diversification | Reward cost exceeds economics; partner captures all value |
| **Partner** | Traffic, brand equity, loyalty members | Revenue stream, CLV uplift, customer data access | Issuer fails to activate; card becomes margin drag |
| **Network** | Global acceptance, scheme benefits, marketing | Spend volume, scheme fees, market share | Either party exits at renewal |

The issuer enters this structure from the weakest negotiating position when the partner brand has genuine demand: customers want the card because of the partner, not the bank. This asymmetry is structural — and it determines which party captures the economics.

---

### Six Revenue Sharing Models

The deal economics are defined by which model is chosen and at what rates. Models vary significantly in issuer risk exposure, partner upside, and structural complexity.

| Model | How it works | Issuer risk | Partner upside | Best fit |
|---|---|---|---|---|
| **Bounty / CPA** | Issuer pays fixed fee per approved card via partner channel | Low | Low | New launch, unproven partner traffic |
| **Points Purchase** | Issuer buys loyalty points from partner at wholesale; distributes to cardholders | Low–Med | Medium | Airline / hotel programs with high breakage |
| **Interchange Share** | Issuer splits interchange revenue with partner | Medium | Medium | Balanced, mature partnership |
| **Revenue Share** | Issuer splits all card fee revenues (interchange + annual fees) | High | High | Scaled programs with 3+ year track record |
| **Profit Share** | Issuer and partner split net profit; partner also shares costs | High | Variable | JV-style; partner behaves as quasi-issuer |
| **Hybrid** | Combination of above (e.g., bounty + points purchase + interchange floor) | Variable | Variable | Tailored deals with multiple value streams |

**Key insight:** Points purchase enables *breakage arbitrage* — the issuer purchases points at wholesale, but 20–35% of points are typically never redeemed, creating a structural cost buffer. Revenue share and profit share eliminate this buffer; partner economics become directly linked to issuer P&L performance.

---

### Three Engagement Types

Co-brand consulting engagements fall into three distinct modes with different analytical starting points.

| Engagement | Trigger | Primary question | Key output |
|---|---|---|---|
| **New Launch** | Partner or issuer initiates; no existing program | Does this deal generate positive NPV at achievable volume? | 3-year business case + contract negotiation levers |
| **Renewal / Renegotiation** | Contract approaching expiry (T–18 to T–6 months) | Are current economics sustainable? What leverage exists? | Revenue share re-pricing + CVP refresh roadmap |
| **Turnaround / Optimization** | Underperformance vs. targets | Where is value leaking, and is it recoverable? | Root-cause diagnostic + 12-month intervention plan |

---

### CVP Assessment: Six Dimensions

A co-brand CVP fails when it is defined as a feature list rather than a behavioral promise. A strong CVP can be stated in one sentence: *who* the card is for, in *what context*, delivering *what specific outcome*. Every benefit must trace back to a behavior the target segment will actually change.

| Dimension | Diagnostic question | Pass threshold |
|---|---|---|
| **Target** | Is the primary segment named and specific enough to design for? | A persona with identifiable spend behavior (e.g., "frequent flyer, 4+ trips/year, income > $80K") |
| **Context** | Can you name 1–3 key use cases where this card wins? | At least one scenario with high frequency *and* high spend |
| **Promise** | Can the CVP be stated in one sentence? | Yes — if it takes a paragraph, it has no CVP |
| **Proof** | Are benefit mechanics defined and costed? | Every major benefit has a delivery mechanism and unit cost |
| **Economics** | Is reward cost sustainable at target revolving rate? | Reward cost < blended interchange + NII contribution |
| **Differentiation** | Is there at least one exclusive or structurally hard-to-copy benefit? | Yes — if all benefits are replicable, the program competes on reward rate alone |

---

## Decision Rules

Eight rules that determine whether a co-brand creates or destroys value. Each rule is a specific failure mode drawn from issuer program diagnostics.

> **On thresholds:** Values below are portfolio-level heuristics informed by publicly available industry benchmarks and the author's experience across Asia Pacific, Middle East, and European payment markets. They serve as triage indicators, not underwriting standards — specific market conditions (regulatory regime, partner tier, portfolio maturity) will shift the applicable ranges.



**Rule 1 — Partner Scale & Customer Overlap**  
IF (partner active loyalty base × customer overlap %) < 75,000 addressable prospects  
THEN: WARN — insufficient audience to reach unit economics at scale  
ACTION: Require partner to demonstrate acquisition funnel conversion quality, not just member count; consider a time-boxed pilot (24 months) with volume ramp triggers before committing to full program economics.

**Rule 2 — Reward Cost vs. Interchange**  
IF blended reward cost rate ≥ blended domestic interchange yield across all card spend  
THEN: FAIL — structurally loss-making on every transaction before fixed overhead  
ACTION: Reprice rewards downward; shift from cashback to points program to recover breakage (typically 20–30% of issued points); or negotiate an interchange floor with the network as a condition of the co-brand agreement. Note: the tool uses blended portfolio interchange as a proxy — MCC-level interchange on partner-channel spend may differ and should be stress-tested in the full business case.

**Rule 3 — Revenue Share Model Viability**  
IF revenue-sharing model selected (interchange share, revenue share, profit share, or hybrid) AND partner revenue share rate > 35% (indicative ceiling; above this level, issuer margin is typically insufficient to cover funding cost, credit losses, and overhead across most market structures)  
THEN: FAIL — issuer retains insufficient margin to cover funding cost, credit losses, and operating overhead  
ACTION: Restructure to bounty + points purchase for new launches; if partner demands revenue share, cap at 25–30% with performance-linked escalators tied to spend targets and activation milestones.

**Rule 4 — CVP Clarity**  
IF the CVP cannot be stated in one sentence describing the target segment and primary use case  
THEN: WARN — product will compete on reward rate alone, driving cost escalation without behavioral differentiation  
ACTION: Before finalizing product design, run a segment-level jobs-to-be-done analysis; every benefit must be traceable to a specific behavioral outcome the target segment will act on.

*CVP score calibration — use these examples to self-assess:*
- Score 1 (Feature list): "Earn points on purchases"
- Score 2 (Category): "A travel card with lounge access"
- Score 3 (Segment): "For frequent travelers who want lounge access and hotel rewards"
- Score 4 (One-sentence): "For frequent flyers: earn miles on every purchase and redeem for flights and upgrades"
- Score 5 (Behavioral): "For travelers flying 4+ times a year: this card replaces your airline loyalty app as the fastest path to a free flight"

**Rule 5 — Portfolio Cannibalization**  
IF projected partner-channel spend as share of total card spend < 15%  
THEN: WARN — co-brand is likely to cannibalize existing premium card spend rather than generate net new volume for the issuer  
ACTION: Model cannibalization explicitly: if incremental spend from partner acquisition channel does not exceed projected margin loss on existing portfolio, the business case is structurally negative regardless of gross volume.

**Rule 6 — Acquisition Cost Payback**  
IF acquisition cost per card (all-in: bounty + onboarding + card production) > (annual interchange revenue + annual fee revenue) × 2  
THEN: WARN — payback period exceeds 2 years; at indicative attrition rates of 10–15% annually, a meaningful share of cards will lapse before the acquisition investment is recovered  
ACTION: Either reduce acquisition cost, increase annual fee, or require partner to co-fund acquisition via CPA model; alternatively, negotiate a higher partner-channel spend allocation to increase interchange yield per card.

**Rule 7 — Contract Term and Data Rights**  
IF contract term < 3 years OR no explicit cardholder data ownership and re-marketing rights clause  
THEN: FAIL — issuer builds the cardholder relationship and credit history but cannot leverage the asset after contract expiry; at under 3 years, acquisition investment cannot be amortized before renewal leverage shifts entirely to the partner  
IF contract term 3–4 years OR data rights partial  
THEN: WARN — minimum viable but fragile; renegotiate before signing  
ACTION: Minimum 5-year initial term with 2-year rolling renewal option; contract must specify that cardholder data remains issuer property with minimum 12-month post-expiry retention rights; partner cannot solicit cardholders for competing products for 24 months post-termination.

**Rule 8 — Revolving Rate Adequacy**  
IF projected revolving rate < 15% (transactor-heavy portfolio)  
THEN: WARN — NII contribution is minimal; P&L is dependent on annual fee renewals and interchange alone  
ACTION: Validate that (annual fee revenue + interchange revenue) per active card covers all-in cost of servicing, rewards, and overhead at breakeven; if not, the program requires either premium fee tier pricing or a higher-margin reward cost structure to be viable.

---

## Worked Example

**Scenario:** A regional Asia Pacific issuer evaluating a co-brand with a global mid-tier hotel loyalty program operating in a regulated, low-interchange environment.

**Deal parameters:**

| Parameter | Value |
|---|---|
| Partner loyalty base (active) | 2.8M members in market |
| Estimated customer overlap | 15% → ~420K addressable prospects |
| Revenue sharing model | Points purchase + acquisition bounty ($55/card) |
| Wholesale point cost | $0.012 per point |
| Annual spend per active card | $4,800 |
| Partner-channel spend share | 22% |
| Reward structure | 3× points at partner hotels; 1× elsewhere |
| Blended reward cost | ~0.65% of total spend |
| Domestic interchange rate | ~0.9% (indicative; regulated low-interchange environment) |
| Revolving rate | 12% |
| Annual card fee | $120 |
| Contract term | 5 years, data rights included |
| Year 1 projected cards | 28,000 |

**Diagnostic results:**

| Rule | Status | Detail |
|---|---|---|
| R1 — Partner Scale | ✅ Pass | 420K addressable prospects >> 75K threshold; quality of loyalty tier matters |
| R2 — Reward Cost | ⚠️ Watch | 0.65% reward cost vs 0.9% interchange — 25 bps spread; thin but positive |
| R3 — Revenue Model | ✅ Pass | Points purchase model; not revenue share |
| R4 — CVP Clarity | ✅ Pass | "For loyalty program members who travel frequently: earn hotel rewards on every purchase — the card becomes the everyday spend vehicle for the partner's core customer" — one sentence, specific segment |
| R5 — Cannibalization | ✅ Pass | 22% partner-channel spend; net new acquisition from hotel loyalty base |
| R6 — Payback | ✅ Pass | $55 acquisition cost ÷ ($120 fee + ~$43 interchange) ≈ 4 months payback |
| R7 — Contract Rights | ✅ Pass | 5-year term, cardholder data ownership clause included |
| R8 — Revolving Rate | ⚠️ Watch | 12% revolving — Japan transactor pattern; NII thin |

**Overall diagnosis:** Viable — proceed with negotiation. Two structural risks to manage: (1) reward cost spread is thin at 25 bps — a 0.1% increase in reward liability wipes this margin, so breakage assumptions must be stress-tested against actual point redemption history from the partner's loyalty program; (2) low revolving rate means annual fee renewal is the primary P&L lever after Year 1 — model fee attrition carefully and build a targeted retention campaign for Year 2–3.

---

## What This Demonstrates

This framework operationalizes a decision that most issuers make intuitively — "is this a good co-brand deal?" — into a repeatable diagnostic system with specific, falsifiable thresholds. The eight rules are not general principles; they are informed by publicly available industry benchmarks and the author's experience across Asia Pacific, Middle East, and European payment markets. The framework deliberately separates *deal economics* (Rules 1–3, 6), *product design quality* (Rules 4–5), and *contract structure* (Rules 7–8) — because the most common failure mode is a structurally sound economic model built on a weak CVP, or a strong CVP attached to a contract that transfers long-term value to the partner. Passing all three layers is the minimum requirement for a viable co-brand.

---

*Built by Nick Chang · Strategy consultant, Mastercard Data & Services · [Logica](https://nickcks.github.io/logica/)*
