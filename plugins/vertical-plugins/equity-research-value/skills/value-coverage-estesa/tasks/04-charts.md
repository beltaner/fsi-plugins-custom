# Task 4 — Chart Generation

## Goal

Produce 10-16 standalone PNG chart files that visualize the company's
historical performance, forecast trajectory, and valuation conclusions.
These charts are inserted into the final docx in Task 5 and are also reusable
artifacts on their own.

## Output

A `charts/` subdirectory in the working directory, populated with PNG files.
One PNG per chart. Standard naming: `{TICKER}_{chart-slug}.png` (e.g.,
`ICE_revenue-by-segment.png`).

## Prerequisites

- Task 1 complete: `{TICKER}_research.md`
- Task 2 complete: `{TICKER}_transcript_evolution.md` (source for the
  transcript-evolution chart(s) — the per-quarter theme table and metric
  trajectories)
- Task 3 complete: `{TICKER}_model.xlsx` (source of all historical and
  forecast data)
- Task 4 complete: `{TICKER}_valuation.xlsx` (source of valuation and
  scenario data)
- **`references/style-guide.md` read — MANDATORY.** It defines the canonical
  palette, the "Figura N." title-inside-the-PNG convention, the source line,
  Italian number formatting, and all composition rules. Every chart must match
  the golden reference (ICE June 2026 report) exactly.
- Python environment with matplotlib and pandas available

## Workflow

1. **Read all prerequisites.** Load the Excel files using pandas (openpyxl
   engine). Extract the data series needed for each chart.

2. **Generate the required chart set** (10 mandatory + 2-6 sector-specific).
   Do NOT generate more than 16 total — additional charts dilute the report.

3. **Apply visual standards** uniformly across all charts (defined below).

4. **Save each chart as PNG** at the resolution and size specified.

## Required Charts (Mandatory — 10)

### 1. Stock Price & Valuation Bands (10y)
- Line: historical stock price, 10 years
- Horizontal lines: current fair value (Task 3), buy-below price, trim-above price
- Annotations: current price level, MOS%
- Filename: `{TICKER}_price-with-valuation-bands.png`

### 2. Revenue by Segment (10y history + 10y forecast, stacked)
- Stacked bar chart, segments as colors
- Year on x-axis, revenue in $M (or $B if appropriate) on y-axis
- Vertical line separating history from forecast
- Filename: `{TICKER}_revenue-by-segment.png`

### 3. Margin Trajectory (10y history + 10y forecast)
- Three lines: Gross margin %, EBIT margin %, FCF margin %
- Vertical line separating history from forecast
- Filename: `{TICKER}_margin-trajectory.png`

### 4. ROIC History (10y) + Forecast
- Line chart: ROIC over 10y history + 10y forecast
- Horizontal dashed line: WACC (from Task 3 DCF sheet)
- Annotation: 10y average ROIC
- Filename: `{TICKER}_roic-history-forecast.png`

### 5. Free Cash Flow & FCF Margin (10y history + 10y forecast)
- Bars: FCF in $M (left axis)
- Line: FCF margin % (right axis)
- Vertical line separating history from forecast
- Filename: `{TICKER}_fcf-and-margin.png`

### 6. Net Debt / EBITDA (10y history + 5y forecast)
- Bar chart
- Horizontal line at 3.0x as a reference (typical investment-grade threshold)
- Filename: `{TICKER}_leverage.png`

### 7. Share Count & Per-Share Value Creation (10y)
- Bars: diluted share count
- Line on secondary axis: FCF per share
- Annotations: cumulative buyback ($M), cumulative dilution from SBC
- Filename: `{TICKER}_share-count-fcf-per-share.png`

### 8. Peer Comparison: Multiples Table as Chart
- Grouped bar chart: company vs 3-5 peers
- Multiples grouped: P/E NTM, EV/EBIT NTM, P/FCF NTM
- Company highlighted in distinct color
- Filename: `{TICKER}_peer-multiples.png`

### 9. Historical Valuation Multiple (15y blended P/E)
- Line: blended P/E over 15 years (or as many years as data allow)
- Horizontal line: 15y average
- Annotation: current blended P/E, % premium/discount to history
- Filename: `{TICKER}_blended-pe-history.png`

### 10. DCF Sensitivity Heatmap
- Heatmap: WACC (rows) × terminal growth or exit multiple (columns)
- Cells show fair value per share
- Current price highlighted; cells delivering >25% MOS shaded green,
  <0% MOS shaded red
- Filename: `{TICKER}_dcf-sensitivity.png`

## Sector-Specific Charts (Pick 2-6)

Choose charts that visualize the sector-specific KPIs from Task 1. Examples:

**For SaaS/software**:
- NRR trend with industry benchmark line
- ARR growth and rule-of-40 over time

**For apparel/retail**:
- Comparable sales by geography over time
- DTC vs Wholesale mix evolution
- Inventory growth vs revenue growth (overlay)

**For insurance broker**:
- Organic growth vs M&A contribution stacked over time
- EBITDAC margin trajectory

**For exchange/data**:
- Recurring vs transactional revenue mix evolution
- Daily ADV by asset class (multi-line)
- Subscription revenue growth

**For consumer staples**:
- Organic volume vs price/mix contribution
- Gross margin vs input cost index

**For industrials**:
- Operating ratio over the cycle
- Capex / D&A ratio

Pick 2-6 based on which KPIs from Task 1 best tell the story. Filename
pattern: `{TICKER}_{descriptive-slug}.png`

## Transcript Evolution Charts (1-2 — when useful)

The new report Section 8 ("Evoluzione su 8 Trimestri") benefits greatly from a
visual, because a quarter-by-quarter trajectory is exactly what a chart conveys
better than prose. Read `{TICKER}_transcript_evolution.md` (Task 2) and produce
**1-2 charts** for this section WHEN the material supports it. Skip only if the
transcript data is too sparse to chart meaningfully (e.g. very few quarters);
in that case note why in the hand-off.

Choose whichever of the following best fits the data Task 2 actually produced:

### A. Metric trajectory across quarters (preferred when a clean metric exists)
A multi-quarter line or bar chart of the 1-3 most important quantitative metrics
the management discussed across the window — e.g. synergies realized per quarter,
a backlog/ASV figure, a segment growth rate, a guidance figure. X-axis = quarters
(oldest → newest), value labels on points. This is the most concrete way to show
whether a tracked theme is genuinely improving or deteriorating.
- Filename: `{TICKER}_transcript-metric-trajectory.png`

### B. Theme trajectory heatmap / status grid (when themes are qualitative)
A grid: rows = tracked themes, columns = quarters, each cell shaded by status
(e.g. green = positive/improving tone, amber = stable/mixed, red =
negative/deteriorating tone). This visualizes the evolution table from Task 2 at
a glance and works even when themes are qualitative rather than numeric. Use the
standard palette: green #2E9E4F, amber #E8A33D, red #C0392B.
- Filename: `{TICKER}_transcript-theme-heatmap.png`

Apply all the standard visual rules (Italian text, "Figura N." title inside the
PNG, source line "Fonte: transcript earnings call {range trimestri}", canonical
palette). These charts are inserted into Section 8 by Task 6.

## Visual Standards

The authoritative specification is `references/style-guide.md`. Key rules
repeated here for convenience (the style guide prevails on any conflict):

- **Dimensions**: 1600 × 1000 pixels at 150 DPI (figsize=(10.67, 6.67), dpi=150)
- **Language**: ALL chart text in Italian, with Italian number formats
  (decimal comma: "11,5%", "4,3x"; thousands period; "mld"/"mln")
- **Title INSIDE the PNG**: "Figura N. Titolo descrittivo" — navy (#1F4E79),
  bold, ~14pt, top. The running figure number must match the insertion order
  planned for Task 5.
- **Source INSIDE the PNG**: bottom-left, small italic grey
  ("Fonte: [documenti usati].")
- **Canonical palette**:
  - Navy #1F4E79 — primary series
  - Teal #2E8B8B — secondary series
  - Amber #E8A33D — highlight; the SUBJECT COMPANY in peer comparisons;
    weighted-result bars
  - Light blue #9DC3E6 — tertiary/lighter series
  - Green #2E9E4F — positive thematic series; bull scenario
  - Red #C0392B — negative/GAAP-loss series; bear scenario
  - Grey #808080 dashed — reference lines (with small labels, e.g.
    "Media 10 anni 24,5x", "Soglia equity 8%")
- Value labels on bars where readable ("$9,9 mld", "+60%")
- Forecast period: same hue, lighter shade or dashed; vertical separator line
- Heatmaps: light-to-navy blue gradient, base case visually identifiable
- Grid: light grey horizontal gridlines only; top and right spines hidden
- Background: white

## Code Pattern

For each chart, the canonical pattern is:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load data from Excel
df = pd.read_excel(f'{TICKER}_model.xlsx', sheet_name='P&L', engine='openpyxl')
# ... extract relevant rows/columns ...

fig, ax = plt.subplots(figsize=(10.67, 6.67), dpi=150)  # = 1600 x 1000

# Plot
ax.plot(years, values, color='#1f4e79', linewidth=2)
# ... or .bar, .stackplot, etc.

# Formatting
ax.set_title('Title Here', loc='left', fontsize=14, fontweight='bold')
ax.set_xlabel('Year')
ax.set_ylabel('Y Label')
ax.spines['top'].set_visible(False)
ax.spines['right'].set_visible(False)
ax.grid(axis='y', alpha=0.3)

# Source
fig.text(0.02, 0.02, 'Source: 10-K filings, internal model',
         fontsize=8, style='italic', color='grey')

fig.tight_layout()
fig.savefig(f'charts/{TICKER}_{slug}.png', dpi=150, bbox_inches='tight')
plt.close(fig)
```

## Quality Checks Before Concluding Task 4

- [ ] 10 mandatory charts produced
- [ ] 2-6 sector-specific charts produced
- [ ] 1-2 transcript-evolution charts produced for Section 8 (or a note on why
      the transcript data was too sparse to chart)
- [ ] Total charts in `charts/` directory: 15-18 (favor the upper end for a
      50-62 page report)
- [ ] All files are PNG, 1600x1000 at 150 DPI
- [ ] All filenames follow `{TICKER}_{slug}.png` pattern
- [ ] No chart uses rainbow palette
- [ ] Forecast period visually distinguished from history
- [ ] Reference lines (WACC, MOS thresholds) included where relevant

## Save and Hand Off

Output a one-paragraph summary noting:
- Path to `charts/` directory
- Number of charts produced (mandatory + sector-specific + transcript)
- Any chart that could not be produced due to missing data, and why

Then proceed to Task 5 (or wait for user confirmation in Mode B).
