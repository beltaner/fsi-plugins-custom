---
name: value-coverage-estesa
description: "Produce a value-investing initiating coverage report in Italian with the standardized house visual identity (ICE golden-reference layout, navy/teal/amber charts, Italian section titles). Same 5-task workflow as value-coverage. This is the preferred edition for finished reports."
argument-hint: <TICKER>
---

Activate the `value-coverage-estesa` skill located at `plugins/vertical-plugins/equity-research-value/skills/value-coverage-estesa/SKILL.md` and apply it to produce a complete value coverage report on the ticker provided as argument: $ARGUMENTS.

Read the full SKILL.md instructions, the supporting framework at `plugins/vertical-plugins/equity-research-value/skills/value-coverage-estesa/references/value-framework.md`, AND the style guide at `plugins/vertical-plugins/equity-research-value/skills/value-coverage-estesa/references/style-guide.md` before starting. Follow the 5-task workflow, the depth mandate, the rating logic, the price level rules, and the visual/editorial identity defined therein without deviation. The final report must be in Italian and visually identical to the golden reference (ICE June 2026 report).

If the user has provided primary documents (10-K, 10-Q, transcripts, investor day deck, peer 10-Ks), prioritize them over web search. If documents are missing, ask the user once at the start which ones they can provide before proceeding.

Produce all five deliverables (research markdown, model xlsx, valuation xlsx, PNG charts, final docx) following the naming conventions and output formats specified in the skill and style guide.
