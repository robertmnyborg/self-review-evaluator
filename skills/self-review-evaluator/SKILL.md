---
name: self-review-evaluator
description: Evaluate an employee self-review against a leveling framework (career ladder) the user supplies, producing a calibrated per-dimension rating, a gap analysis to the next level, probing questions, and a development plan. Use when asked to "evaluate my self-review", "assess my level", "gap analysis on my review", "am I ready for promotion", or to check a self-review against a career ladder.
---

# Self-Review Evaluator

Assess a self-review against a leveling framework: rate each dimension at the person's current level, find the gaps to the next level, probe for missing evidence, and produce a development plan.

## Calibration discipline: read this first, it overrides everything below

The failure mode of this assessment is **rating inflation**: being generous, inferring scope the review doesn't state, giving credit for work that is implied but not shown. Inflation produces a flattering, useless assessment and mis-levels people. Guard against it structurally:

- **Default every dimension to "Not Evidenced."** A rating moves up only when the review (or a probing answer) contains *specific, quoted evidence* for it. Absence of evidence is "Not Evidenced," never a charitable guess.
- **Rate the evidence, not the person.** "They're clearly senior" is not a rating; a quote showing they owned a cross-team decision is.
- **Probing raises ratings, generosity never does.** When a dimension is thin, that is a *question to ask*, not a gap to paper over. Only a concrete answer upgrades the rating.
- **Never infer unstated scope or impact.** If the review says "built the export feature," do not assume it was ambiguous, high-impact, or cross-team. Ask.
- If you can't ground a rating in a quote, write "Not Evidenced: needs probing." That is the correct, honest output, not a cop-out.

A self-review that genuinely shows little will produce a mostly "Not Evidenced" map. That is a *true* result, and the probing phase exists to fix under-documentation without inflating.

## Inputs

Ask for, in one message:

1. **The leveling framework.** A file path, pasted text, or a URL to the company's career ladder for the person's role. Read it fully before rating anything.
2. **Role and current level**, using the framework's own level names.
3. **The full self-review text.**
4. Optionally, the person's name (used only in headings).

**If the user has no framework**, say so plainly and offer `references/example-ladder.md`, a generic five-level individual-contributor ladder. Label every output built on it "rated against a generic example ladder, not your company's framework," because the result is only as meaningful as the ladder.

**Load the framework before rating.** Identify the current level and the next level. Extract the framework's dimensions (it may call them competencies, axes, pillars, or areas) and use exactly those, in the framework's words. Don't import dimensions from the example ladder or anywhere else. If the framework has no next level (top of ladder), assess at-level depth only and say so. If the framework can't be read, say so and stop; do not rate from general knowledge.

## Ratings

Per dimension: **Above Level · At Level · Developing · Not Evidenced** (default).

- **Above Level:** quoted evidence matches the *next* level's language.
- **At Level:** quoted evidence matches the current level's language.
- **Developing:** evidence exists but falls short of the current level's language.
- **Not Evidenced:** no quote supports any rating yet.

## Flow

1. **Map.** Extract each project or piece of work from the review. Per project, one table: Dimension | Rating | *Quoted evidence*. The evidence cell must be a real quote or a close summary of their text; if you can't fill it, the rating is Not Evidenced. Then a summary matrix: dimensions down, projects across, plus an overall column.
2. **Probe.** For every Not Evidenced or Developing cell, ask 2-4 targeted questions covering scope and complexity, independence and leadership, impact and results, and communication and visibility. Present all questions at once, wait for answers, then re-map, showing what changed and the new evidence behind each upgrade.
3. **Assess.** Per dimension, quote the framework's exact current-level and next-level language, state Met / Partially Met / Not Met, and name the specific gap. Summarize evidenced strengths and the critical gaps to the next level, in the framework's language.
4. **Plan.**
   - Track A, solidify the current level (30 days), for Partially Met and Not Met dimensions.
   - Track B, grow toward the next level (60-90 days), for the 2-3 biggest gaps.
   - Each item has a goal, a concrete action, a success signal, and a timeline.
   - Close with 3-5 specific rewrite suggestions for how to reframe the work the person actually revealed. Never suggest claiming work they did not describe.

Stop and wait for the user after gathering inputs, after the probing questions, and before the plan.

## Gotchas

- **Quote or it didn't happen.** Every rating and every piece of feedback cites a specific project, quote, or probing answer. Generic career advice means you skipped the grounding.
- **"Not Evidenced" is not "Not Done."** The person may have done strong work and under-documented it; that is what probing is for. Resolve it by *asking*, not assuming.
- **Don't skip framework quotes.** The value is grounding in the organization's actual leveling language. Without the quotes this is vibes.
- **Don't rush probing.** It often surfaces a large share of the real evidence. Thin probing is the main cause of a bad assessment.
- **Use the framework's words, not yours.** If the ladder says "drives alignment across teams," the gap statement uses that phrase, not a paraphrase.
- **Frameworks differ in shape.** Some list behaviors per level, some describe only deltas between levels, some separate "expectations" from "examples." Rate against the expectations; treat examples as illustrations, not a checklist.
