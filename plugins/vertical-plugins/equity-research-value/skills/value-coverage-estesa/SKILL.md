---
name: value-coverage-estesa
description: "Create institutional-quality value-investing initiating coverage reports in ITALIAN with the standardized house visual identity (ICE golden-reference layout: Italian section titles, navy/teal/amber chart palette, 'Figura N.' chart titling, page-1 summary table with Qualita/Fair value/MOS/Rating/IRR, Tabella-styled tables). Same 5-task workflow as value-coverage — (1) company research, (2) financial modeling, (3) valuation & quality scoring, (4) chart generation, (5) final report assembly — with verified prerequisites and reusable deliverables (markdown research doc, Excel models, PNG charts, final DOCX). Audience is a private long-term value investor (5-10 year horizon). Quality-first framework, point estimate of fair value, MOS-based rating, operational price levels. Use when user requests 'copertura value', 'value coverage estesa', 'report standard', 'value coverage formato ICE', or a value coverage explicitly in Italian / in the house style. This is the user's preferred default edition for finished reports. Reports must be very extensive and in-depth: 45-55 pages, 16,000-22,000 words minimum — the user is making real investment decisions and requires exhaustive analysis."
---

# Value Coverage Estesa — Multi-Task Workflow (Standardized House Style)

This skill produces an institutional-quality value-investing initiating coverage
report through a 5-task workflow. Each task produces specific deliverables that
feed into subsequent tasks. The final output is a deep-dive `.docx` report
(45-55 pages, 16,000-22,000 words), supported by a research markdown document,
two Excel models, and 10-16 PNG charts — all preserved as reusable artifacts.

## Why a Multi-Task Workflow

Producing a 35-page report in a single generation has three problems: late
sections drift in quality as context fills, intermediate artifacts (Excel models,
research notes) are not preserved for reuse in later quarterly updates, and
mid-stream errors require re-generating the entire output. The 5-task workflow
solves all three by checkpointing deliverables, enforcing prerequisites, and
allowing surgical re-runs of individual tasks.

## The Five Tasks

| Task | Name | Output | Dependencies |
|------|------|--------|--------------|
| 1 | Company Research | `{TICKER}_research.md` | None |
| 2 | Financial Modeling | `{TICKER}_model.xlsx` | Task 1 |
| 3 | Valuation & Quality Scoring | `{TICKER}_valuation.xlsx` | Tasks 1, 2 |
| 4 | Chart Generation | `charts/*.png` (10-16 files) | Tasks 1, 2, 3 |
| 5 | Final Report Assembly | `{TICKER}_value_coverage_{YYYY-MM-DD}.docx` | Tasks 1, 2, 3, 4 |

Detailed specifications for each task are in:

- `tasks/01-research.md`
- `tasks/02-modeling.md`
- `tasks/03-valuation.md`
- `tasks/04-charts.md`
- `tasks/05-assembly.md`

The underlying value framework (quality scoring rubrics, DCF formulas, MOS
matrix, rating logic, price level rules) is defined in:

- `references/value-framework.md`

The visual and editorial identity (Italian language conventions, document
layout, table styling, chart palette, figure composition) is defined in:

- `references/style-guide.md`

Read the framework FIRST, then read the task definition before executing any
task. Tasks 4 and 5 must ALSO read the style guide before producing any chart
or document output — every report must be visually identical to the golden
reference (the ICE June 2026 report).

## Required Inputs

Before starting Task 1, the user must provide:

1. **Ticker and exchange** (mandatory)
2. **Latest 10-K or 20-F** (mandatory)
3. **Latest 10-Q or interim** (mandatory)
4. **Last 4-8 earnings call transcripts** (strongly recommended)

Optional but valuable:

5. Investor Day / strategic plan deck (last 2 years)
6. Peer company 10-Ks (top 3-5 peers)
7. Past management letters / shareholder letters

If any required input is missing, ASK ONCE at the start of Task 1 — do not
proceed with web-search-only data for an initiating coverage. Documents in a
user-provided directory (e.g., `~/Downloads/{TICKER}_research/`) should be read
exhaustively and prioritized over web search.

## Execution Modes

The skill supports three execution modes. **At the very start of every
invocation, BEFORE doing any work, ALWAYS ask the user which mode they want.**
Do not assume a default and do not begin Task 1 until the user has answered.
Present the choice concisely, for example:

> Prima di iniziare la copertura di [TICKER], come vuoi procedere?
> 1. **Task per task** (consigliato) — eseguo una fase alla volta, ti mostro il
>    deliverable e aspetto il tuo ok prima di passare alla successiva. Ideale
>    per controllare la profondità della ricerca e correggere subito.
> 2. **Tutto insieme** — eseguo le 5 fasi in sequenza e ti consegno tutti i
>    deliverable (research, modello, valutazione, grafici, report finale) in
>    un'unica volta.
> 3. **Solo una fase** — se hai già dei deliverable e vuoi rigenerarne solo uno
>    (es. solo la valutazione, o solo i grafici), dimmi quale.

The only time you may skip this question is when the user has ALREADY specified
the mode in their triggering message (e.g. "fai ICE task per task" or "fai ICE
tutto insieme") — in that case honor what they said and proceed.

The exception: even when asking, if the user's message already names a single
task to re-run ("rifai solo la valutazione di ICE"), treat it as Mode C and
proceed after confirming which prior artifacts exist.

### Mode A — All-In-One
The skill runs all 5 tasks sequentially, checkpointing each artifact along the
way, and delivers the final docx plus all intermediate files. The sequence is
still preserved (each task reads the prior task's output before proceeding).

### Mode B — Task-by-Task (recommended)
Execute one task per turn. After completing each task, present the deliverable,
summarize the key outputs, and explicitly state which task is next and what
artifacts will be produced. Wait for user confirmation before proceeding to the
next task. This is the recommended mode for the FIRST coverage on a new company,
where the user may want to review the research doc before greenlighting the
modeling phase. Given the 45-55 page length mandate, this mode also lets the
user verify the research doc actually reaches its 9,000-13,000 word target
before the rest of the report is built on top of it.

### Mode C — Single Task Re-Run
The user has previously produced some artifacts and wants to re-run only one
task (e.g., re-do valuation after multiple expansion, or regenerate charts after
updating the model). Verify which prior-task artifacts exist, read them as
prerequisites, then execute only the requested task. State explicitly which
downstream tasks will need to be re-run for consistency.

## Workflow Enforcement Rules

1. **Never skip the framework read.** Before any task, read
   `references/value-framework.md`. The framework defines quality scoring rubrics,
   formulas, the MOS-to-rating mapping, and the price level rules — without
   them the task outputs are not coherent.

2. **Verify prerequisites before executing a task.** Tasks 2-5 require artifacts
   from earlier tasks. If a prerequisite artifact is missing in Modes B/C, state
   so and ask the user to provide it or re-run the earlier task. Do not improvise.

3. **Checkpoint outputs.** After every task, save the deliverable to disk as a
   standalone file with the standard naming convention (see each task spec).
   These files are the user's reusable artifacts — the Excel model from Task 2
   becomes the basis for `/earnings-analysis` next quarter.

4. **Honor the depth mandate.** Five sections of the final report are
   substantially deeper than a standard report (Industry, Business Model,
   Competitive Landscape, Growth Strategy, Recent Issues). The research doc
   from Task 1 must already cover them at depth — Task 5 then transcribes and
   refines, it does not invent.

5. **Use primary documents over web search.** For data Claude can extract from
   the user's filings or transcripts, use the filings. Only resort to web search
   for data not present in the documents (current price, consensus estimates,
   sector news post-filing, peer comparables not provided).

6. **Stop and ask if a quality threshold fails.** Per the framework, if the
   quality score in Task 3 comes in below 18/30, halt the workflow and surface
   this finding to the user before completing the report — for low-quality
   businesses, a full coverage report is not justified, only a brief "not a
   candidate" summary.

## Output Naming Conventions

All artifacts go in the user's working directory (defaults to the input
directory if provided, e.g., `~/Downloads/{TICKER}_research/`). Standard names:

- `{TICKER}_research.md`
- `{TICKER}_model.xlsx`
- `{TICKER}_valuation.xlsx`
- `charts/{descriptive-chart-name}.png` (one PNG per chart)
- `{TICKER}_value_coverage_{YYYY-MM-DD}.docx`

## Default Behavior on Ambiguous Triggers

When the user says "copertura value di X", "value coverage estesa X", or
"/equity-research-value:value-coverage-estesa X" WITHOUT naming a mode, do NOT
start working. First ask which execution mode they want (see "Execution Modes"
above), then proceed according to their answer.

If the user's triggering message already names the mode — "fai X task per task",
"fai X tutto insieme", "rifai solo la valutazione di X" — skip the question and
honor it directly.

If the user references existing artifacts ("ho già il modello, rifai solo la
valutazione"), treat as Mode C and proceed after confirming which artifacts
exist.

**Sibling skill disambiguation**: this skill is the standardized Italian
house-style edition. A sibling skill `value-coverage` exists in the same
plugin with the same 5-task workflow but without the binding style guide.
If the user explicitly asks for the generic/English edition or free
formatting, defer to `value-coverage`. For ambiguous requests, prefer THIS
skill — it is the user's stated default for finished reports.

## References

- `tasks/01-research.md` — Task 1 detailed spec
- `tasks/02-modeling.md` — Task 2 detailed spec
- `tasks/03-valuation.md` — Task 3 detailed spec
- `tasks/04-charts.md` — Task 4 detailed spec
- `tasks/05-assembly.md` — Task 5 detailed spec (final docx structure)
- `references/value-framework.md` — quality rubrics, formulas, MOS matrix, rating logic
- `references/style-guide.md` — visual/editorial identity: Italian conventions, layout, tables, chart palette
