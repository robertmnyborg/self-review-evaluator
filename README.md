# self-review-evaluator

A Claude Code skill that evaluates a self-review against your company's leveling framework: a calibrated per-dimension rating, a gap analysis to the next level, probing questions, and a development plan.

Bring your own framework. The skill asks for your career ladder (file path, pasted text, or URL) and rates against its exact language. A short generic example ladder is included for anyone who doesn't have one.

## Install

```bash
git clone <this repo> self-review-evaluator
cp -R self-review-evaluator/skills/* ~/.claude/skills/
```

Requirements: Claude Code.

## What it does

**Failure it prevents:** rating inflation. An unguarded agent reads a self-review generously, infers scope and impact that were never stated, and hands back a flattering assessment that mis-levels the person.

**How:**

1. **Map.** Every project in the review gets a table of dimension, rating, and a quoted piece of evidence. No quote means "Not Evidenced," which is the default for every dimension.
2. **Probe.** Every thin cell becomes 2-4 targeted questions. Only a concrete answer raises a rating; generosity never does.
3. **Assess.** Per dimension, quote the framework's current-level and next-level language and state Met, Partially Met, or Not Met, with the specific gap.
4. **Plan.** A 30-day track to solidify the current level, a 60-90 day track for the 2-3 biggest gaps, and rewrite suggestions that reframe work the person actually did.

The skill pauses for you after inputs, after the probing questions, and before the plan.

**Use it:** "evaluate my self-review", "assess my level", "gap analysis on my review", "am I ready for promotion".

## The example ladder

`skills/self-review-evaluator/references/example-ladder.md` is a generic five-level individual-contributor ladder with five dimensions (scope, impact, craft, execution, influence). It was written for this skill from general industry practice and is not any company's framework. Results against it are labeled as such. Use your real ladder whenever you have one.

## License

MIT. See `LICENSE`.
