# Style Guide — Value Coverage Reports

This document codifies the visual and editorial identity of value-coverage
reports. It was extracted from the ICE initiating coverage (June 2026), which
serves as the golden reference. Every report produced by this skill MUST follow
these specifications so that all reports in the user's library are visually
identical. Tasks 4 (charts) and 5 (assembly) must read this file before
producing any output.

---

## 1. Language and Numeric Conventions

- **Report language: Italian.** All section titles, table headers, chart
  titles, axis labels, captions, and prose are written in Italian. (If the user
  explicitly requests another language, follow the request — but Italian is the
  default.)
- **Decimal separator: comma.** "$142,00", "11,5%", "4,3x", "0,95".
- **Thousands separator: period.** "9.931", "47.776".
- **Magnitudes:** "mld" for billions ("$9,9 mld"), "mln" for millions
  ("$859 mln"). Dollar sign before the number.
- **Negative numbers:** parentheses in tables; minus sign acceptable in prose.
- **Standard Italian section titles** (use exactly these — 17 sections):
  1. Quadro di sintesi
  2. Analisi del Settore
  3. Profilo Societario e Modello di Business
  4. Panorama Competitivo
  5. Valutazione della Qualità
  6. Strategia di Crescita e Prospettive Future
  7. Criticità Recenti e Punti di Pressione
  8. Evoluzione su 8 Trimestri
  9. Analisi Finanziaria
  10. Proiezioni e DCF
  11. Triangolazione di Valutazione
  12. Margine di Sicurezza, Rating e Livelli di Prezzo
  13. Allocazione del Capitale e Ritorni per gli Azionisti
  14. Rischi
  15. Scenari Bull / Base / Bear
  16. Management e Governance
  17. Catalizzatori e Monitoraggio
  + closing unnumbered section: "Metodologia e Fonti"
  Note: the golden-reference ICE report predates the transcript phase and shows
  only 16 sections (no "Evoluzione su 8 Trimestri"). Use ICE for VISUAL identity
  only; the canonical section structure is the 17-section list above. Section 8
  "Evoluzione su 8 Trimestri" is built from the Task 2 transcript-evolution
  deliverable and sits between "Criticità Recenti" (7) and "Analisi
  Finanziaria" (9).
- **Standard rating labels in Italian:** Strong Buy / Accumulare / Mantenere /
  Evitare. (Keep "Strong Buy" in English; translate the other three.)
- **Standard recurring phrases:** "Copertura Value — Report di Avvio" (report
  type), "Solo per uso privato. Non è una consulenza d'investimento."
  (disclaimer), "Fair value (obiettivo)", "Prezzo d'acquisto (posizione piena)",
  "Prezzo di alleggerimento".

## 2. Document Layout (.docx)

### Page setup
- Times New Roman. Body 11pt, justified, single-spaced.
- Section headers (H1): 14pt bold, numbered ("9. Analisi Finanziaria").
- Subsection headers (H2): 12pt bold italic, colored teal-blue (#1F7A8C or
  similar) — e.g. "Architettura dei ricavi: la spina dorsale
  ricorrente-vs-transazionale".
- Margins 1 inch. Page numbers bottom right within the footer line.

### Header (every page except none — ICE report has it on all pages)
Centered, small caps / bold, 8-9pt, navy:
"NOME AZIENDA (NYSE: TICKER) · Copertura Value — Report di Avvio"
with a thin horizontal rule below.

### Footer (every page)
Left: "Solo per uso privato. Non è una consulenza d'investimento."
Right: "TICKER · N" (page number). Small grey 8pt.

### Page 1 (title block — no separate title page)
In order:
1. Company full name, large bold (e.g. "Intercontinental Exchange, Inc.")
2. Line: "NYSE: TICKER · Avvio di Copertura in Ottica Value"
3. **Thematic tagline in italic** — one sentence capturing the thesis (e.g.
   "Un'azienda eccellente a un prezzo equo — il de-rating di un compounder di
   infrastrutture critiche"). Every report MUST have one; it is the hook.
4. Line: "Data del report: [data] · Prezzo all'analisi: $X · Orizzonte: 5–10 anni"
5. **Summary table, 5 columns**: Qualità | Fair value | Margine di sicurezza |
   Rating | IRR attesa 10a — one data row (e.g. "26 / 30 | $168 | 15,5% |
   ACCUMULARE | ~11,7%"). Header row navy with white text.
6. One-paragraph "Settore / L'attività in una frase" block.
7. **Indice** (table of contents) with dot leaders and page numbers.

### Tables
- Numbered and titled above: "Tabella N. Titolo" in navy bold.
- Header row: navy background (#1F4E79), white bold text.
- Alternating row shading: white / very light grey-blue (#F2F5F9).
- Thin single borders. First column bold when it is a label column.
- Keep 1-3 tables per section; only when they earn their place.

### Figures in the document
- Insert the PNG inline at the relevant point in prose.
- Below each figure, a caption in small italic grey:
  "Figura N. [descrizione estesa con il 'so what']."
- Figure numbering is global and sequential across the report.

## 3. Chart Style (PNG generation — Task 4)

### Canonical palette (hex)
- **Navy (primary series / structure):** #1F4E79
- **Teal (secondary series):** #2E8B8B
- **Amber/gold (highlight, the subject company in peer comparisons, weighted
  result bars):** #E8A33D
- **Light blue (tertiary / lighter series):** #9DC3E6
- **Green (positive thematic series, e.g. energy momentum, adjusted profit
  lines):** #2E9E4F
- **Red (negative/GAAP-loss series, bear scenario):** #C0392B
- **Grey (reference lines, sources):** #808080, dashed for reference lines.
- Heatmaps: blue gradient (light → navy), with the base case visually centered.

### Composition rules
- **Title INSIDE the PNG**, top-left or centered: "Figura N. Titolo descrittivo"
  — navy, bold, ~14pt. The figure number is part of the chart image.
- **Source INSIDE the PNG**, bottom-left, small italic grey:
  "Fonte: ICE 10-K FY2025, 10-Q Q1-2026, comunicati earnings." (adapt to the
  actual sources of that chart).
- Value labels on bars where readable ("$9,9 mld", "+60%", "18,1").
- Reference lines as grey/green dashed with small label (e.g. "Media ICE 10
  anni 24,5x", "Soglia equity 8%", "Obiettivo ≤3,0x").
- In peer comparison charts, the subject company's bar is AMBER, peers are navy.
- In scenario charts: bear red, base navy, bull green, weighted amber.
- Forecast periods: same hue, lighter shade or dashed.
- Horizontal light gridlines only; top/right spines hidden.
- Axis labels and everything textual in Italian with Italian number formats.
- Dimensions: 1600x1000 px @150 DPI (figsize=(10.67, 6.67), dpi=150).

### matplotlib implementation notes
- Use `matplotlib.ticker.FuncFormatter` to render Italian decimal commas
  (e.g. lambda x, _: f"{x:,.1f}".replace(",", "X").replace(".", ",").replace("X", "."))
- Embed the figure number in the title string when saving each PNG; keep a
  running counter consistent with the insertion order planned for Task 5.

## 4. Editorial Style

- Long-form analytical prose; every section opens with a framing paragraph.
- Bold for key inline concepts; italics for the tagline and rhetorical pivots.
- Each "extended" section closes with an explicit verdict ("Verdetto: ...",
  "È rumore o segnale?", "La riconciliazione in una riga...").
- The pressure-points section uses the fixed rubric "Punto di pressione N — ..."
  and closes each with the noise-vs-signal judgment.
- The final "Metodologia e Fonti" section lists primary sources (treated as
  authoritative), secondary sources, the method weights actually used, and the
  standard disclaimer that the rating is the mechanical output of the MOS
  decision matrix, not a sell-side rating.

## 5. File Naming

- Report: `{TICKER}_value_coverage_{YYYY-MM-DD}_IT.docx`
- Charts: `charts/{TICKER}_{slug}.png` (slug in English, content in Italian)
- Research doc, model, valuation files keep their Task 1-3 names.
