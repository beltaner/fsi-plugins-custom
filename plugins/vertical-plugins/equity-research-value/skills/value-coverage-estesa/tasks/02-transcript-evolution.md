# Task 2 — Transcript Evolution Analysis (8-Quarter)

> File name: `tasks/02-transcript-evolution.md`. In the workflow this is the
> SECOND task, executed after Task 1 (research) and before Task 3 (financial
> modeling).

## Goal

Produce a dedicated, systematic quarter-by-quarter reading of the company's
last earnings call transcripts (target: last 8 quarters; adapt to however many
are provided — see "Adaptive Quarter Count"). The objective is to capture the
EVOLUTION of the management narrative over time: how each pressure point and
each growth driver has been discussed quarter after quarter, whether the tone
has strengthened or weakened, what has newly appeared, and what has quietly
dropped out of the discussion. This temporal signal is what a static analysis
misses and what a long-term holder most needs.

This task produces its own standalone deliverable, which Task 6 (assembly)
transcribes into a dedicated report section ("Evoluzione su 8 Trimestri").

## Output

A markdown file at: `{TICKER}_transcript_evolution.md`

Target length: **3,500-4,500 words** plus the evolution tables (this feeds a
full 3+ page section in the final report, so the material must be substantial).
This is an
ADDITIVE deliverable — it does NOT reduce the depth or word targets of any
other section. The final report grows by one section; the other sections keep
their full length.

## Prerequisites

- Task 1 complete: `{TICKER}_research.md` read (so the analysis is informed by
  the business model, segments, and the pressure points already identified)
- The user's earnings call transcripts available in the input directory
- The user-specified pressure points / watch items from the triggering prompt
  (the themes the user always wants tracked — e.g. for ICE: Black Knight
  integration, FMX, mortgage cycle, leverage). If the user named specific
  themes, those are MANDATORY tracked items.
- `references/value-framework.md` read (noise-vs-signal discipline applies here)

## Adaptive Quarter Count

- The default and target is the **last 8 quarters**.
- If fewer than 8 transcripts are provided, use all available and state clearly
  at the top of the deliverable how many quarters were analyzed (e.g. "Analisi
  basata su 5 trimestri disponibili: Q1-2025 → Q1-2026").
- If MORE than 8 are provided, use the most recent 8 unless the user asks for
  more; note that older quarters are available if a longer history is wanted.
- Never fabricate a quarter that was not provided. If there are gaps in the
  sequence (e.g. a missing quarter), note the gap explicitly.

## Workflow

1. **Read prerequisites.** Open `{TICKER}_research.md` to anchor on the business
   model, segments, and the already-identified pressure points. Note the
   user-specified watch items from the prompt.

2. **Inventory the transcripts.** List which quarters are available, in
   chronological order. Confirm the count and the date range.

3. **Define the tracked-theme set.** This is a UNION of two sources:
   - **(a) User-specified watch items** — the pressure points the user named in
     the prompt. These are mandatory; track every one across all quarters.
   - **(b) AI-identified themes** — themes that recur across the transcripts or
     that emerge as newly important, even if the user did not name them.
     Identify these by reading for: topics raised repeatedly by management,
     topics analysts keep asking about, new initiatives introduced mid-series,
     guidance changes, and any shift in language/tone. Aim for 4-7 total tracked
     themes (user items + AI items combined), enough to be comprehensive without
     diluting focus.
   - State explicitly which themes came from the user and which the AI added,
     and why each AI-added theme was deemed important.

4. **Read each quarter for each theme.** For every tracked theme, trace how it
   was discussed in each available quarter: what management said, the metric or
   data point cited, the tone (confident / cautious / defensive / silent), and
   any change versus the prior quarter. Read the analyst Q&A, not just prepared
   remarks — the questions reveal what the market is worried about, and the
   answers reveal management candor.

5. **Judge the trajectory of each theme.** Across the full window, classify each
   theme as IMPROVING, STABLE, or DETERIORATING, with a one-line justification
   grounded in the quarter-by-quarter evidence. Distinguish genuine trend from
   single-quarter noise (framework's noise-vs-signal discipline).

6. **Surface narrative shifts.** Explicitly call out:
   - Themes that NEWLY appeared in the discussion (e.g. a topic absent until
     2 quarters ago) — often an early signal.
   - Themes that QUIETLY DISAPPEARED (management stopped mentioning something
     they used to emphasize) — sometimes a quiet warning, sometimes resolution.
   - Guidance trajectory: how forward guidance evolved quarter to quarter
     (raised, lowered, reaffirmed) and whether management consistently hit it.
   - Tone shifts: where management language became notably more confident or
     more guarded on a given theme.

7. **Write the deliverable** in the structure below.

## Deliverable Structure

### 1. Intestazione e perimetro (~150 words)
- Number of quarters analyzed and the exact date range
- The tracked-theme set, split into "richiesti dall'utente" and "individuati
  dall'analisi", with one line on why each AI-added theme matters
- Any gaps in the transcript sequence

### 2. Tabella evolutiva dei temi (the core table)
A matrix: rows = tracked themes, columns = quarters (oldest → newest). Each cell
is a terse note capturing how that theme stood that quarter (a metric, a tone
word, a one-clause status). The rightmost column is "Traiettoria" =
IMPROVING / STABLE / DETERIORATING. This table is the visual heart of the
section and must be readable at a glance.

### 3. Narrativa per tema (~2,400-3,200 words)
One subsection per tracked theme. For each:
- How it evolved across the window, quarter by quarter, in prose
- The metric trajectory where applicable (e.g. "le sinergie Black Knight sono
  passate da $55M nel Q4-2024 a ~$100M nel Q4-2025")
- The tone trajectory (became more/less confident, and where the turn happened)
- The verdict: IMPROVING / STABLE / DETERIORATING and what it implies for the
  thesis and for intrinsic value — noise or signal?

### 4. Temi emergenti e temi scomparsi (~450-650 words)
- New themes that entered the narrative recently (and what they may foreshadow)
- Themes management stopped discussing (resolution or quiet warning?)
- Any notable tone reversals

### 5. Sintesi: direzione complessiva (~400-550 words)
- The overall trajectory across all themes: is the management narrative, taken
  as a whole, strengthening or weakening over the 8 quarters?
- Which 2-3 themes are the most important to keep watching, and the specific
  next-quarter signal for each
- A one-paragraph judgment on whether the temporal evidence supports, qualifies,
  or contradicts the thesis built in the static sections

## Quality Checks Before Concluding Task 2

- [ ] Quarter count stated explicitly; adapts to actual transcripts provided
- [ ] All user-specified watch items tracked across every available quarter
- [ ] 4-7 total themes, with user vs AI origin labeled
- [ ] Evolution table present, rows=themes, cols=quarters, trajectory column
- [ ] Each theme has a per-quarter trace AND a trajectory verdict
- [ ] Analyst Q&A read, not just prepared remarks
- [ ] Newly-appeared and disappeared themes surfaced
- [ ] Guidance trajectory and tone shifts documented
- [ ] Noise-vs-signal judgment applied per theme
- [ ] No fabricated quarters; gaps noted
- [ ] This deliverable is additive — it does not shorten other sections

## Save and Hand Off

Save as `{TICKER}_transcript_evolution.md`. Output a one-paragraph summary
noting: file saved, number of quarters analyzed, the tracked-theme set, the
2-3 themes with the most decisive trajectory (improving or deteriorating), and
the overall direction of the management narrative.

Then proceed to Task 3 (financial modeling) or wait for user confirmation in
Mode B.
