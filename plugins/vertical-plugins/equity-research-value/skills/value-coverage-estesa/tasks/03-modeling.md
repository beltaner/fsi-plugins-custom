# Task 3 — Financial Modeling

## Goal

Produce a 10-year historical + 10-year forecast financial model in Excel, with
sector-specific KPIs, ROIC build, and FCF build. This model is the quantitative
foundation for Task 4 (valuation) and feeds inputs to Task 5 (charts) and
Task 5 (final report tables).

## Output

An Excel file at: `{TICKER}_model.xlsx`

The file must be a usable, reusable model — the same workbook will be reopened
in future quarters to run `/earnings-analysis` or to update the forecast after
new data. Therefore: clean formatting, blue-input / black-formula / green-link
convention, no hardcoded values where formulas belong.

## Prerequisites

- Task 1 complete: `{TICKER}_research.md` must exist and be read first
- Sector-specific KPI set identified in Task 1 (used in Sheet 3)
- 10-K and at least one 10-Q ingested from user inputs
- `references/value-framework.md` read (for ROIC formula conventions)

## Workflow

1. **Read prerequisites.** Open and read `{TICKER}_research.md` to retrieve:
   sector, KPI set, growth-strategy assumptions for the forecast period,
   segment list.

2. **Build the workbook with 6 sheets** as defined below. Each sheet has a
   defined purpose. Do not over-engineer — these 6 sheets are the structure;
   do not add appendix sheets unless explicitly justified by sector specifics.

3. **Source historical data exhaustively from filings.** For revenue, costs,
   margins, capex, working capital — go to the 10-K segment notes and CF
   statement, not summary tables. Build at least 10 years of history; if the
   company has been public less than 10 years, build what's available and
   flag it.

4. **Build forecast bottom-up.** Forecast revenue by segment using
   growth-strategy assumptions from Task 1. Forecast margins explicitly (not
   "expand 100bps per year" without a mechanism — name the mechanism). Forecast
   capex and working capital as % of revenue or as explicit absolutes.

5. **Compute ROIC properly.** Use the framework definition. Decompose into
   NOPAT margin × invested capital turnover. Show both 10-year history and
   forecast.

6. **Build FCF the right way.** Cash from operations − capex (be explicit about
   whether you include stock-based comp; the framework's default is to subtract
   SBC fully from FCF since it's a real economic cost). Show FCF margin, FCF
   conversion (FCF / Net Income), and FCF per share.

7. **Quality-check the model.** Internal consistency: revenue ties between
   sheets, segment sum = total, balance sheet balances, capex on CF = capex
   on PP&E roll-forward, share count progresses through buyback assumption.

## Workbook Structure (6 Sheets)

### Sheet 1: README
A one-page text sheet documenting:
- Ticker, fiscal year-end convention used
- Data sources (which 10-K, which 10-Q, which transcripts)
- Build date
- Sector and identified KPIs (must match Task 1)
- Key forecast assumptions in 5-8 bullets
- Formatting convention legend (blue=input, black=formula, green=cross-sheet link)
- Known limitations (missing years, restatement issues, segment changes)

### Sheet 2: P&L
10y history + 10y forecast, columns = years, rows = line items.

Required rows:
- Revenue (by segment, then total)
- Revenue growth % (total and per segment)
- COGS, Gross Profit, Gross Margin %
- SG&A, R&D (if applicable), other opex
- EBIT (operating income), EBIT margin %
- Interest expense, interest income, net interest
- Pre-tax income, tax expense, effective tax rate %
- Net income, Net margin %
- Shares outstanding (diluted average)
- EPS (diluted)
- EPS growth %

### Sheet 3: Sector KPIs
The 6-8 sector-specific KPIs identified in Task 1, computed across 10y history
and 10y forecast. Examples by sector:

- SaaS: NRR, gross retention, ARR ($M), magic number, rule of 40, FCF margin
- Apparel/retail: comparable sales %, revenue by geo, DTC/wholesale mix %,
  gross margin, inventory turns, sales per sqft
- Insurance broker: organic growth %, contingent commissions ($M),
  EBITDAC margin, retention %, M&A revenue contribution
- Exchange/data: recurring revenue %, transactional revenue %, daily ADV by
  asset class, subscription growth, FCF margin
- Consumer staples: organic volume, price/mix, gross margin, working capital %
- Asset-light fee compounder: take rate, AUM growth, fee compression, FCF/NI

If the sector is none of the above, design the KPI set bespoke based on what
matters for that business — but state explicitly in the README why those KPIs.

### Sheet 4: Cash Flow & FCF Build
10y history + 10y forecast.

Required rows:
- Net income
- Plus: D&A, SBC, other non-cash
- Working capital changes (detailed: AR, inventory, AP)
- Cash from Operations (CFO)
- Capex (maintenance vs growth where determinable)
- Free Cash Flow = CFO − capex
- FCF margin %
- FCF conversion = FCF / Net Income
- FCF per share
- FCF per share growth %
- Capital allocation: dividends paid, buybacks, M&A, debt paydown, ending cash

### Sheet 5: Balance Sheet & ROIC Build
10y history + 10y forecast.

Balance sheet section:
- Cash and equivalents
- Receivables, inventory, other current assets
- PP&E net, intangibles, goodwill, other LT assets
- Payables, debt (current + LT), other liabilities
- Equity
- Net debt = total debt − cash
- Net debt / EBITDA
- Interest coverage = EBIT / interest expense

ROIC build:
- NOPAT = EBIT × (1 − tax rate)
- Invested capital = Net Debt + Equity (or Working Capital + Net PP&E + Net Intangibles)
- ROIC = NOPAT / Invested Capital
- ROIC decomposition: NOPAT margin × Invested capital turnover
- Reinvestment rate = (Change in invested capital) / NOPAT
- Implied compounding rate = ROIC × Reinvestment rate

### Sheet 6: Forecast Assumptions Summary
A single dashboard sheet that surfaces all the explicit forecast assumptions
in one place. The user (or future Claude in a re-run) can change values here
and the model will flow through. Show:
- Revenue growth assumption by segment, year-by-year
- Margin assumption (gross, EBIT, net)
- Capex / revenue %
- Working capital / revenue %
- Share buyback assumption (count or $ per year)
- Dividend growth assumption (if applicable)
- Tax rate assumption

For each, a brief note on the rationale (e.g., "EBIT margin expands to 28%
by year 5 based on operating leverage on subscription revenue mix shift —
see Task 1 research section 5").

## Formatting Standards

- Font: Calibri 10pt (or equivalent system default)
- Blue cells = direct input (hardcoded)
- Black cells = formula within sheet
- Green cells = formula linking to another sheet
- Negative numbers in parentheses, not minus sign
- Thousands separator (1,000), no decimals on $M figures, 1 decimal on margin %
- Year headers in bold, frozen pane at row 1 and column A
- One blank row between section blocks

## Quality Checks Before Concluding Task 3

- [ ] All 6 sheets populated
- [ ] 10-year history + 10-year forecast on P&L, CF, BS, ROIC
- [ ] Revenue ties between P&L (segment total) and Sector KPIs sheet
- [ ] Capex on CF sheet = capex driving PP&E roll-forward on BS sheet
- [ ] Net income on CF starting line = Net income on P&L final line
- [ ] Sector KPIs are the ones identified in Task 1
- [ ] All forecast assumptions traceable to the Assumptions sheet
- [ ] No hardcoded values inside formula cells
- [ ] README sheet completed

## Save and Hand Off

Save as `{TICKER}_model.xlsx`. Output a one-paragraph summary noting:
- File saved (path)
- 10-year revenue CAGR (historical and forecast)
- 10-year average ROIC and 10-year forecast ending ROIC
- 10-year average FCF margin and 10-year ending FCF margin (forecast)
- Net debt / EBITDA today and 5 years forward
- Any data gaps or restatement issues flagged

Then proceed to Task 4 (or wait for user confirmation in Mode B).
