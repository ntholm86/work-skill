# pea-skills-lite

A cost-optimized, single-file fork of the [pea/skills](../skills/) suite. Where the full suite is five separate skills (`intent`, `improve`, `destination`, `orient`, `trail` — plus `probe`), `pea-skills-lite` is **one skill**: [`pea-lite/SKILL.md`](./pea-lite/SKILL.md).

## Why

The full suite was built during a period where token cost wasn't the binding constraint. In practice, most sessions only ever invoke Intent and Improve, chained together, with Trail always following. Loading and running five skill files' worth of ceremony for that common case costs more than it needs to. `pea-lite` merges:

- **Intent** — folded into the loop's own first step, narrated only when the interpretation is genuinely uncertain.
- **Improve** — the base loop (examine → challenge → decide → act → reflect), depth-scaled to the stakes of the change.
- **Destination** — a "mini" bootstrap: only runs if the target repo has no `.acm/destination.md` yet, and asks a short question instead of running the full multi-session signal-gathering process.
- **Orient** — a "mini" tripwire: a condensed arc-read every 5th trail entry, not the full freshness-guard/derived-artifact machinery.
- **Trail** — always happens, every run, with a variable-depth entry format (Micro / Standard / Full) so routine work costs little and real decisions still get full reasoning.

`probe` (contamination / pattern-matching detection) is intentionally left out of this consolidation for now — see `.acm/destination.md` for the reasoning and the open item.

## Status

v1.0.0 — first draft, not yet battle-tested against a real multi-session run. See [`.acm/destination.md`](./.acm/destination.md) for the full mandate and open items, and [`.acm/audit-trail.md`](./.acm/audit-trail.md) for the record of how this repo came to exist.

## Use

Point an agent at [`pea-lite/SKILL.md`](./pea-lite/SKILL.md) the same way you'd point it at any of the `pea/skills` skill files (e.g. copy the `pea-lite/` folder into wherever your agent loads skills from, such as `~/.copilot/skills/`). No install script yet — that's a deliberate scope cut for this first version, not an oversight.
