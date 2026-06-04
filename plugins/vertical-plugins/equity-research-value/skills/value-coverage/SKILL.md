---
name: value-coverage
description: "Create a deep-dive initiating coverage report on a single equity in value-investing style (25-40 pages, 9,000-14,000 words). Audience is a private long-term investor with a 5-10 year horizon, NOT a sell-side analyst. Quality-first framework — durability of competitive advantage and ROIC sustainability come before valuation. Strong emphasis on industry analysis, business model deconstruction, competitive landscape, growth strategy, and a dedicated section on recent issues and pressure points — these sections must be substantially deeper and longer than a standard report. Output includes a point estimate of intrinsic value (the price target), a buy-below and trim-above price, a margin of safety, and a rating (Strong Buy / Accumulate / Hold / Avoid) derived from the decision matrix. Use when user requests 'value coverage', 'deep dive', 'initiating coverage value-style', 'compounder analysis', 'long-term coverage', or similar wording asking for a fundamental write-up on a stock the user does not yet own or is just starting to study."
---

# Value Coverage — Initiating Report (Extended Edition)

## Key Characteristics

- **Length**: 25-40 pages
- **Word Count**: 9,000-14,000 words
- **Tables**: 8-14 (only when they earn their place)
- **Figures**: 10-16 charts
- **Turnaround**: 2-4 days from input ingestion
- **Audience**: Private long-term value investor, 5-10 year horizon, no clients to convince
- **Focus**: Is this a wonderful business? At what price would I own it? What's the margin of safety today?
- **Font**: Times New Roman 11pt body, 14pt section headers, 12pt subsection headers, single-spaced, 1-inch margins
- **Tone**: Honest analyst writing for themselves. No "BUY/HOLD/SELL", no "we recommend", no 12-month price target.

## Depth Mandate (READ FIRST)

This is the EXTENDED edition of the value-coverage skill. Five sections must be written
at substantially greater depth and length than a conventional report. They are the
analytical core and together should account for roughly 55-60% of total word count:

1. **Industry & Sector Analysis** — target 1,800-2,500 words
2. **Company Profile & Business Model** — target 1,800-2,500 words
3. **Competitive Landscape** — target 1,500-2,200 words
4. **Growth Strategy & Forward Outlook** — target 2,000-3,000 words
5. **Recent Issues & Pressure Points** — target 1,200-1,800 words

If any of these five sections comes in materially shorter than its target, the report
is incomplete. These sections must go beyond description into analysis: every fact must
be followed by a "so what" — what it implies for durability, returns, or intrinsic value.

The remaining sections (quality scoring, financials, valuation, capital return, risks)
remain rigorous but are sized normally.

## When to Use

Trigger this skill when the user requests:

- "Initiating coverage on [Company] value-style"
- "Deep dive on [Company]"
- "Value coverage of [Company]"
- "Long-term thesis on [Company]"
- "Compounder analysis [Company]"
- "Is [Company] a buy at current prices?" (when no prior coverage exists)
- "Fundamental write-up on [Company]"

## Do NOT Use If

- User requests a quarterly earnings update -> use `earnings-analysis` skill
- User requests a sell-side initiation note (institutional clients, PT, rating) -> use default `initiating-coverage` skill
- User requests a quick screen, one-pager, or summary -> use `one-pager` skill
- User requests pitch deck or PowerPoint output -> different skill
- User requests short-form analysis (< 5 pages) -> use `flash-note` or similar

## Required Inputs

Ask the user to provide, at minimum:

1. **Ticker and exchange** (mandatory)
2. **Latest 10-K or 20-F** (mandatory — full annual report)
3. **Latest 10-Q or interim** (mandatory)
4. **Last 4-8 earnings call transcripts** (strongly recommended — captures management tone, capital allocation framing, multi-quarter consistency)

Optional but valuable:

5. Investor Day presentation / multi-year strategic plan deck (last 2 years)
6. Peer company 10-Ks (top 3-5 peers) — for the competitive landscape section
7. Industry primer or sector report
8. Past management letters / annual shareholder letters

If the user has not provided these, ask once at the start. Do NOT proceed with
web-search-only data for an initiating coverage — the depth required, especially in
the four extended sections, demands primary documents.

## Workflow Steps

1. **Ingest and inventory.** Read all provided documents. Build internal data tables
   for the last 10 years of: revenue, gross margin, EBIT margin, net margin, ROIC, FCF,
   FCF margin, capex/revenue, debt/EBITDA, share count, dividend per share, buyback spend.
   Flag missing years.

2. **Deconstruct the business model.** Before writing anything else. What does the company
   sell, to whom, through which channels, how does it get paid, what is the unit economics,
   what makes a customer return. This anchors everything downstream.

3. **Identify the sector and pull the right KPIs.** Different sectors need different metrics.
   Examples (not exhaustive):
   - SaaS / software: NRR, gross retention, ARR growth, magic number, rule of 40, FCF margin
   - Apparel / retail: comparable sales (comps), revenue by geography, DTC vs wholesale mix,
     gross margin, inventory turns, inventory growth vs revenue growth, store count and
     four-wall productivity (sales per square foot), full-price sell-through
   - Consumer staples: organic volume, price/mix, gross margin, working capital cycle, ROIC
   - Industrial / freight: tonnage, operating ratio, asset utilization, capex cycle
   - Financial data/ratings: subscription %, retention, price/volume, incremental margin
   - Insurance broker: organic growth, contingent commissions, EBITDAC margin, retention
   - Identify the sector at the start and select the 6-8 KPIs that actually matter.
     State them explicitly and use them consistently throughout the report.

4. **Score the quality of the business.** Apply the 6-dimension framework from
   `references/value-framework.md`. Each dimension scored 1-5 with justification.

5. **Triangulate intrinsic value.** Use 4 methods (see framework doc for formulas):
   DCF, multiples, FAST Graphs lens, reverse DCF.

6. **Produce ONE point estimate of fair value.** A single number, weighted from the
   4 methods, with explicit weighting rationale. No ranges.

7. **Calculate margin of safety** and map to the decision matrix.

8. **Build bull / base / bear scenarios** with explicit probabilities and 10-year IRRs.

9. **Risk register** — 6-12 risks, each with probability, magnitude, mitigation,
   monitoring signal.

10. **Write the report in the structure below**, respecting the Depth Mandate.

## Report Structure

The report must follow this section order. Word counts are guides; the four extended
sections have hard minimum targets per the Depth Mandate.

### 1. Snapshot (1 page, ~400 words)
- Ticker, exchange, current price, market cap, enterprise value
- Sector, business in one sentence
- Quality score (X/30), fair value (point estimate), MOS%, decision
- **Rating** — derived from the decision matrix, stated explicitly as one of:
  Strong Buy (MOS > 25%), Accumulate (MOS 10-25%), Hold / Watchlist (MOS 0-10%),
  Avoid / Reduce (MOS < 0%). The rating is the decision-matrix outcome surfaced as a
  label — it is not an independent sell-side rating.
- **Price levels** — three explicit, operational numbers:
  - *Fair value (primary price target)*: the point estimate of intrinsic value
  - *Buy-below price*: the price that delivers a 25% margin of safety
    (= fair value x 0.75), i.e. the level at which a full position is justified
  - *Trim-above price*: a price meaningfully above fair value at which valuation risk
    warrants reducing (default = fair value x 1.20; adjust with rationale for very
    high-quality compounders where a premium is more defensible)
- Top 3 reasons to own, top 3 reasons NOT to own
- 10-year expected IRR (probability-weighted)

### 2. Industry & Sector Analysis (EXTENDED — target 1,800-2,500 words)
This section must be a genuine industry study, not a paragraph of context. Cover:
- **Market definition and sizing**: total addressable market, served market, current
  penetration. Distinguish the category the company competes in from adjacent categories.
- **Historical growth and forward growth**: category growth rate over the last 10 years,
  the structural and demographic drivers behind it, and a reasoned forward estimate.
  Separate volume growth from price growth.
- **Demand drivers**: what makes the end market grow — demographics, disposable income,
  cultural / behavioral shifts, technology, regulation. Assess the durability of each.
- **Industry structure**: concentration (fragmented vs consolidated), the economics of
  the typical participant, where industry profit pools sit and whether they are shifting.
- **Cyclicality**: is demand cyclical, seasonal, secular? Map performance across the GFC,
  COVID, and the 2022 inflation shock. Identify where the industry sits in its cycle now.
- **Channel dynamics**: how the product reaches the end customer, how channel mix is
  evolving (e.g. DTC vs wholesale, physical vs digital), and who captures margin in each.
- **Structural threats and tailwinds**: substitution risk, disruption, input-cost trends,
  regulatory direction, ESG / sustainability pressure, geopolitics and tariffs where relevant.
- **Why this industry does — or does not — produce durable economic profit.** This is the
  closing judgment of the section and must be explicit.

### 3. Company Profile & Business Model (EXTENDED — target 1,800-2,500 words)
A deep deconstruction of how the company actually works and makes money. Cover:
- **Origin and evolution**: brief history, how the company reached its current position,
  major strategic pivots and what they reveal about the company's DNA.
- **What it sells**: product / service portfolio, the role of each line, lifecycle stage.
- **Revenue architecture**: a detailed breakdown of revenue by segment, by geography, by
  channel, and by customer type. Show the mix today and how it has shifted over 5-10 years.
  For each meaningful segment: size, growth rate, margin profile, strategic importance.
- **Unit economics**: revenue per customer or per store or per unit, contribution margin,
  customer acquisition cost and lifetime value where applicable, payback period.
- **How segments are performing right now**: which parts are accelerating, which are
  decelerating, which are under pressure, and why. Use the most recent 4-8 quarters.
- **The economic engine**: the single mechanism that converts activity into profit and
  cash. Explain it in plain terms — then explain what could break it.
- **Operating model**: manufacturing / sourcing, supply chain, asset intensity, fixed vs
  variable cost structure, operating leverage.
- **The one-sentence "why they pay us and not someone else"** — and a rigorous test of
  whether that sentence is still true and will remain true for 10 years.

### 4. Competitive Landscape (EXTENDED — target 1,500-2,200 words)
- **Map of competition**: direct competitors, adjacent threats, and potential entrants.
  For the top 3-6 competitors: size, positioning, market share, trajectory, strengths
  and weaknesses relative to the subject company.
- **Market share dynamics**: who is gaining, who is losing, and the mechanism behind the
  shift. Share stability is itself evidence about moat strength.
- **Barriers to entry**: capital, brand, distribution, scale, regulation, switching costs,
  network effects. Assess how high each barrier really is — and whether it is rising or
  eroding. Be skeptical: many claimed barriers are weaker than management asserts.
- **The moat**: name the moat type(s) explicitly (intangible assets, switching costs,
  network effects, cost advantage, efficient scale). Assess width and, more importantly,
  durability. Provide evidence from pricing power, margin stability, and share retention.
- **Competitive intensity and rivalry**: pricing discipline vs price war risk, the threat
  of well-capitalized new entrants, private-label or low-cost disruption.
- **The honest verdict**: is the competitive position strengthening, stable, or weakening?
  State it plainly and support it.

### 5. Quality Assessment (3-4 pages, ~1,600 words) — THE SCORING CORE
For each of the 6 quality dimensions in `references/value-framework.md`:
moat, ROIC, reinvestment runway, capital intensity / FCF conversion, management quality,
stress resilience. Each gets a 1-5 score with paragraph justification. Aggregate to /30.
This section converts the qualitative analysis of sections 2-4 into a structured score.

### 6. Growth Strategy & Forward Outlook (EXTENDED — target 2,000-3,000 words)
The most important forward-looking section. Cover:
- **Management's stated strategy**: the explicit multi-year plan, targets, and timeline.
  Summarize it fairly, then assess it critically.
- **Growth algorithm decomposition**: break future growth into its components — unit /
  volume growth, price/mix, new geographies, new categories, channel expansion, M&A.
  Quantify each where possible. A credible growth story names its sources.
- **Geographic expansion**: maturity of each region, white-space remaining, execution
  risk and local competitive dynamics in the key growth markets.
- **New category / adjacency expansion**: track record of extending beyond the core,
  probability of success, and the returns on capital those extensions are likely to earn.
- **Reinvestment runway**: how much capital can be deployed, at what incremental ROIC,
  for how long. This is what separates a compounder from a cash cow — see framework doc.
- **Margin trajectory**: is there a credible path to margin expansion (or a risk of
  compression)? Name the specific operating-leverage or mix mechanism. Never assume
  margin expansion without a stated cause.
- **Forward financial outlook**: a reasoned 10-year view of revenue growth, margins,
  capex, working capital, and share count — the inputs that feed the DCF.
- **What has to go right**: the 3-5 things that must hold for the growth thesis to work.
- **Saturation and maturity risk**: honestly assess when and how growth slows, and what
  the business looks like at maturity.

### 7. Recent Issues & Pressure Points (EXTENDED — target 1,200-1,800 words)
A dedicated, honest examination of what is currently going wrong, or is contested, or
worries the market. This section is mandatory regardless of how strong the business is —
every company has pressure points, and a report that finds none has not looked hard
enough. Identify the issues specific to THIS company from the filings, transcripts, and
recent news; do not apply a generic checklist. Typical pressure points to probe for:
- **Growth deceleration**: is a previously fast-growing segment, geography, or the whole
  company slowing? Is it cyclical, competitive, or structural (the saturation question)?
- **Margin pressure**: input costs, tariffs / trade exposure, mix shift, promotional
  intensity, deleverage. Identify the driver and whether it is transient or permanent.
- **Management / leadership disruption**: recent departures of key executives (CEO, CFO,
  CPO, divisional heads), succession uncertainty, board turnover, strategy turnover.
- **Product or operational problems**: quality issues, recalls, missed product cycles,
  inventory mismanagement, supply-chain disruption, an underperforming key launch.
- **Competitive losses**: market share ceded to a specific rival, a new entrant gaining
  traction, erosion of pricing power or brand heat.
- **Demand / end-market weakness**: a soft consumer, a key region underperforming, a
  category falling out of favor.
- **Balance sheet or capital concerns**: rising leverage, a refinancing wall, a buyback
  done at high prices, a stretched working-capital position.
- **Legal, regulatory, governance, or reputational issues**: litigation, investigations,
  regulatory scrutiny, ESG / labor / sourcing controversies, accounting questions.
- **Valuation / sentiment problems**: a sharp share-price decline, multiple compression,
  a souring narrative, elevated short interest.
For each material issue: state what it is, how it arose, its financial magnitude, whether
it is transient or structural, what management is doing about it, and — critically — what
it implies for the long-term thesis and the intrinsic value estimate. Distinguish clearly
between issues that are noise (a value investor should look through them) and issues that
are signal (they change the thesis). This judgment is the point of the section.

### 8. Financial Analysis (3-4 pages, ~1,400 words)
Tables (not prose) for:
- 10-year P&L summary (revenue, gross profit, EBIT, net income, EPS, with growth rates)
- 10-year FCF build (CFO - capex, FCF margin, FCF/share)
- 10-year balance sheet summary (net debt, debt/EBITDA, interest coverage, share count)
- 10-year ROIC build (NOPAT / invested capital, decomposed)
- Sector-specific KPI table (e.g. for apparel/retail: comps, inventory turns, sales/sqft)
Prose around the tables: what changed, the trajectory, what looks unsustainable.
Explicit treatment of: returns on capital, margin structure and trend, free cash flow
generation and conversion, and the balance sheet / leverage position.

### 9. Forecast & DCF (2-3 pages, ~900 words)
- 10-year explicit forecast: revenue growth, margin trajectory, capex, working capital,
  share buyback assumption — consistent with the Growth Strategy section
- WACC build (risk-free rate source, ERP assumption, beta, debt cost, weights)
- Terminal value (Gordon growth or exit multiple — state which and why)
- DCF output: enterprise value, equity value, per-share fair value
- Sensitivity table: WACC x terminal growth rate (or x exit multiple)

### 10. Valuation Triangulation (2-3 pages, ~1,000 words)
- Multiples table: company vs 5y avg vs 10y avg vs peer median, for P/E, EV/EBIT,
  EV/EBITDA, P/FCF
- FAST Graphs analysis: blended P/E vs 15y average, normalized earnings yield,
  "fair" P/E based on growth rate
- Reverse DCF: what growth x margin x terminal is the current price implying? Plausible?
- **Final point estimate of fair value, with explicit weighting of methods**

### 11. Margin of Safety, Rating & Price Levels (1 page, ~550 words)
- Fair value $X / current price $Y / MOS Z%
- **Rating**: the decision-matrix outcome stated as a label — Strong Buy / Accumulate /
  Hold / Avoid (see Snapshot for the MOS bands)
- **Decision**: full position / scale in / wait / avoid, per the matrix in the framework doc
- **Price levels table**: fair value (primary target), buy-below price (25% MOS level),
  trim-above price. Show each as an absolute price and as % distance from current price.
- Conditions that would change the rating (price level moves, fundamental change)
- A one-line reconciliation: if the rating and the current price seem to conflict with
  the quality score, explain it (a wonderful business can still be a Hold on price)

### 12. Capital Allocation & Shareholder Returns (1.5-2 pages, ~800 words)
A dedicated, thorough treatment. Cover:
- **Capital allocation history**: 10-year cumulative breakdown of where cash went —
  capex, M&A, buybacks, dividends, debt paydown — with commentary on the returns earned.
- **Dividend analysis**: whether the company pays a dividend; if so — history, payout
  ratio, FCF cover, growth rate, yield vs its own history and vs peers, sustainability.
  If it does NOT pay a dividend, state why (reinvestment priority, lifecycle stage) and
  whether a future initiation is plausible.
- **Buyback analysis**: history of repurchases, average price paid vs intrinsic value
  (did they buy low or high?), authorization remaining, share count trajectory, and
  whether buybacks have been accretive or value-destructive.
- **The return-of-capital framework**: how management thinks about returning cash vs
  reinvesting it, and whether that framework is rational given the reinvestment runway.
- **Per-share value creation**: total shareholder yield (dividend + net buyback) and
  whether per-share metrics have compounded faster than absolute metrics.

### 13. Risks (2 pages, ~800 words)
- 6-12 risks. For each: description, probability (L/M/H), magnitude (L/M/H), mitigation,
  monitoring signal (the specific data point that signals the risk is materializing).
- Cover at minimum: competitive / market-share risk, demand / cyclical risk, execution
  risk on the growth strategy, margin / cost risk, balance-sheet risk, governance / key-
  person risk, valuation risk, and any company-specific structural risks.

### 14. Bull / Base / Bear (1.5-2 pages, ~700 words)
Three scenarios, each with: one-paragraph narrative, probability (sum to 100%),
10-year IRR estimate, "what has to be true" in one sentence. Probability-weighted
expected return at the end.

### 15. Management & Governance (1 page, ~450 words)
- CEO and CFO: tenure, background, prior track record
- Insider ownership %, founder involvement
- Compensation structure: short-term vs long-term, the KPIs it incentivizes
- Board quality, governance red flags if any
- Communication quality: candor in letters and on calls, willingness to admit error

### 16. Catalysts & Monitoring (0.5 page, ~250 words)
- What to watch over the next 4-8 quarters (specific KPIs, specific thresholds)
- What would make you reduce position size
- What would make you add

## Output Format

- File type: `.docx`
- Filename: `{TICKER}_value_coverage_{YYYY-MM-DD}.docx`
- Font: Times New Roman 11pt body, 14pt section headers (bold), 12pt subsection
  headers (bold italic)
- Margins: 1 inch all sides
- Page numbers: bottom right
- Header: ticker and report title
- Footer: "For private use only. Not investment advice. Sources: [primary documents used]"
- Tables: clean, no color fills, single-line borders
- Charts: greyscale or single-color, source noted under each chart
- Include a table of contents after the snapshot, given the report length

## Style Rules

- Write declaratively. "Revenue grew 8% per year" not "We believe revenue grew ~8%"
- No first-person plural ("we", "our view"). Third-person analytical voice or stated facts.
- The rating is the decision-matrix outcome (Strong Buy / Accumulate / Hold / Avoid),
  derived mechanically from the margin of safety — it is NOT an independent sell-side call.
- The price target is the point estimate of intrinsic (fair) value. Do NOT produce a
  speculative 12-month sell-side price target based on a target forward multiple. The
  buy-below and trim-above prices are operational levels derived from fair value, not
  short-term forecasts.
- Every fact in the five extended sections must be followed by an implication — what it
  means for durability, returns, growth, or value. Description without analysis is a defect.
- Acknowledge what you don't know explicitly. If forecast confidence is low, say so.
- Numbers > adjectives. "ROIC averaged 22% over 10 years" beats "exceptional returns".
- If the quality score is below 18/30, the report can be shorter and should end with
  "this is not a candidate for long-term holding; further work not justified".

## References

For the underlying value framework, quality scoring criteria, and DCF/MOS formulas, read:

- `references/value-framework.md`
