# Marketplace Launch Readiness Diagnostic

## Problem

Platform companies face a recurring high-stakes decision: whether to launch a new vertical in a specific market. A ride-hailing platform evaluating two-wheel taxis in a dense Asian metropolis, a food delivery platform considering grocery delivery in a mid-tier city, or a super-app weighing elderly transport as a new service line — the underlying decision structure is the same.

Most platforms make this call using a mix of executive intuition and top-line TAM estimates. The result: verticals launched into markets where supply can't be recruited profitably, where regulatory barriers consume years of stakeholder management before a single trip is completed, or where unit economics require permanent subsidies because demand density never reaches the liquidity threshold.

The cost of getting it wrong is not just the failed vertical — it's the opportunity cost of platform resources, engineering bandwidth, and regulatory capital that could have been deployed to a viable vertical instead.

This tool structures the launch decision across three layers: market viability (is there enough demand?), supply-side economics (can you build and retain supply profitably?), and execution readiness (regulatory, competitive, and platform leverage). It converts a complex, multi-stakeholder judgment call into a structured diagnostic with explicit pass/warn/fail thresholds — making the hidden assumptions visible and debatable.

What makes this different from a market sizing exercise: Market sizing tells you the prize is big. This tool tells you whether you can actually capture it — by stress-testing the conditions that determine whether the platform can achieve minimum viable liquidity in this specific vertical × market combination.

## Framework

The diagnostic is structured around three layers, each addressing a different question:

**Layer 1 — Market Viability: Is there demand worth pursuing?**

| Factor | What it measures |
|--------|-----------------|
| Addressable Population | Target user base in this market × vertical |
| Demand Density | Concentration of potential demand in serviceable geography — sparse demand = high deadhead = poor unit economics |
| Alternative Saturation | How well-served is this need by existing solutions? |

**Layer 2 — Supply & Unit Economics: Can you build it profitably?**

| Factor | What it measures |
|--------|-----------------|
| Supply Pool Availability | Size and accessibility of potential providers who could join the platform |
| Provider Economics | After platform take rate, can providers earn enough vs. their opportunity cost to stay? |
| Path to Liquidity | How quickly can the platform reach minimum viable liquidity? |

**Layer 3 — Execution Readiness: Can you actually do it?**

| Factor | What it measures |
|--------|-----------------|
| Regulatory Clarity | Is the legal/regulatory framework clear, emerging, or hostile? |
| Platform Leverage | Can the platform reuse existing infrastructure, or is this a ground-up build? |
| Competitive Defensibility | Once launched, how defensible is this position? |

## Decision Rules

> **Disclaimer:** These rules use indicative thresholds informed by publicly available marketplace economics research (a16z, Andrew Chen, NFX) and the author's analytical methodology. Actual thresholds vary significantly by market, vertical, and business model. Use as a structured starting point for analysis, not as definitive criteria.

### Layer 1 — Market Viability (Rules 1–3)

**R1: Market Scale Floor**

Addressable population (thousands) in the target market × vertical.

- **PASS:** ≥ 150K — sufficient scale for dedicated vertical operations
- **WARN:** 50K–149K — marginal scale; may require bundling with adjacent verticals to justify investment
- **FAIL:** < 50K — below minimum viable scale for standalone vertical

**R2: Demand Density Threshold**

Demand density score (1–5 scale): 1 = sparse/rural, 3 = moderate urban, 5 = hyper-dense core.

- **PASS:** > 2.5 — density supports on-demand matching economics
- **WARN:** 1.5 < density ≤ 2.5 — low density; requires zone-based launch to concentrate supply
- **FAIL:** ≤ 1.5 — demand too sparse for on-demand models; evaluate scheduled/batch alternatives

**R3: Displacement Difficulty**

Alternative solution coverage (%) — share of target use cases adequately served by existing solutions.

- **PASS:** ≤ 65% — meaningful unmet demand exists
- **WARN:** 65% < coverage ≤ 85% — well-served market; need clear differentiation to win share
- **FAIL:** > 85% — market fully served; differentiation must be extreme to justify entry

### Layer 2 — Supply & Unit Economics (Rules 4–6)

**R4: Supply Sufficiency**

Available supply pool (thousands of potential providers).

- **PASS:** ≥ 2K providers — sufficient for minimum viable liquidity
- **WARN:** 0.5K–1.9K — thin supply; requires aggressive recruitment and guaranteed earnings
- **FAIL:** < 0.5K — critical shortage; cannot reach liquidity without recruitment breakthrough

**R5: Provider Economics Viability**

Provider earnings vs. opportunity cost (ratio). Platform earnings ÷ best local alternative.

- **PASS:** ≥ 1.0 — providers earn at least as much as alternatives; retention is sustainable
- **WARN:** 0.8–0.99 — marginal economics; supply retention at risk from competitive alternatives
- **FAIL:** < 0.8 — earnings structurally below alternatives; supply will not retain without permanent subsidies

**R6: Liquidity Timeline**

Estimated months to minimum viable liquidity.

- **PASS:** ≤ 12 months — manageable runway; standard launch planning applies
- **WARN:** 13–24 months — extended timeline; requires patient capital and phased milestones
- **FAIL:** > 24 months — excessive runway; burn will likely exhaust budget before flywheel engages

### Layer 3 — Execution Readiness (Rules 7–9)

**R7: Regulatory Risk**

Composite of regulatory status and government partnership requirements.

- **FAIL:** Regulatory environment is hostile — active legal/enforcement barriers regardless of other factors
- **FAIL:** Regulatory environment is restrictive AND government partnership is blocked — structural blocker
- **WARN:** Regulatory environment is restrictive AND government partnership is required — compliance requires active engagement; timeline and outcome uncertain
- **WARN:** Regulatory framework is still emerging — first-mover advantage possible but rules may shift
- **PASS:** Clear or manageable regulatory environment

**R8: Platform Leverage**

Platform infrastructure reuse (%) — share of existing stack reusable for this vertical.

- **PASS:** ≥ 40% — meaningful leverage from existing platform; reduces launch cost and timeline
- **WARN:** 20%–39% — significant new infrastructure required; budget must reflect build complexity
- **FAIL:** < 20% — near ground-up build; investment approaches new platform launch, not vertical extension

**R9: Competitive Defensibility**

Composite of competitive position, platform leverage, and demand density. Competitive moat score (0–5) is derived from competitive timing advantage + infrastructure reuse + demand density network effects.

- **FAIL:** Late entry AND competitive moat score < 3 — market likely winner-take-most with entrenched incumbents
- **WARN:** Late entry (moat ≥ 3) — late but some structural advantage exists; requires clear wedge strategy
- **WARN:** Contested market AND infrastructure reuse < 50% — elevated execution risk without platform leverage
- **PASS:** First-mover, early entry, or contested with adequate leverage

### Diagnosis

**Four tiers:**

| Tier | Condition | Meaning |
|------|-----------|---------|
| Launch Ready | 0 fails, ≤ 1 warn | Conditions support a go decision |
| Conditional Go | 0 fails, 2–3 warns | Viable with targeted risk mitigation |
| Significant Gaps | 1 fail OR 4+ warns | Address structural barriers before committing |
| Not Ready | 2+ fails | Fundamental conditions not met |

**Special diagnoses (checked before general tier):**

| Pattern | Condition | Meaning |
|---------|-----------|---------|
| Economics Trap | R5 + R6 both fail | Provider economics AND liquidity timeline both fail — the marketplace flywheel cannot engage |
| Regulatory Blocker | R7 fail + R1 pass + R5 pass | Market and economics are viable but regulation blocks entry — purely a policy problem |
| Saturated Late | R3 + R9 both fail | Fully-served market + late entry with no structural opening |
| No Market | R1 + R2 both fail | Below scale AND below density — not a viable market for on-demand |

### Worked Examples

**Preset A — Two-Wheel Urban Mobility (Conditional Go)**

Scenario: Dense urban market with large commuter base, well-served by existing taxis and public transit, moderate regulation requiring government partnership, good platform leverage from existing ride-hailing operations.

Inputs: addressable pop 2,000K, demand density 4.5, alternative coverage 70%, supply pool 30K, earnings ratio 1.3, months to MVL 8, regulatory status restrictive, government partnership required, infrastructure reuse 70%, competitive position early.

| Rule | Input | Threshold | Result |
|------|-------|-----------|--------|
| R1: Market Scale Floor | 2,000K population | ≥ 150K | ✓ Pass |
| R2: Demand Density | 4.5 density score | > 2.5 | ✓ Pass |
| R3: Displacement Difficulty | 70% alt coverage | > 65% | ⚠ Warn — well-served market |
| R4: Supply Sufficiency | 30K providers | ≥ 2K | ✓ Pass |
| R5: Provider Economics | 1.3× earnings ratio | ≥ 1.0 | ✓ Pass |
| R6: Liquidity Timeline | 8 months to MVL | ≤ 12 | ✓ Pass |
| R7: Regulatory Risk | Restrictive + required | Restrictive + required | ⚠ Warn — government engagement required |
| R8: Platform Leverage | 70% infra reuse | ≥ 40% | ✓ Pass |
| R9: Competitive Defensibility | Early entry, moat 3.9 | Not late | ✓ Pass |

Result: 0 fails, 2 warns → **Conditional Go.** Strong market fundamentals — massive addressable population, high density, healthy provider economics, and fast path to liquidity. Two binding constraints: (1) existing alternatives serve 70% of use cases, requiring clear differentiation on speed, price, or convenience; (2) restrictive regulation requires active government partnership before launch. Both are solvable but introduce timeline uncertainty.

**Preset B — Elderly Accessibility Transport (Significant Gaps)**

Scenario: Growing addressable base from aging population, policy support likely, but thin supply pool requiring specialized vehicles/training, extended liquidity timeline, sparse demand outside urban core.

Inputs: addressable pop 800K, demand density 2.0, alternative coverage 40%, supply pool 1.5K, earnings ratio 1.1, months to MVL 18, regulatory status emerging, government partnership helpful, infrastructure reuse 45%, competitive position first-mover.

| Rule | Input | Threshold | Result |
|------|-------|-----------|--------|
| R1: Market Scale Floor | 800K population | ≥ 150K | ✓ Pass |
| R2: Demand Density | 2.0 density score | ≤ 2.5 | ⚠ Warn — low density for on-demand |
| R3: Displacement Difficulty | 40% alt coverage | ≤ 65% | ✓ Pass |
| R4: Supply Sufficiency | 1.5K providers | < 2K | ⚠ Warn — thin supply pool |
| R5: Provider Economics | 1.1× earnings ratio | ≥ 1.0 | ✓ Pass |
| R6: Liquidity Timeline | 18 months to MVL | > 12 | ⚠ Warn — extended timeline |
| R7: Regulatory Risk | Emerging + helpful | Emerging | ⚠ Warn — framework still forming |
| R8: Platform Leverage | 45% infra reuse | ≥ 40% | ✓ Pass |
| R9: Competitive Defensibility | First-mover, moat 3.3 | Not late | ✓ Pass |

Result: 0 fails, 4 warns → **Significant Gaps.** Promising social mission and genuine unmet need (60% uncovered), but four structural warnings converge: demand density too low for standard on-demand matching, thin supply pool requiring specialized recruitment, 18-month runway to liquidity, and emerging regulatory framework. First-mover advantage and government alignment are strong positives, but the operational model likely needs redesign — scheduled service or zone-restricted pilot rather than city-wide on-demand.

**Preset C — Shared Rides / Carpooling (Not Ready)**

Scenario: Large addressable population but hostile regulatory environment, well-served by existing alternatives, marginal provider economics, late competitive entry with no structural advantage.

Inputs: addressable pop 3,000K, demand density 3.5, alternative coverage 70%, supply pool 15K, earnings ratio 0.9, months to MVL 20, regulatory status hostile, government partnership blocking, infrastructure reuse 55%, competitive position late.

| Rule | Input | Threshold | Result |
|------|-------|-----------|--------|
| R1: Market Scale Floor | 3,000K population | ≥ 150K | ✓ Pass |
| R2: Demand Density | 3.5 density score | > 2.5 | ✓ Pass |
| R3: Displacement Difficulty | 70% alt coverage | > 65% | ⚠ Warn — well-served market |
| R4: Supply Sufficiency | 15K providers | ≥ 2K | ✓ Pass |
| R5: Provider Economics | 0.9× earnings ratio | 0.8–0.99 | ⚠ Warn — marginal earnings |
| R6: Liquidity Timeline | 20 months to MVL | > 12 | ⚠ Warn — extended timeline |
| R7: Regulatory Risk | Hostile | Hostile | ✗ Fail — active legal barriers |
| R8: Platform Leverage | 55% infra reuse | ≥ 40% | ✓ Pass |
| R9: Competitive Defensibility | Late entry, moat 1.9 | Late + moat < 3 | ✗ Fail — late with no structural advantage |

Result: 2 fails, 3 warns → **Not Ready.** Large addressable population is misleading — the fundamentals don't support launch. Two structural FAILs: (1) hostile regulation actively opposes this vertical, requiring 12+ months of policy advocacy before any operational investment; (2) late entry with low competitive moat (1.9/5) means entrenched incumbents have likely captured network effects. Even if regulation clears, marginal provider economics and well-served alternatives make this an uphill battle on every dimension.

**Preset D — New F&B Delivery Vertical (Launch Ready)**

Scenario: Platform already operates food delivery; expanding into adjacent category. High infrastructure reuse, proven demand patterns, existing supply base partially transferable, clear regulatory framework.

Inputs: addressable pop 1,500K, demand density 4.0, alternative coverage 45%, supply pool 25K, earnings ratio 1.4, months to MVL 6, regulatory status clear, government partnership none, infrastructure reuse 85%, competitive position early.

| Rule | Input | Threshold | Result |
|------|-------|-----------|--------|
| R1: Market Scale Floor | 1,500K population | ≥ 150K | ✓ Pass |
| R2: Demand Density | 4.0 density score | > 2.5 | ✓ Pass |
| R3: Displacement Difficulty | 45% alt coverage | ≤ 65% | ✓ Pass |
| R4: Supply Sufficiency | 25K providers | ≥ 2K | ✓ Pass |
| R5: Provider Economics | 1.4× earnings ratio | ≥ 1.0 | ✓ Pass |
| R6: Liquidity Timeline | 6 months to MVL | ≤ 12 | ✓ Pass |
| R7: Regulatory Risk | Clear + none | Clear | ✓ Pass |
| R8: Platform Leverage | 85% infra reuse | ≥ 40% | ✓ Pass |
| R9: Competitive Defensibility | Early entry, moat 3.6 | Not late | ✓ Pass |

Result: 0 fails, 0 warns → **Launch Ready.** This is the "easy extension" archetype — strong across all three layers. The diagnosis should clarify *why* it's easy: 85% infrastructure reuse dramatically reduces execution risk and time-to-liquidity (6 months). Existing driver base is partially transferable, clear regulation removes compliance friction, and early entry with high moat (3.6/5) provides defensible positioning. The strategic question is not *whether* to launch but *how fast* to scale.

## Cross-Domain Note

This tool applies the same Logica methodology proven across five payments industry tools to a different domain — platform economics. The diagnostic architecture is identical: decompose a complex decision into testable rules, formalize thresholds, and produce actionable diagnostics with explicit pass/warn/fail logic.

This tool is built entirely from publicly available frameworks and data — marketplace economics research (a16z, Andrew Chen, NFX), platform company earnings disclosures, and regulatory frameworks. The structural quality comes from the method, not proprietary industry knowledge. The specific metrics change; the diagnostic architecture doesn't.

## What This Demonstrates

Platform launch decisions and payment strategy decisions share the same structural DNA: multi-stakeholder systems where demand, supply, economics, and regulation interact in non-obvious ways. This tool demonstrates that the methodology — not domain-specific expertise — is the transferable asset.

Five payments tools prove domain depth. This tool proves the method transfers. Same architecture. Different domain. Same quality.

---

*Source: Public marketplace economics research (a16z, Andrew Chen, NFX), platform company earnings disclosures, regulatory frameworks, and author's analytical methodology. Indicative thresholds — not definitive benchmarks for any specific market.*
