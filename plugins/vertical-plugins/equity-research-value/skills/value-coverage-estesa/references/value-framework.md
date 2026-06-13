# Value Framework Reference

This document defines the philosophy, scoring criteria, and formulas used by the `value-coverage` skill. Read this before generating any value coverage report.

---

## 1. Core Philosophy: Quality Before Price

A value-investing initiating coverage is not a sell-side note repackaged. The order of operations is reversed:

1. **First**, decide whether the business is worth owning at *any* reasonable price.
2. **Only then**, calculate at what price you'd own it.

If the business fails the quality test, the valuation exercise is pointless. A bad business at a cheap price is still a bad business; the price will follow the deterioration.

Conversely, a high-quality business at a fair price (no margin of safety) is a watchlist candidate, not an automatic skip. Wonderful businesses rarely trade at deep discounts; sometimes a fair price + time + reinvestment is the deal.

**The default mistake to avoid**: treating valuation as the primary question. Valuation is the *last* step, not the first.

---

## 2. The Six Quality Dimensions

Each scored 1-5. Aggregate to /30. Thresholds:

- **24-30**: Exceptional business. Worth deep work. Candidate for long-term ownership.
- **18-23**: Solid business. Worth analysis but be more demanding on price.
- **12-17**: Mediocre. Only worth attention at significant MOS, and even then with reduced position size.
- **Below 12**: Skip. The report ends here with "not a candidate".

### Dimension 1 — Moat: Type, Width, Durability (1-5)

What protects this business from competition over the next 10 years?

Moat types (one or more):
- **Intangible assets**: brand, patent, regulatory license, network of trust
- **Switching costs**: financial, procedural, relational lock-in
- **Network effects**: value of the platform grows with users
- **Cost advantages**: scale, location, proprietary process, lower input cost
- **Efficient scale**: market structurally too small for more than X players

Scoring rubric:
- **5**: Wide moat, multiple sources, demonstrably durable through cycles, expanding
- **4**: Wide moat, single source but very strong, durable
- **3**: Narrow moat, defensible for 5-7 years, no obvious widening
- **2**: Weak moat or eroding; competitive pressure visible in margins
- **1**: No moat; commodity-like economics

### Dimension 2 — ROIC: Level and Sustainability (1-5)

Return on invested capital is the cleanest single number for business quality.

Calculation: `ROIC = NOPAT / (Total Debt + Equity − Cash)`

Or alternatively: `ROIC = (Operating Income × (1 − Tax Rate)) / (Working Capital + Net PP&E + Net Intangibles)`

Scoring rubric (use 10-year average, not single year):
- **5**: ROIC consistently > 20%, low variance, > 2x WACC
- **4**: ROIC 15-20%, stable, > 1.5x WACC
- **3**: ROIC 10-15%, > WACC but margin is narrowing or volatile
- **2**: ROIC 5-10%, barely covering WACC
- **1**: ROIC < cost of capital — destroying value

**Critical**: also assess sustainability. A 30% ROIC declining 200bps/year for 5 years scores worse than a stable 18%.

### Dimension 3 — Reinvestment Runway (1-5)

Can the company put incremental capital to work at high returns? This is what separates a compounder from a cash cow.

Compounding rate ≈ Reinvestment Rate × ROIC

Scoring rubric:
- **5**: Large addressable market, clear reinvestment opportunities at incremental ROIC ≥ historical ROIC, multi-decade runway
- **4**: Good runway, incremental ROIC slightly below historical, 10+ years visible
- **3**: Limited runway; mature business returning most cash via dividends/buybacks
- **2**: No organic runway; growth requires expensive M&A with mediocre returns
- **1**: Negative reinvestment economics; capital should be returned, not reinvested

### Dimension 4 — Capital Intensity & FCF Conversion (1-5)

How much of accounting profit becomes real cash?

Key ratios:
- Capex / Revenue (lower is better, all else equal)
- FCF / Net Income (closer to 1.0 is better; sustainably > 1.0 is best)
- Working capital / Revenue trend

Scoring rubric:
- **5**: Asset-light, FCF/NI consistently > 1.0, capex < 5% of revenue
- **4**: FCF/NI 0.8-1.0, manageable capex
- **3**: FCF/NI 0.6-0.8, moderate capital intensity
- **2**: FCF/NI 0.4-0.6, capital-heavy business
- **1**: FCF/NI persistently < 0.4 or negative; accounting earnings don't translate to cash

### Dimension 5 — Management & Capital Allocation (1-5)

Track record matters more than résumé.

Look at:
- Insider ownership (skin in the game — meaningful at > 3% for non-founders, > 10% is strong)
- Tenure (CEO/CFO continuity through cycles)
- Capital allocation track record: 10-year decomposition of where cash went and the ROI on those decisions
- M&A history: prices paid (multiples vs business quality), integration outcomes
- Buyback discipline: did they buy back when shares were cheap, or only when price was high?
- Compensation structure: short-term EPS vs long-term per-share value creation
- Shareholder letters / earnings call quality: candor, owner-orientation, error acknowledgment

Scoring rubric:
- **5**: Founder-led or owner-operator culture, exceptional capital allocation, demonstrably honest communication
- **4**: Strong track record, aligned incentives, sensible capital decisions
- **3**: Competent but unremarkable
- **2**: Mixed track record; some value-destructive M&A; misaligned comp
- **1**: Empire-building, dilutive issuance at low prices, poor communication, or worse

### Dimension 6 — Stress Resilience (1-5)

How does the business behave when things go wrong?

Test against:
- 2008-2009 GFC: revenue decline, margin compression, FCF preservation
- 2020 COVID: same
- 2022 inflation spike: pricing power, margin defense
- Current balance sheet: net debt / EBITDA, interest coverage, debt maturity wall
- Customer concentration: top 10 customers as % of revenue
- Cyclicality of demand

Scoring rubric:
- **5**: Counter-cyclical or recession-resistant; net cash or low leverage; diversified customer base
- **4**: Modest cyclicality; comfortable leverage; some customer concentration but manageable
- **3**: Moderately cyclical; debt manageable but not low
- **2**: Highly cyclical; meaningful leverage; concentration risk visible
- **1**: Bet-the-company exposures (single customer, single contract, refinancing wall, leverage > 4x)

---

## 3. Valuation Triangulation: Four Methods

The point estimate of fair value is a weighted average of four methods. Each method has assumptions and known weaknesses; using only one is a mistake.

### Method 1: DCF (Discounted Cash Flow)

**Inputs**:
- 10-year explicit FCF forecast
- Year-11 terminal value (Gordon growth or exit multiple)
- WACC

**Build**:
```
FCF_t = Revenue_t × FCF_margin_t
PV(FCF_t) = FCF_t / (1 + WACC)^t
TV_year10 = FCF_11 / (WACC − g)   [Gordon growth method]
   or:    = EBIT_year10 × terminal multiple
PV(TV) = TV / (1 + WACC)^10
Enterprise Value = Σ PV(FCF) + PV(TV)
Equity Value = EV − Net Debt + Cash
Per-Share Value = Equity Value / Diluted Shares
```

**Rules**:
- Terminal growth rate `g` should never exceed long-run GDP growth (typically 2.5%)
- WACC should be defensible: state risk-free rate source, equity risk premium, beta, debt cost, tax rate, debt/equity weights
- Sensitivity matrix is mandatory: WACC (±200bps) × terminal growth (±100bps)
- Reject the DCF if > 70% of value sits in the terminal — the forecast is too short

### Method 2: Multiples (Historical and Peer)

Compute current multiples and compare against:
- Company's own 5-year average
- Company's own 10-year average
- Peer group median
- Sector / industry median

Multiples to use (pick the ones relevant to the business):
- **P/E**: useful for stable mature businesses with clean accounting
- **EV/EBIT**: better than P/E for cross-capital-structure comparison
- **EV/EBITDA**: industry standard but ignores capital intensity — flag when D&A is meaningful
- **P/FCF**: arguably the cleanest, especially for asset-light businesses
- **EV/Sales**: only when margins are not yet stable (early-stage, post-cyclical recovery)

Output: a fair-value-implied price using each multiple × the relevant 12-month-forward earnings/cash flow metric, then weighted to a single multiples-based fair value.

### Method 3: FAST Graphs Lens

Three sub-calculations:

**3a. Blended P/E vs 15-year history**
- Compute current blended P/E (current price / blended EPS where blended = 50% TTM + 50% NTM, or per FAST Graphs convention)
- Compare to 15-year average blended P/E
- Apply the historical multiple to next-12-month EPS → implied fair value

**3b. Normalized Earnings Yield**
- E/P at current price
- Compare to long-term 10y Treasury yield
- The premium/discount tells you if the equity is cheap or expensive on an absolute yield basis

**3c. "Fair" P/E based on growth rate (Peter Lynch / FAST Graphs heuristic)**
- For companies growing earnings 0-5%: fair P/E ≈ 12-15
- For companies growing 5-10%: fair P/E ≈ 15-18
- For companies growing 10-15%: fair P/E ≈ growth rate (PEG ≈ 1.0), so 15-20
- For companies growing 15%+: cap fair P/E at ~22-25 regardless of growth

Apply fair P/E × NTM EPS → implied fair value.

Triangulate 3a + 3b + 3c into a single FAST-Graphs-style fair value.

### Method 4: Reverse DCF

Take the current stock price as given. Solve for the implied growth rate (or implied margin, or implied terminal value) the market is pricing in.

Then ask: is this implied set of assumptions plausible? Conservative? Aggressive?

This is a sanity check, not a fair-value generator on its own. But it tells you what the market consensus believes, and whether you're betting on the consensus being wrong (and in which direction).

### Weighting to a Single Fair Value

The final point estimate is a weighted average. Default weights:

- DCF: 40%
- Multiples: 30%
- FAST Graphs: 20%
- Reverse DCF: 10% (used as a check; rarely the dominant input)

Adjust weights based on the business:
- **High-growth or high-uncertainty business** → reduce DCF weight (forecast unreliable), increase Multiples and FAST Graphs
- **Mature, stable, predictable business** → DCF can go to 50%, FAST Graphs to 25%
- **Cyclical business** → use normalized earnings (mid-cycle), reduce Multiples weight if at extreme of cycle
- **Asset-light fee compounder with high ROIC** → DCF and FAST Graphs roughly equal weight; multiples often misleading

State the weighting explicitly in the report.

---

## 4. Margin of Safety: Formula, Rating & Price Levels

```
MOS = (Fair Value − Current Price) / Fair Value
```

Always compute as a percentage. Map to rating and decision:

| MOS | Rating | Decision | Action |
|-----|--------|----------|--------|
| > 25% | Strong Buy | Full position | Build to target weight |
| 10-25% | Accumulate | Scale in | DCA over months; partial position |
| 0-10% | Hold / Watchlist | Wait | Watchlist; alert on -10% price moves |
| < 0% | Avoid / Reduce | Avoid | If owned, evaluate trim or hold |

The rating is the decision-matrix outcome surfaced as a label. It is mechanically
derived from the margin of safety — it is not an independent judgment call layered on top.

**Price levels** — three operational numbers derived from the single fair value estimate:

```
Price target (primary)  = Fair Value                  (the point estimate of intrinsic value)
Buy-below price         = Fair Value × 0.75            (the price delivering a 25% MOS)
Trim-above price        = Fair Value × 1.20            (default; valuation risk warrants trimming)
```

The trim-above multiplier (default 1.20) may be widened with explicit rationale for
exceptionally high-quality compounders, where the market rarely offers them at fair
value and a modest premium is defensible for a long-term holder. Always state the
multiplier used and why.

Do NOT produce a speculative 12-month price target based on a target forward multiple.
The "price target" in this framework is intrinsic value; the buy-below and trim-above
levels are operational thresholds, not short-term price forecasts.

**Important**: MOS thresholds apply only after the quality score is ≥ 18/30. For
lower-quality businesses, demand more MOS (e.g., >40% for a quality score of 14), which
also shifts the rating bands — a 20% MOS on a 14/30 business is still only a Hold.

---

## 5. Bull / Base / Bear Scenario Rules

Three scenarios. Probabilities must sum to 100%. No 50/50/0 splits — there is always a tail risk and a positive surprise.

Default starting probabilities: 25% / 50% / 25%. Adjust based on:
- Business quality (higher quality → fatter base case, thinner bear)
- Forecast certainty (lower → wider tails)
- Cyclical position (late cycle → fatter bear; early cycle → fatter bull)

For each scenario, compute the 10-year IRR from current price to projected exit value. Probability-weight to get expected IRR.

A useful sanity check: if probability-weighted IRR < 8% (long-run equity return), the position is not interesting regardless of MOS.

---

## 6. Common Errors to Avoid

1. **Anchoring on current price**. Don't reverse-engineer a fair value that justifies the current quote. Build fair value bottom-up.

2. **Ignoring the base rate**. Most companies do not compound at 15%+ for a decade. Be suspicious of forecasts that imply they will.

3. **Treating the DCF as truth**. The DCF is a discipline, not an oracle. Garbage-in, garbage-out.

4. **Overweighting recent quarters**. The thesis should not hinge on the last earnings beat. Use 10-year averages and trajectories.

5. **Ignoring share count drift**. Buybacks at high prices destroy value. Issuance dilutes. Always model per-share value, not enterprise value.

6. **Forecasting margin expansion without a mechanism**. If you forecast 200bps of margin expansion, name the operating leverage source.

7. **Underestimating capital allocation as a value driver**. Over 10 years, capital allocation often matters more than operating execution. Score it accordingly.

8. **Treating analyst consensus as a benchmark to beat**. Consensus is an input, not a target. The point of the work is to be right, not to be different.

9. **Confusing a great company with a great investment**. Price matters. Always. Even for the best businesses.

10. **Confirmation bias from selective transcript reading**. Read the questions, not just the answers. Read the bear case. Read what management *didn't* say.

---

## 7. What This Framework Will NOT Do

- It will not produce a speculative 12-month price target based on a target forward
  multiple. (It does produce a price target — but that target is intrinsic value.)
- It will not produce an independent BUY/HOLD/SELL rating divorced from valuation.
  (It does produce a rating — but the rating is mechanically the decision-matrix
  outcome: Strong Buy / Accumulate / Hold / Avoid, derived from the margin of safety.)
- It will not optimize for short-term performance.
- It will not chase momentum or "story stocks" without quality.
- It will not assume mean reversion in either direction without a thesis for why.

The output is: a point estimate of fair value (the price target), buy-below and
trim-above price levels, a margin-of-safety percentage, a rating and a categorical
decision (Strong Buy/full position, Accumulate/scale in, Hold/wait, Avoid), all
supported by a quality score and a probability-weighted IRR.
