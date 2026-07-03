# Destination — pea-skills-lite

_Operator: Nils Holmager | Initialised: 2026-07-03_

> Repo-level destination. Governs work specific to this repo. The workspace destination (`../.acm/destination.md`, i.e. `pea/.acm/destination.md`) governs cross-repo coordination and wins on any conflict — see ACM §4 Scoped Memory. Read that file first when reasoning about how this repo fits the wider research program; this file governs what happens *inside* pea-skills-lite.

---

## The One Question

> What does the accountability-architecture skill suite look like once the binding constraint is cost-per-unit-of-reasoning-quality, not reasoning quality alone?

## Why this repo exists

The full skills suite (`pea/skills`: intent, improve, destination, orient, trail, probe) was built during what the operator calls the **"token bonanza"** — a period before 2026-07 where token cost was not the binding constraint. In practice, the operator finds they mostly invoke two of those six skills — Intent and Improve — for almost everything, and is now **"running out of tokens too fast"** using the full multi-skill-invocation discipline.

`pea-skills-lite` is a deliberate cost-optimized fork: the same governing principles, delivered as **one consolidated skill** instead of chaining several, so a session pays for one skill-load and one reasoning pass instead of many.

## Operator's direct mandate

Source: operator's message, 2026-07-03 (quoted in full in this repo's `.acm/audit-trail.md`, first entry). Verbatim requirements:

1. **One skill, not six.** Improve becomes the base loop; it always applies Intent internally — no separate invocation.
2. **Trail always happens.** Every run appends to `.acm/audit-trail.md` in the target repo. No exceptions, no opt-out.
3. **Mini-Destination.** If `.acm/destination.md` doesn't exist yet in the *target* repo being worked on, ask the operator a short question or two and write it. If it exists, just read it.
4. **Mini-Orient.** Every 5th iteration, do a condensed arc-read (not the full freshness-guard / derived-artifact machinery of real Orient) and note what's changing.
5. **The explicit trade-off:** lower token cost per session, *without* silently lowering reasoning quality at the moments quality actually matters (real decisions). If a cost/quality trade-off is unavoidable, it must be visible and justified in the trail entry, never silently absorbed.

## Sourced inferences (not literally stated — offered for confirmation, not blocking)

- **[Inference, unconfirmed]** Probe (the 6th original skill — contamination / pattern-matching detection) is intentionally *not* part of the lite consolidation. *Source:* the operator's message names Intent, Improve, mini-Orient, mini-Destination, and Trail explicitly, and never mentions Probe. Treated as: Probe stays a separate, occasionally-invoked skill outside `pea-lite`, not folded in. **If wrong, say so** and a mini-Probe trigger can be added later.
- **[Inference, unconfirmed]** This is, for now, meant for the operator's own personal/local use across their own repos, not yet a public-distribution package with install scripts, badges, CI, etc. — mirroring `pea/skills`'s full packaging (install.ps1/.sh, CHANGELOG, CITATION.cff) is a later step, not this one. *Source:* the framing "I find myself mostly using..." reads as a personal-workflow observation; the ask was to "initiate ACM" and "initialize a repo," not to write install docs. **If wrong, say so** and full packaging can be added.

## Constraints carried over from the workspace destination

- Higher scope wins on coordination matters (ACM §4) — `pea/.acm/destination.md` governs if this repo's direction ever conflicts with cross-repo coordination.
- Append-only memory — corrections happen by appending, never rewriting.
- The three principles — **Operator's Intent, Observable Autonomy, Convergence Is Silence** — are constraints, not preferences, even in the lite version. Cost is optimized *around* them, never at their expense. This is the design tension the `pea-lite/SKILL.md` file exists to resolve.

## What "done" looks like for this repo

Not a fixed release. Working-in-use signal: the operator actually reaches for `pea-lite` instead of chaining Intent → Improve manually, session token cost visibly drops, and reasoning quality at real decision points is not perceptibly worse — the operator would notice a regression and say so.

## Open items (not blocking, revisit when the operator has a moment)

- Confirm or correct the two sourced inferences above.
- Decide whether `pea-skills-lite` should eventually be listed as a variant of the "Reasoning" layer in `pea/.acm/destination.md`'s layer table (not done in this session — that file is operator-held and wasn't asked to be changed).
- Decide whether to add install tooling (`install.ps1`/`install.sh`) mirroring `pea/skills` once the design has proven itself in real use.
