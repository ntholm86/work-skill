# think-it-through-skill

A cost-optimized, single-file fork of the [pea/skills](../skills/) suite. Where the full suite is five separate skills (`intent`, `improve`, `destination`, `orient`, `trail` — plus `probe`), `think-it-through-skill` is **one skill**: [`think-it-through/SKILL.md`](./think-it-through/SKILL.md).

## Why

The full suite was built during a period where token cost wasn't the binding constraint. In practice, most sessions only ever invoke Intent and Improve, chained together, with Trail always following. Loading and running five skill files' worth of ceremony for that common case costs more than it needs to. `think-it-through` merges:

- **Intent** — folded into the loop's own first step, narrated only when the interpretation is genuinely uncertain.
- **Improve** — the base loop (examine → challenge → decide → act → reflect), depth-scaled to the stakes of the change.
- **Destination** — a "mini" bootstrap: only runs if the target repo has no `.acm/destination.md` yet, and asks a short question instead of running the full multi-session signal-gathering process.
- **Orient** — a "mini" tripwire: a condensed arc-read every 5th trail entry, not the full freshness-guard/derived-artifact machinery.
- **Trail** — always happens, every run, with a variable-depth entry format (Micro / Standard / Full) so routine work costs little and real decisions still get full reasoning.

`probe` (contamination / pattern-matching detection) is intentionally excluded from this consolidation — confirmed by the operator, not a placeholder for later.

## Status

v2.3.0 — confirmed as the operator's daily-usage skill going forward (superseding day-to-day use of the full `pea/skills` suite, which stays available for whatever still warrants its depth). Not yet battle-tested against a long multi-session run. A second design bar applies alongside the operator's own use: **a stranger should be able to pick up `think-it-through/SKILL.md` and use it without the author explaining anything** — jargon or unexplained references to the original five-skill suite are defects. See [`.acm/destination.md`](./.acm/destination.md) for the full mandate and open items, and [`.acm/audit-trail.md`](./.acm/audit-trail.md) for the record of how this repo came to exist.

## Use

Point an agent at [`think-it-through/SKILL.md`](./think-it-through/SKILL.md) the same way you'd point it at any of the `pea/skills` skill files (e.g. copy the `think-it-through/` folder into wherever your agent loads skills from, such as `~/.copilot/skills/`), or just paste the file into a prompt. There is no installer, and there won't be one — by design. The whole point of this fork is that it's just a skill: one readable file, no build step, no script to trust between reading it and using it.
