# Task 4 — Valuation & Quality Scoring

## Goal

Convert the research (Task 1) and the financial model (Task 3) into a complete
valuation: quality score (out of 30), four-method intrinsic value triangulation,
single point estimate of fair value, MOS calculation, rating, and operational
price levels (buy-below, trim-above). Plus probability-weighted IRR via
bull/base/bear scenarios.

This task is where the conclusion of the coverage report is determined.

## Output

An Excel file at: `{TICKER}_valuation.xlsx`

The output is also summarized in markdown form at the end of execution so that
Task 5 (assembly) can directly transcribe the conclusions.

## Prerequisites

- Task 1 complete: `{TICKER}_research.md` read
- Task 3 complete: `{TICKER}_model.xlsx` read (forecast assumptions, FCF
  forecast, ROIC history all consumed)
- `references/value-framework.md` read (quality rubrics, formulas, MOS matrix,
  rating logic — this is the most framework-dependent task)
- Current stock price retrieved (web search) and stored

## Workflow

1. **Read all prerequisites.** Open Task 1 markdown + Task 3 Excel. Cache the
   forecast FCF series, the ROIC history, and the qualitative judgments from
   research.

2. **Score the 6 quality dimensions.** Per the framework, 1-5 each, with
   one-paragraph justification rooted in evidence from Tasks 1 and 2.
   Aggregate to /30.

3. **CHECK quality threshold.** If aggregate quality score < 18/30:
   - STOP the full valuation work
   - Flag this to the user
   - Skip directly to producing a brief "not a candidate for long-term holding"
     summary in this file
   - Note that downstream tasks 4 and 5 should produce shortened outputs
   - The user may override and request full valuation anyway — only proceed
     if they confirm

4. **If quality ≥ 18, execute four-method valuation triangulation.** Per the
   framework formulas. Each method goes in its own sheet.

5. **Combine to one point estimate.** Default weighting DCF 40% / Multiples 30%
   / FAST 20% / Reverse 10%. Adjust per framework rules for the business type;
   state weighting explicitly with rationale.

6. **Compute MOS, rating, and price levels.**
   - MOS = (Fair Value − Current Price) / Fair Value
   - Rating from MOS bands per framework
   - Buy-below = Fair Value × 0.75
   - Trim-above = Fair Value × 1.20 (default; widen for exceptional compounders
     with explicit rationale)

7. **Build bull / base / bear scenarios.** Per framework rules: probabilities
   sum to 100%, each scenario with 10-year IRR estimate, "what has to be true"
   one-liner. Probability-weighted expected IRR.

## Workbook Structure (8 Sheets)

### Sheet 1: Summary Dashboard
A one-page output sheet showing:
- Ticker, date, current price
- Quality score: X/30 with breakdown by dimension
- Fair value: $X (the point estimate)
- MOS: Z%
- Rating: Strong Buy / Accumulate / Hold / Avoid
- Price levels: Buy-below $X (= FV × 0.75), Trim-above $X (= FV × 1.20)
- Probability-weighted 10-year IRR
- Bull / Base / Bear scenarios summary
- Method weighting used in triangulation

This sheet is the one the user looks at most often. It must be clean and
self-explanatory.

### Sheet 2: Quality Scoring
For each of 6 dimensions (moat, ROIC, reinvestment runway, capital intensity /
FCF conversion, management, stress resilience):
- Score (1-5)
- Justification paragraph (drawn from Task 1 research)
- Supporting metrics (e.g., 10-year average ROIC from Task 3 model)
- Direction (improving / stable / weakening)
Aggregate: /30 with bands per framework (24-30 exceptional, 18-23 solid, etc.)

### Sheet 3: DCF
- 10-year explicit FCF forecast (linked from Task 3 model)
- WACC build:
  - Risk-free rate (state source — 10y Treasury yield as of report date)
  - Equity risk premium assumption
  - Beta (state source)
  - Cost of equity = RFR + Beta × ERP
  - Pre-tax cost of debt
  - After-tax cost of debt
  - Weights (debt / EV, equity / EV)
  - WACC
- Terminal value: Gordon growth (terminal g must not exceed long-run GDP, ~2.5%)
  OR exit multiple method — state which and why
- PV of explicit FCF + PV of terminal value
- Enterprise value → equity value → per-share value
- Per-share fair value from DCF
- Sensitivity matrix: WACC (±200bps in 50bps increments) × terminal g
  (±100bps in 25bps increments) OR × exit multiple
- **Rejection check**: if > 70% of value sits in terminal, flag the DCF as
  unreliable and lower its weight in the final blend

### Sheet 4: Multiples
Table:
- Current P/E, EV/EBIT, EV/EBITDA, P/FCF (all using NTM estimates from Task 3)
- Company's own 5-year average and 10-year average for each multiple
- Peer median for each multiple (peer set defined in Task 1)
- Sector median for context

For each multiple: fair value = (target multiple) × (NTM metric per share).
Blend the multiples-based fair values into a single multiples-based fair
value (state weighting).

### Sheet 5: FAST Graphs Lens
Three sub-calculations per framework:

**5a. Blended P/E vs 15-year history**
- Current blended P/E (= price / blended EPS where blended = 50% TTM + 50% NTM)
- 15-year average blended P/E (compute from data; if 15y data unavailable,
  use what's available and flag)
- Fair value = 15y avg blended P/E × NTM EPS

**5b. Normalized Earnings Yield**
- E/P at current price
- 10y Treasury yield (current)
- Spread vs Treasury (positive = relatively cheap, negative = relatively expensive)

**5c. "Fair P/E" by Growth Rate**
Per framework heuristic:
- 0-5% growth: fair P/E ≈ 12-15
- 5-10% growth: fair P/E ≈ 15-18
- 10-15% growth: fair P/E ≈ growth rate (PEG ≈ 1.0), 15-20
- 15%+ growth: cap fair P/E at 22-25
Apply: fair value = fair P/E × NTM EPS

Triangulate 5a + 5b + 5c into a single FAST Graphs fair value.

### Sheet 6: Reverse DCF
- Take current stock price as given
- Solve for implied 10-year growth rate (holding margin and terminal at base case)
- Solve for implied terminal margin (holding growth and terminal at base case)
- Solve for implied terminal multiple (if Gordon used)
Output: "the market is pricing in X% revenue CAGR with Y% terminal margin,
which is [conservative / consensus / aggressive] vs realistic expectations."
Not a fair value generator on its own — a consensus check.

### Sheet 7: Triangulation & Fair Value
- DCF fair value, Multiples fair value, FAST fair value, Reverse DCF (info only)
- Method weighting with stated rationale
- Final point estimate of fair value (single number, no range)
- Current price
- MOS = (FV − Price) / FV
- Rating from MOS bands
- Buy-below = FV × 0.75
- Trim-above = FV × 1.20

### Sheet 8: Scenarios (Bull / Base / Bear)
Three scenarios, columns:
- Narrative (one paragraph)
- Probability % (must sum to 100% across the three)
- Year-10 revenue and EBIT margin assumption
- Year-10 EPS assumption
- Exit P/E assumption
- Year-10 share price
- 10-year IRR from current price
- "What has to be true" one-liner

Below: probability-weighted expected 10-year IRR.

**Sanity check**: if probability-weighted IRR < 8%, flag that the position is
not interesting regardless of MOS.

## Quality Checks Before Concluding Task 4

- [ ] All 8 sheets populated
- [ ] Quality score has full justification per dimension
- [ ] Quality threshold (≥18) verified or escalated to user
- [ ] DCF terminal value not > 70% of total value (or flagged)
- [ ] Multiples reference NTM (not TTM) for forward-looking fair value
- [ ] FAST Graphs three sub-calculations all done
- [ ] Reverse DCF outputs an interpretable implied assumption
- [ ] Triangulation has explicit weighting with rationale
- [ ] Fair value is a single number, not a range
- [ ] MOS is a percentage
- [ ] Rating is one of Strong Buy / Accumulate / Hold / Avoid
- [ ] Bull/base/bear probabilities sum to 100%
- [ ] Probability-weighted IRR computed

## Save and Hand Off

Save as `{TICKER}_valuation.xlsx`. Output a markdown-formatted summary at the
end (this will be reused in Task 5 assembly):

```
## Valuation Summary

**Quality Score**: X/30
**Fair Value**: $XXX
**Current Price**: $XXX
**Margin of Safety**: XX%
**Rating**: [Strong Buy / Accumulate / Hold / Avoid]
**Buy-Below**: $XXX  (= Fair Value × 0.75)
**Trim-Above**: $XXX  (= Fair Value × 1.20)
**Probability-Weighted 10-Year IRR**: XX%

**Method weights used**: DCF X% / Multiples X% / FAST X% / Reverse X%
**Rationale for weighting**: [one sentence]

**Quality breakdown**:
- Moat: X/5
- ROIC: X/5
- Reinvestment runway: X/5
- Capital intensity / FCF conversion: X/5
- Management: X/5
- Stress resilience: X/5

**Bull / Base / Bear**:
- Bull (P=XX%): 10y IRR XX% — [what has to be true]
- Base (P=XX%): 10y IRR XX% — [what has to be true]
- Bear (P=XX%): 10y IRR XX% — [what has to be true]
```

Then proceed to Task 5 (or wait for user confirmation in Mode B).
