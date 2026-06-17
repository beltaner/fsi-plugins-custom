# Task 1 — Company Research

## Goal

Produce a deep, structured research document that captures everything analytically
relevant about the company. This document is the analytical backbone of all
subsequent tasks. Tasks 2 (modeling), 3 (valuation), 4 (charts), and 5 (assembly)
all consume the artifacts produced here.

## Output

A markdown file at: `{TICKER}_research.md`

Target length: **9,000-13,000 words**, organized in the 8 sections below. This
document is NOT the final report — it is the source-of-truth research that will
later be transcribed and condensed into 5 of the 16 sections of the final docx.

## Prerequisites

- Required inputs from SKILL.md provided by user (10-K, 10-Q, transcripts)
- `references/value-framework.md` read

## Workflow

1. **Ingest exhaustively.** Read every document in the user's input directory.
   Build internal notes on what's covered where.

2. **Identify the business model in one paragraph.** Before structuring anything
   else. What does the company sell, to whom, how does it get paid, what
   produces the unit of value. This anchors the entire research.

3. **Identify the sector explicitly.** From the business model, classify the
   sector. Then SELECT the 6-8 KPIs that actually matter for this sector — these
   become the metrics used throughout this document AND in Task 2 modeling.
   Examples (not exhaustive):
   - SaaS: NRR, gross retention, ARR growth, magic number, rule of 40, FCF margin
   - Apparel/retail: comps, revenue by geography, DTC vs wholesale mix, gross
     margin, inventory turns, store productivity (sales/sqft)
   - Insurance broker: organic growth, contingent commissions, EBITDAC margin,
     retention rate, M&A roll-forward
   - Exchange/data: recurring vs transactional revenue, daily ADV by asset
     class, subscription growth, operating leverage, FCF margin
   - Consumer staples: organic volume, price/mix, gross margin, working capital
   - Asset-light fee compounder: take rate, AUM growth, fee compression risk,
     incremental margin

4. **Write the 8 sections below** at the prescribed depth. Five of these are
   "extended" sections with hard minimum word targets — these are the analytical
   core and will become the bulk of the final report.

## Section Structure

### 1. Snapshot (300-500 words)
- Ticker, exchange, current price (from web search if not in filings), market
  cap, enterprise value
- Sector and business in one sentence
- Identified sector-specific KPI set (the 6-8 KPIs)
- Top 3 reasons to consider owning
- Top 3 reasons NOT to own
- 3 questions the rest of the research must answer

### 2. Industry & Sector Analysis (EXTENDED — 2,800-3,500 words)
Cover:
- **Market definition and sizing**: TAM, served market, current penetration
- **Historical and forward growth**: 10-year category growth, structural drivers,
  reasoned forward estimate; separate volume from price
- **Demand drivers**: demographics, income, behavior shifts, technology,
  regulation, durability of each
- **Industry structure**: concentration, profit pool location, profit pool shifts
- **Cyclicality**: secular, cyclical, seasonal; map performance through GFC, COVID,
  2022 inflation; where in the cycle now
- **Channel dynamics**: how product reaches end customer, mix evolution, margin
  capture by channel
- **Structural threats and tailwinds**: substitution, disruption, input costs,
  regulation direction, ESG pressure, geopolitics/tariffs where relevant
- **Closing judgment**: does this industry produce durable economic profit, and
  why or why not?

### 3. Company Profile & Business Model (EXTENDED — 2,800-3,500 words)
Cover:
- **Origin and evolution**: brief history, strategic pivots, what they reveal
  about company DNA
- **What it sells**: product/service portfolio, role of each line, lifecycle
- **Revenue architecture**: breakdown by segment, geography, channel, customer
  type. Mix today and 5-10 year shift
- **Per-segment depth**: for each meaningful segment — size, growth rate, margin
  profile, strategic importance
- **Unit economics**: revenue per customer/store/unit, contribution margin, CAC
  and LTV where applicable, payback period
- **Current segment performance**: which parts are accelerating, decelerating,
  pressured (last 4-8 quarters)
- **The economic engine**: the single mechanism that converts activity into cash;
  what could break it
- **Operating model**: sourcing/manufacturing, supply chain, asset intensity,
  cost structure (fixed vs variable), operating leverage
- **The "why us not them" sentence** — and a stress test of whether it will
  remain true for 10 years

### 4. Competitive Landscape (EXTENDED — 2,400-3,000 words)
Cover:
- **Map of competition**: direct, adjacent, potential entrants; top 3-6
  competitors with size, positioning, share, trajectory
- **Market share dynamics**: who's gaining, who's losing, mechanism behind
  the shift
- **Barriers to entry**: capital, brand, distribution, scale, regulation,
  switching costs, network effects. Honest assessment of height and direction
  of each barrier
- **The moat**: name moat type(s), assess width and durability, support with
  pricing power / margin stability / share retention evidence
- **Competitive intensity and rivalry**: pricing discipline, new-entrant threat,
  private-label / low-cost disruption
- **Honest verdict**: position strengthening, stable, or weakening — with support

### 5. Growth Strategy & Forward Outlook (EXTENDED — 3,000-4,000 words)
Cover:
- **Management's stated strategy**: explicit multi-year plan, targets, timeline.
  Summarize fairly, then assess critically.
- **Growth algorithm decomposition**: future growth decomposed into volume,
  price/mix, new geographies, new categories, channels, M&A. Quantify each.
- **Geographic expansion**: maturity per region, white-space remaining, execution
  risk, local competitive dynamics in key growth markets
- **New category / adjacency expansion**: track record beyond core, probability
  of success, expected incremental ROIC
- **Reinvestment runway**: how much capital, at what incremental ROIC, for how
  long. The compounder test.
- **Margin trajectory**: credible path to expansion (or compression risk); name
  the specific operating-leverage or mix mechanism
- **Forward financial outlook (qualitative)**: 10-year view of revenue growth,
  margins, capex, working capital, share count. These will become inputs to
  Task 2 modeling.
- **What has to go right**: the 3-5 things that must hold for the growth thesis
- **Saturation and maturity risk**: when and how growth slows; what the
  business looks like at maturity

### 6. Recent Issues & Pressure Points (EXTENDED — 2,000-2,800 words)
Identify and analyze the specific current issues for THIS company. Do not use a
generic checklist — pull from the filings, transcripts, and recent news.
Categories to probe:
- Growth deceleration (segment, geography, total): cyclical, competitive, or
  structural?
- Margin pressure: input costs, tariffs, mix shift, promotional intensity,
  deleverage — transient or permanent?
- Management / leadership disruption: executive departures, succession, board
  turnover, strategy turnover
- Product / operational problems: quality, recalls, missed launches, inventory,
  supply-chain disruption
- Competitive losses: share ceded to rivals, new entrants, pricing power erosion
- Demand / end-market weakness: soft consumer, regional underperformance,
  category out of favor
- Balance sheet / capital concerns: rising leverage, refinancing wall, bad
  buybacks, stretched working capital
- Legal / regulatory / governance / reputational issues
- Valuation / sentiment problems: price drawdown, multiple compression, short
  interest, narrative souring

For each material issue: description, mechanism, financial magnitude, transient
vs structural, management response, implications for thesis and intrinsic value.
Distinguish **noise** (look-through) from **signal** (changes the thesis).

### 7. Management & Governance (500-800 words)
- CEO and CFO: tenure, background, prior track record (specific roles, specific
  outcomes — not just résumé)
- Insider ownership %, founder involvement
- Compensation structure: short-term vs long-term, KPIs incentivized, dilution
- Board: composition, independence, governance red flags
- Communication quality: candor in letters and calls, willingness to admit error
- Capital allocation track record: 10-year decomposition (capex, M&A, buybacks,
  dividends, debt paydown) with ROI commentary. M&A prices paid vs business
  quality. Buyback discipline (low or high price purchases?).

### 8. Capital Allocation & Shareholder Returns Detail (500-800 words)
- Dividend: history, payout ratio, FCF cover, growth rate, yield vs own history
  and peers, sustainability. If no dividend, state why (reinvestment, lifecycle)
  and whether initiation is plausible.
- Buyback: history, average price paid vs intrinsic value (low or high?),
  authorization remaining, share count trajectory, accretion vs destruction
- Return-of-capital framework: how management thinks about returning vs
  reinvesting; rationality given reinvestment runway
- Per-share value creation: total shareholder yield, per-share metric compounding

## Quality Checks Before Concluding Task 1

Before saving the file, verify:
- [ ] All 8 sections present
- [ ] Five extended sections meet their word minimums
- [ ] Sector-specific KPIs identified and used consistently
- [ ] Every fact in extended sections is followed by an implication ("so what")
- [ ] No invented data — every number traces to a source document or web search
- [ ] Recent Issues distinguishes noise from signal
- [ ] No "BUY/HOLD/SELL" recommendation (that comes in Task 3)
- [ ] No price target (that comes in Task 3)
- [ ] No first-person plural ("we", "our view")

## Save and Hand Off

Save the file as `{TICKER}_research.md` in the working directory. Output a
one-paragraph summary noting:
- File saved (path)
- Sector identified
- Sector-specific KPIs selected
- 3 most important issues from Section 6
- Whether quality screen will likely pass (i.e., gut sense of whether full
  coverage is justified — formal scoring happens in Task 3)

Then proceed to Task 2 (or wait for user confirmation in M
