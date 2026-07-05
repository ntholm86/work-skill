# work-skill

**Real work, fully auditable, in one file.** `work` is a standalone, target-agnostic improvement-reasoning skill: point an agent at anything it can reason about — code, documents, plans, letters, music — and it examines, improves, and records every reasoning step in an auditable trail. The whole skill is one readable markdown file: [`work/SKILL.md`](./work/SKILL.md). No installer, no tooling, no dependencies — by design, permanently.

It is built on the three [Principles of Earned Autonomy](https://github.com/ntholm86/principles-of-earned-autonomy):

1. **Operator's Intent** — the agent is given a destination, not a route.
2. **Observable Autonomy** — every reasoning step is recorded as it happens; an observer can reconstruct what was done and why from the trail alone.
3. **Convergence Is Silence** — finding nothing actionable is a valid outcome; ceremony is never manufactured to look thorough.

## Why

Its parent, the full [skills suite](https://github.com/ntholm86/principles-of-earned-autonomy-skills-suite), delivers the same discipline as five separate skills (`intent`, `improve`, `destination`, `orient`, `trail`) — and proved the capability, but priced itself out of daily use: five skill-loads and full ceremony on every run, even a one-line fix. `work` is the consolidation — one skill-load, one loop, with reasoning depth scaled to the stakes of the moment instead of a fixed template:

- **Intent** — folded into the loop's own first step, narrated only when the interpretation is genuinely uncertain.
- **Improve** — the base loop (examine → challenge → decide → act → reflect), depth-scaled to the stakes of the change.
- **Destination** — a "mini" bootstrap: asks one short question on first contact with a target that has no `.acm/destination.md` yet — and can re-trigger *itself* when its own evidence says the destination is exhausted or wrong, while the operator always owns what the destination becomes.
- **Orient** — a condensed arc-read the skill triggers itself when the work signals a need (contradictions, pushback, a stretch closing, staleness), with an entry-count backstop catching what judgment misses.
- **Trail** — always happens, every run, with a variable-depth entry format (Micro / Standard / Full) so routine work costs little and real decisions still get full reasoning.

The skill leads the workflow, not the operator: it announces what it's doing and why, and names the one decision that belongs to the operator at each moment. `probe` (contamination / pattern-matching detection) is intentionally excluded from this consolidation — a settled decision, not a placeholder.

## Status

v3.1.0 — the operator's confirmed daily-usage skill, and dogfooded hard: the skill has been pointed at itself and at external targets (a Python code repo where it made a test-verified source change, and editorial/content repos), with every run — including its own design decisions — recorded in this repo's trail. Scored against its own destination on a dual-axis (capability × cost) evidence-cited scorecard; ratings and their deltas live in [`.acm/orientation.md`](./.acm/orientation.md). A second design bar applies alongside the operator's own use: **a stranger should be able to pick up `work/SKILL.md` and use it without the author explaining anything** — jargon or unexplained references to the parent suite are treated as defects. See [`.acm/destination.md`](./.acm/destination.md) for the full mandate and open items, and [`.acm/audit-trail.md`](./.acm/audit-trail.md) for the complete record of how this repo came to be — including the wrong turns.

## Use

Point an agent at [`work/SKILL.md`](./work/SKILL.md) — copy the `work/` folder into wherever your agent loads skills from (such as `~/.copilot/skills/`), or just paste the file into a prompt. There is no installer, and there won't be one — by design. The whole point is that it's just a skill: one readable file, no build step, no script to trust between reading it and using it.
