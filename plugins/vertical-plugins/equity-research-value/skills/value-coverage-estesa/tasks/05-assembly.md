# Task 5 — Final Report Assembly

## Goal

Assemble the final initiating coverage report as a polished `.docx` file,
integrating the research from Task 1, the financial tables from Task 2, the
valuation conclusions from Task 3, and the charts from Task 4. This is the
artifact the user actually reads.

## Output

A `.docx` file at: `{TICKER}_value_coverage_{YYYY-MM-DD}.docx`

Target: 45-55 pages, 16,000-22,000 words, Times New Roman 11pt body, 14pt
section headers, 12pt subsection headers, single-spaced, 1-inch margins.

### LENGTH MANDATE (non-negotiable)

The user is making real capital-allocation decisions and requires an exhaustive
report. The finished docx MUST reach at least 45 pages / 16,000 words. This is
a hard floor, not an aspiration. Concretely:

- Each section's word target below is a MINIMUM, not a ceiling. If a section
  comes in under target, expand it with more analysis — never pad with filler,
  but every claim should carry its full reasoning, evidence, and implication.
- Do NOT compress or summarize the extended research from Task 1 when
  transcribing it into sections 2-7. Transcribe in full and refine; if anything,
  add depth. A common failure is sections 8-16 thinning out as generation
  proceeds — guard against this explicitly and keep the back half as dense as
  the front half.
- After drafting, COUNT the total words. If below 16,000, identify the
  thinnest sections and expand them with additional sub-analysis (more
  granular segment discussion, additional historical context, deeper treatment
  of each risk, fuller scenario narratives) until the floor is met.
- Quality is paramount, but for this user length is itself a requirement:
  a thorough 50-page report is the deliverable, not a tight 30-page one.

## Prerequisites

- Task 1 complete: `{TICKER}_research.md`
- Task 2 complete: `{TICKER}_model.xlsx`
- Task 3 complete: `{TICKER}_valuation.xlsx` AND the markdown summary from
  Task 3 conclusion
- Task 4 complete: `charts/` directory populated
- `references/value-framework.md` read
- **`references/style-guide.md` read — MANDATORY.** It defines the Italian
  language convention, page-1 title block, header/footer, table styling,
  figure captions, standard section titles, and file naming. The final docx
  must be visually identical to the golden reference (ICE June 2026 report).

## Workflow

1. **Read all prerequisite artifacts.** Load the research markdown, the
   valuation Excel summary outputs, and inventory the charts directory.

2. **Build the 16-section report** per structure below. The five extended
   sections from Task 1 (Industry, Business Model, Competitive, Growth,
   Recent Issues) are transcribed and refined — not re-written from scratch.
   The valuation sections are transcribed from Task 3 outputs.

3. **Insert tables** from Task 2 model data (extract via openpyxl and render
   in docx as native tables).

4. **Insert charts** from Task 4 PNGs at the appropriate places.

5. **Apply formatting standards** uniformly.

## Final Report Structure (16 Sections)

### Front Matter
- Title page: ticker, company name, "Value Coverage — Initiating Report",
  date, "For private use only. Not investment advice."
- Table of contents (auto-generated from heading styles)

### 1. Snapshot (1-1.5 pages, ~500 words)
Transcribe and condense from Task 1 Section 1 PLUS valuation conclusions from
Task 3 summary. Must include:
- Ticker, exchange, current price, market cap, enterprise value
- Sector, business in one sentence
- Quality score X/30, fair value (point estimate), MOS%, decision
- **Rating** (Strong Buy / Accumulate / Hold / Avoid)
- **Price levels**: Fair value (primary target), Buy-below ($FV×0.75),
  Trim-above ($FV×1.20) — each with % distance from current price
- Top 3 reasons to own, top 3 reasons NOT to own
- 10-year expected IRR (probability-weighted)

### 2. Industry & Sector Analysis (2,800-3,500 words)
Transcribe and refine Task 1 Section 2. Insert relevant charts (sector growth
visualization if available).

### 3. Company Profile & Business Model (2,800-3,500 words)
Transcribe and refine Task 1 Section 3. Insert: Chart "Revenue by Segment".

### 4. Competitive Landscape (2,400-3,000 words)
Transcribe and refine Task 1 Section 4. Insert: Chart "Peer Comparison
Multiples" if relevant for positioning.

### 5. Quality Assessment (2,000-2,400 words)
From Task 3 Sheet 2 (Quality Scoring). For each of 6 dimensions:
- Subsection heading: "[Dimension Name]: Score X/5"
- Justification paragraph
- Supporting metric or chart reference
Aggregate section: total /30, band interpretation per framework.

### 6. Growth Strategy & Forward Outlook (3,000-4,000 words)
Transcribe and refine Task 1 Section 5. Insert: chart showing forecast revenue
and margin trajectory.

### 7. Recent Issues & Pressure Points (2,000-2,800 words)
Transcribe and refine Task 1 Section 6.

### 8. Financial Analysis (1,800-2,200 words)
Insert tables (extracted from Task 2 model):
- 10-year P&L summary (revenue, gross profit, EBIT, net income, EPS,
  with growth rates)
- 10-year FCF build (CFO − capex, FCF margin, FCF/share)
- 10-year balance sheet summary (net debt, debt/EBITDA, interest coverage,
  share count)
- 10-year ROIC build
- Sector-specific KPI table (from Task 2 Sheet 3)

Prose around the tables (600-800 words): trajectory, what changed, what's
unsustainable. Explicit treatment of returns on capital, margin trajectory,
FCF generation, balance sheet strength.

Insert charts: ROIC History, Margin Trajectory, FCF & FCF Margin, Net Debt /
EBITDA, Share Count.

### 9. Forecast & DCF (1,100-1,400 words)
From Task 3 Sheet 3:
- 10-year forecast assumptions summary (linked from Task 2 Sheet 6)
- WACC build (compact table)
- Terminal value method and assumption
- DCF output: EV, equity value, per-share fair value
- Sensitivity table (transcribed from Task 3)

Insert chart: DCF Sensitivity Heatmap.

### 10. Valuation Triangulation (1,300-1,600 words)
From Task 3 Sheets 4-7:
- Multiples table: current vs 5y avg vs 10y avg vs peer median
- FAST Graphs three sub-calculations
- Reverse DCF result and interpretation
- Final point estimate of fair value, with explicit method weighting and
  rationale

Insert chart: Blended P/E History.

### 11. Margin of Safety, Rating & Price Levels (700-900 words)
From Task 3 summary:
- Fair value $X / current price $Y / MOS Z%
- **Rating**: [label] per decision matrix
- **Decision**: [full position / scale in / wait / avoid]
- **Price levels table**: fair value, buy-below, trim-above (each as absolute
  $ and % from current)
- Conditions that would change the rating

Insert chart: Stock Price with Valuation Bands.

### 12. Capital Allocation & Shareholder Returns (1,000-1,300 words)
Transcribe from Task 1 Section 8 PLUS data tables from Task 2.
- 10y cumulative capital deployment (capex, M&A, buybacks, dividends, debt
  paydown) — table or chart
- Dividend analysis (or explanation if no dividend)
- Buyback analysis: average price paid vs intrinsic value
- Return-of-capital framework
- Per-share value creation

### 13. Risks (1,200-1,500 words)
6-12 risks. Format each as a paragraph with bold lead-in:
- **[Risk Name]** (Probability: L/M/H, Magnitude: L/M/H). Description.
  Mitigation. Monitoring signal.

Cover at minimum: competitive, demand/cyclical, execution, margin/cost, balance
sheet, governance/key-person, valuation, plus any company-specific structural
risks identified in Task 1 Section 6.

### 14. Bull / Base / Bear Scenarios (900-1,200 words)
From Task 3 Sheet 8. For each scenario:
- Subsection heading: "[Scenario]: Probability X%, 10y IRR XX%"
- One-paragraph narrative
- "What has to be true" one-liner

End the section with probability-weighted expected IRR and sanity-check
commentary.

### 15. Management & Governance (600-800 words)
Transcribe from Task 1 Section 7.

### 16. Catalysts & Monitoring (350-500 words)
- What to watch over the next 4-8 quarters (specific KPIs, specific thresholds)
- What would make you reduce position size
- What would make you add
- Pull from Task 1 forecast inflection points and Task 3 sensitivity matrix

## Style Rules

- **Discursive prose, not bullets.** Sections 2-16 are written as flowing
  paragraphs, matching the ICE golden reference — NOT as bulleted lists. The
  bulleted items in the section specifications above describe the CONTENT each
  section must contain; they are not a formatting template. Render that content
  as continuous prose. Bullets are allowed only in the Snapshot (reasons to own
  / not to own), the Risks section (a short paragraph per risk with a bold
  lead-in, or the risk table), and Catalysts & Monitoring. See style guide §4.
- **No mid-paragraph bold.** Bold appears ONLY as a paragraph lead-in (a risk
  name, a scenario label, a pressure-point label). Never bold a word, figure,
  percentage, company name, or concept inside a running sentence. The ICE
  reference has essentially no inline bold; match it.
- No "BUY/HOLD/SELL" rating as an independent label. The rating is the
  decision-matrix outcome surfaced as Strong Buy / Accumulate / Hold / Avoid.
- No speculative 12-month sell-side price target. The "price target" is the
  fair value point estimate. Buy-below and trim-above are operational levels,
  not short-term forecasts.
- Declarative voice. "Revenue grew 8% per year" — not "We believe revenue
  grew approximately 8%."
- No first-person plural ("we", "our view"). Third-person analytical voice
  or stated facts.
- Every fact in extended sections is followed by an implication ("so what")
  for durability, returns, growth, or value.
- If forecast confidence is low in a section, state so explicitly.

## Formatting Standards

The authoritative specification is `references/style-guide.md`. Key rules
repeated here (the style guide prevails on any conflict):

- **Language: Italian** throughout — section titles use the standard Italian
  set from the style guide; numbers use decimal comma, thousands period,
  "mld"/"mln".
- File type: `.docx` (python-docx). Filename:
  `{TICKER}_value_coverage_{YYYY-MM-DD}_IT.docx`
- Font: Times New Roman. Body 11pt justified single-spaced; H1 14pt bold
  numbered; H2 12pt bold italic in teal-blue.
- **Page 1 title block** (no separate title page): company name large bold →
  "NYSE: TICKER · Avvio di Copertura in Ottica Value" → **thematic tagline in
  italic (mandatory — one sentence capturing the thesis)** → date/price/horizon
  line → 5-column summary table (Qualità | Fair value | Margine di sicurezza |
  Rating | IRR attesa 10a) → sector one-liner → Indice with dot leaders.
- **Header every page**: "NOME AZIENDA (NYSE: TICKER) · Copertura Value —
  Report di Avvio", small navy, centered, thin rule below.
- **Footer every page**: left "Solo per uso privato. Non è una consulenza
  d'investimento."; right "TICKER · N" (page number). Small grey.
- **Tables**: titled above as "Tabella N. Titolo" (navy bold); header row navy
  background with white bold text; alternating white / light grey-blue rows;
  thin borders; label column bold.
- **Figures**: PNGs from Task 4 inserted inline (they already contain the
  "Figura N." title and source line); below each, a caption in small italic
  grey repeating "Figura N." plus an extended description with the "so what".
  Figure numbering global and sequential.
- Close with the unnumbered "Metodologia e Fonti" section per the style guide:
  primary sources, secondary sources, method weights actually used, and the
  standard disclaimer that the rating is the mechanical MOS-matrix output.

## Quality Checks Before Concluding Task 5

- [ ] **Total word count >= 16,000 (hard floor); page count >= 45.** If not,
      expand the thinnest sections before finalizing — do not deliver under floor.
- [ ] All 16 sections present in order
- [ ] Each section meets its individual word MINIMUM (targets are floors)
- [ ] Back-half sections (8-16) are as dense as front-half sections (2-7)
- [ ] Title page and TOC included
- [ ] Five extended sections meet word minimums
- [ ] All 12-16 charts from Task 4 inserted at appropriate places
- [ ] All required tables from Task 2 inserted in Section 8
- [ ] Snapshot (Section 1) shows quality score, fair value, MOS, rating, all
      three price levels, probability-weighted IRR
- [ ] Section 11 shows fair value, MOS, rating, decision, price levels table
- [ ] No "BUY/HOLD/SELL" rating used
- [ ] No 12-month price target
- [ ] Sections 2-16 are discursive prose, NOT bulleted (bullets only in Snapshot
      reasons, Risks, Catalysts per style guide §4)
- [ ] No mid-paragraph bold anywhere; bold only as a paragraph lead-in
- [ ] Times New Roman throughout
- [ ] Page numbers present
- [ ] Footer disclaimer present
- [ ] TOC reflects actual page numbers

## Save and Hand Off

Save as `{TICKER}_value_coverage_{YYYY-MM-DD}.docx` in the working directory.

Output a final summary:
- Path to docx file
- Path to all 5 deliverables (research.md, model.xlsx, valuation.xlsx,
  charts/, value_coverage.docx)
- The headline conclusion: Rating, Fair Value, MOS, probability-weighted IRR
- One sentence on the decision rationale
- A note that all artifacts are reusable: the model.xlsx can be reopened for
  future quarterly updates, the research.md can be appended to for thesis
  maintenance, etc.

The workflow is complete.
