# Vertical Market Prioritization Diagnostic

**Tool 6** — Logica · Payments

---

## Problem

An acquirer entering a new market or expanding vertical coverage faces 15–30 potential merchant segments — restaurants, healthcare, education, travel, fuel, government. Most choose targets by intuition or volume alone: "restaurants process a lot of cards, so let's start there." This systematically misallocates resources because it ignores competition intensity, acquirer readiness, and the interaction between opportunity size and execution difficulty.

The result: a high-volume vertical with entrenched competitors and unbuilt capabilities becomes a multi-year resource drain — a "Time Sink" — instead of a profitable market entry. Meanwhile, smaller verticals where the acquirer has existing banking relationships and low competition sit untouched. Those were the Quick Wins.

This tool scores merchant verticals across five factors on two axes (Opportunity vs. Effort), classifying each into one of four strategic quadrants: Quick Win, Strategic Bet, Potential Opportunity, or Time Sink. It makes the prioritization decision explicit before resources are committed.

---

## Framework

### Two axes, five factors

**Axis 1 — Opportunity** (how attractive is this vertical?)

| Factor | What it measures | Key indicator |
|--------|-----------------|---------------|
| Card Volume Scale | Total processed volume + growth trajectory | Market size viability |
| Deposits Propensity | Industry revenue scale + growth (proxy for banking cross-sell) | Revenue diversification potential |
| Competition Intensity | Market concentration × active acquirer count × targeting pressure | Competitive headroom |

**Axis 2 — Effort** (how hard is it for THIS acquirer to win?)

| Factor | What it measures | Key indicator |
|--------|-----------------|---------------|
| Acquirer Readiness | Capability fit × onboarding infrastructure | Execution feasibility |
| Cross-sell Leverage | Existing banking relationships with businesses in this vertical | Customer acquisition efficiency |

### Output: 2×2 quadrant matrix

| Quadrant | Opportunity | Effort (Ease) | Strategic action |
|----------|-------------|---------------|------------------|
| **Quick Win** | High | High (Easy) | Fast-track — dedicated vertical team, first cohort within 3 months |
| **Strategic Bet** | High | Low (Hard) | Invest in capability building (6–12 months) before committing acquisition resources |
| **Potential Opportunity** | Low | High (Easy) | Monitor — enter if resources allow after Quick Wins are captured |
| **Time Sink** | Low | Low (Hard) | Avoid — redirect resources to higher-return quadrants |

### Opportunity Score computation

The Opportunity Score (0–10) is a weighted composite: card volume contributes 30% (base scaled against a $30B saturation point, multiplied by a growth factor), deposits propensity contributes 25% (industry revenue scaled against ~$300B saturation, with revenue growth multiplier), and competition intensity contributes 45% (inverse — lower concentration and fewer targeting acquirers yield higher scores). Competition is weighted highest because even large, growing verticals deliver poor returns when fortress incumbents control the market.

### Effort Score computation

The Effort Score (0–10) is a weighted composite: capability fit contributes 40%, onboarding readiness contributes 30%, and banking overlap contributes 30% (saturating at 60%). Capability fit is weighted highest because it represents the longest-lead-time investment — banking relationships and onboarding processes can be developed in months, but fundamental capability gaps (vertical-specific VAS, compliance infrastructure, specialized servicing) require years.

---

## Decision rules

> **Disclaimer:** Thresholds are indicative and informed by publicly available industry benchmarks and the author's experience across Asia Pacific acquiring markets. They are not calibrated to any single institution or proprietary dataset. Adjust parameters to reflect your specific market context.

### Layer 1 — Opportunity assessment (Rules 1–4)

**Rule 1 — Volume Viability**
- IF card_volume < 5 AND volume_growth < 5% → WARN "Sub-scale: volume may not justify dedicated vertical team"
- IF card_volume < 3 AND volume_growth < 3% → FAIL "Below minimum viable scale for dedicated vertical investment"
- ACTION: Re-evaluate whether this vertical merits standalone targeting or should be bundled with adjacent verticals

**Rule 2 — Growth Trajectory**
- IF volume_growth < 3% AND revenue_growth < 3% → WARN "Mature/declining vertical — limited organic growth"
- IF volume_growth <= 0% → FAIL "Contracting vertical — entry timing is wrong"
- ACTION: Assess whether share capture (vs. growth riding) is feasible given competition intensity

**Rule 3 — Competition Fortress**
- IF top2_share > 70% AND targeting_count > 5 → FAIL "Fortress vertical — dominant incumbents + aggressive targeting = no room"
- IF top2_share > 55% AND num_acquirers > 8 → WARN "Crowded vertical — differentiation required for entry"
- ACTION: Identify unserved sub-segments within the vertical, or consider alternative entry angles (vertical SaaS partnership, niche product)

**Rule 4 — Deposits & Banking Upside**
- IF industry_revenue < 50 AND banking_overlap < 10% → WARN "Low banking upside — acquiring stand-alone ROI must justify entry"
- ACTION: If acquiring margin alone is thin, cross-sell deposits/lending to justify customer acquisition cost

### Layer 2 — Effort assessment (Rules 5–7)

**Rule 5 — Capability Readiness**
- IF capability_fit < 2 → FAIL "Critical capability gaps — cannot serve this vertical without significant investment"
- IF capability_fit < 3 → WARN "Below table-stakes — need 6–12 month capability build before serious market entry"
- ACTION: Map specific capability gaps (onboarding, servicing, vertical-specific VAS) and estimate build timeline

**Rule 6 — Onboarding Fit**
- IF onboarding_ready < 2 → FAIL "Onboarding infrastructure not ready — merchants will churn during setup"
- IF onboarding_ready < 3 → WARN "Onboarding friction will slow merchant acquisition velocity"
- ACTION: Prioritize onboarding process optimization for this vertical's specific requirements (compliance, integration, POS type)

**Rule 7 — Cross-sell Leverage**
- IF banking_overlap < 10% → WARN "Cold start — no existing relationships to leverage for merchant acquisition"
- ACTION: Explore indirect channels (ISV partnerships, vertical-specific referrals) to substitute for direct banking relationships

### Layer 3 — Quadrant classification (Rules 8–10)

**Rule 8 — Quick Win Identification**
- IF opportunity_score ≥ 7 AND effort_score ≥ 7 AND no FAIL in Rules 1–7 → QUICK WIN
- ACTION: Fast-track with dedicated vertical team, aim for first merchant cohort within 3 months

**Rule 9 — Strategic Bet Identification**
- IF opportunity_score ≥ 7 AND effort_score < 7 AND ≤ 1 FAIL in Rules 1–7 → STRATEGIC BET
- ACTION: Build capability roadmap (6–12 months) before committing dedicated acquisition resources

**Rule 10 — Time Sink Warning**
- IF opportunity_score < 5 AND effort_score < 5 → FAIL "Time Sink — resources will be consumed without adequate return"
- IF opportunity_score < 5 AND FAIL count ≥ 2 → FAIL "Compounded risk — low opportunity + multiple execution barriers"
- ACTION: Redirect resources to Quick Wins or Strategic Bets

---

## Worked examples

### Preset 1: Southeast Asian Food & Beverage (Quick Win)

A large acquirer in Southeast Asia evaluates the F&B vertical. Card volume is $22B with 12% YoY growth — high scale and trajectory. Industry revenue is $180B growing at 8%, signaling strong deposits propensity. Competition is moderate: top-2 share at 35%, only 4 active acquirers, and 2 explicitly targeting. The acquirer has strong capability fit (4/5), existing banking relationships with 45% of merchants in this vertical, and solid onboarding readiness (4/5).

**Inputs:** card_volume: 22, volume_growth: 12, industry_revenue: 180, revenue_growth: 8, top2_share: 35, num_acquirers: 4, targeting_count: 2, capability_fit: 4, banking_overlap: 45, onboarding_ready: 4

**Rule-by-rule:**
- R1 Volume Viability: PASS (22 ≥ 5)
- R2 Growth Trajectory: PASS (12% ≥ 3%)
- R3 Competition Fortress: PASS (35% ≤ 55%, 4 ≤ 8 — open market)
- R4 Deposits & Banking Upside: PASS (180 ≥ 50)
- R5 Capability Readiness: PASS (4 ≥ 3)
- R6 Onboarding Fit: PASS (4 ≥ 3)
- R7 Cross-sell Leverage: PASS (45% ≥ 10%)
- R8 Quick Win: Opportunity score ~8.1, Effort score ~7.5, 0 FAILs → **QUICK WIN**
- R9: Not triggered (already Quick Win)
- R10: Not triggered (scores above thresholds)

**Diagnosis: Quick Win.** High opportunity + high readiness + no structural barriers. Fast-track with dedicated vertical team.

### Preset 2: Healthcare / Public Sector (Strategic Bet)

A mid-sized acquirer evaluates the healthcare vertical. Card volume is $18B with 6% growth. Industry revenue is $300B (high deposits propensity) growing at 5%. Competition is moderate-to-high: top-2 share 50%, 6 acquirers, 4 targeting. However, the acquirer's capability fit is low (2/5) — compliance complexity and specialized integration requirements. Banking overlap is 15%, and onboarding readiness is limited (2/5) due to sector-specific regulatory requirements.

**Inputs:** card_volume: 18, volume_growth: 6, industry_revenue: 300, revenue_growth: 5, top2_share: 50, num_acquirers: 6, targeting_count: 4, capability_fit: 2, banking_overlap: 15, onboarding_ready: 2

**Rule-by-rule:**
- R1 Volume Viability: PASS (18 ≥ 5)
- R2 Growth Trajectory: PASS (6% ≥ 3%)
- R3 Competition Fortress: PASS (50% ≤ 55%, 6 ≤ 8)
- R4 Deposits & Banking Upside: PASS (300 ≥ 50)
- R5 Capability Readiness: WARN (2 < 3, ≥ 2 — below table-stakes)
- R6 Onboarding Fit: WARN (2 < 3, ≥ 2 — friction will slow acquisition)
- R7 Cross-sell Leverage: PASS (15% ≥ 10%)
- R8 Quick Win: Effort score ~2.5 < 7 → not Quick Win
- R9 Strategic Bet: Opportunity score ~7.1 ≥ 7, Effort score ~2.5 < 7, 0 FAILs (≤ 1) → **STRATEGIC BET**
- R10: Not triggered (opportunity ≥ 5)

**Diagnosis: Strategic Bet.** The opportunity is real — high revenue, decent volume — but capability gaps must be closed before committing acquisition resources. Build a 6–12 month capability roadmap targeting compliance infrastructure and onboarding automation.

### Preset 3: Luxury Retail (Time Sink)

An acquirer evaluates the luxury retail vertical. Card volume is low ($4B) with minimal growth (2%). Industry revenue is $40B growing at just 1%. Competition is intense: top-2 share 75%, 8 acquirers active, 7 explicitly targeting. The acquirer has moderate capability fit (2.5/5), minimal banking overlap (5%), and limited onboarding readiness (2.5/5).

**Inputs:** card_volume: 4, volume_growth: 2, industry_revenue: 40, revenue_growth: 1, top2_share: 75, num_acquirers: 8, targeting_count: 7, capability_fit: 2.5, banking_overlap: 5, onboarding_ready: 2.5

**Rule-by-rule:**
- R1 Volume Viability: WARN (4 < 5, growth 2% < 5% — sub-scale)
- R2 Growth Trajectory: WARN (2% < 3% AND 1% < 3% — mature/declining)
- R3 Competition Fortress: FAIL (75% > 70% AND 7 > 5 — fortress vertical)
- R4 Deposits & Banking Upside: WARN (40 < 50 AND 5% < 10% — low banking upside)
- R5 Capability Readiness: WARN (2.5 < 3, ≥ 2 — below table-stakes)
- R6 Onboarding Fit: WARN (2.5 < 3, ≥ 2 — onboarding friction)
- R7 Cross-sell Leverage: WARN (5% < 10% — cold start)
- R8 Quick Win: Not triggered (multiple issues)
- R9 Strategic Bet: 1 FAIL (≤ 1) but opportunity score ~2.8 < 7 → not Strategic Bet
- R10 Time Sink: Opportunity score ~2.0 < 5 AND Effort score ~2.9 < 5 → **FAIL** (Time Sink)

**Diagnosis: Fortress Time Sink.** R3 FAIL (fortress competition) combined with opportunity score below 5 triggers the specific fortress time sink diagnosis. Entrenched competition in a low-opportunity vertical — even building capabilities would not create a viable entry angle. Redirect resources.

Fortress competition, sub-scale volume, no growth, no banking relationships. Every dimension points to resource drain. Redirect to Quick Wins.

---

## What this demonstrates

This diagnostic reflects how I approach acquiring market strategy: not as a volume-ranking exercise, but as a structural assessment of whether the opportunity–effort balance supports profitable entry. The five-factor model, dual-axis scoring, and quadrant classification mirror the analytical frameworks used in real "Where to Play" engagements across Asia Pacific markets — where the most common mistake is confusing high card volume with high attractiveness, and the most valuable insight is often that the obvious target is not the highest-return entry point.

---

*Source: Industry frameworks, public acquiring market benchmarks, author experience across Asia Pacific markets.*

*Nick Chang · Strategy consultant · Payments & financial services*
