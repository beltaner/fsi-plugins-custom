---
name: value-coverage
description: "Produce a value-investing initiating coverage report on a single equity. Quality-first framework, fair value point estimate, MOS-based rating, operational price levels. Generic across sectors."
argument-hint: <TICKER>
---

Activate the `value-coverage` skill located at `plugins/vertical-plugins/equity-research/skills/value-coverage/SKILL.md` and apply it to produce a complete value coverage report on the ticker provided as argument: $ARGUMENTS.

Read the full SKILL.md instructions and the supporting framework at `plugins/vertical-plugins/equity-research/skills/value-coverage/references/value-framework.md` before starting. Follow the report structure, depth mandate, rating logic, and price level rules defined therein without deviation.

If the user has provided primary documents (10-K, 10-Q, transcripts, investor day deck, peer 10-Ks), prioritize them over web search. If documents are missing, ask the user once at the start which ones they can provide before proceeding.

Produce the final report as a `.docx` file following the output format specified in the skill.
