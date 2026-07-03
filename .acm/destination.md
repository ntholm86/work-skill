# Destination — pea-skills-lite

_Operator: Nils Holmager | Initialised: 2026-07-03_

> Repo-level destination. Governs work specific to this repo. The workspace destination (`../.acm/destination.md`, i.e. `pea/.acm/destination.md`) governs cross-repo coordination and wins on any conflict — see ACM §4 Scoped Memory. Read that file first when reasoning about how this repo fits the wider research program; this file governs what happens *inside* pea-skills-lite.

---

## The One Question

> What does the accountability-architecture skill suite look like once the binding constraint is cost-per-unit-of-reasoning-quality, not reasoning quality alone?

## Why this repo exists

The full skills suite (`pea/skills`: intent, improve, destination, orient, trail, probe) was built during what the operator calls the **"token bonanza"** — a period before 2026-07 where token cost was not the binding constraint. In practice, the operator finds they mostly invoke two of those six skills — Intent and Improve — for almost everything, and is now **"running out of tokens too fast"** using the full multi-skill-invocation discipline.

`pea-skills-lite` is a deliberate cost-optimized fork: the same governing principles, delivered as **one consolidated skill** instead of chaining several, so a session pays for one skill-load and one reasoning pass instead of many.

**[Confirmed 2026-07-03, second Destination pass]** This is not a side experiment — the operator has confirmed `pea-lite` is meant to become their actual daily-usage skill, superseding day-to-day reliance on the full `pea/skills` suite. The full suite remains untouched and available for whatever still warrants its depth (this repo does not delete or deprecate it), but the default reach-for is now `pea-lite`.

## Operator's direct mandate

Source: operator's message, 2026-07-03 (quoted in full in this repo's `.acm/audit-trail.md`, first entry). Verbatim requirements:

1. **One skill, not six.** Improve becomes the base loop; it always applies Intent internally — no separate invocation.
2. **Trail always happens.** Every run appends to `.acm/audit-trail.md` in the target repo. No exceptions, no opt-out.
3. **Mini-Destination.** If `.acm/destination.md` doesn't exist yet in the *target* repo being worked on, ask the operator a short question or two and write it. If it exists, just read it.
4. **Mini-Orient.** Every 5th iteration, do a condensed arc-read (not the full freshness-guard / derived-artifact machinery of real Orient) and note what's changing.
5. **The explicit trade-off:** lower token cost per session, *without* silently lowering reasoning quality at the moments quality actually matters (real decisions). If a cost/quality trade-off is unavoidable, it must be visible and justified in the trail entry, never silently absorbed.

## Sourced inferences (not literally stated — offered for confirmation, not blocking)

- **[Confirmed 2026-07-03]** Probe (the 6th original skill — contamination / pattern-matching detection) is intentionally *not* part of the lite consolidation. *Source:* the operator's message names Intent, Improve, mini-Orient, mini-Destination, and Trail explicitly, and never mentions Probe. Operator confirmed directly: "I dont think the probe skill is needed in pea-skills-lite." Probe stays a separate, occasionally-invoked skill outside `pea-lite`, not folded in — settled, not just assumed.
- **[Corrected 2026-07-03]** No installer — permanently, by design, not a temporary v1 scope cut. Operator's own words: "I dont want an installer, its should be so easy its just a skill that ppl can use." Ease-of-adoption is itself part of what "lite" means here: a single self-contained `SKILL.md` a person can read, drop into wherever their agent loads skills from, or paste straight into a prompt — no build step, no script to trust, no packaging ceremony between the file and using it. This supersedes the earlier unconfirmed inference, which had incorrectly framed the lack of an installer as "not yet" rather than "not ever."

## Constraints carried over from the workspace destination

- Higher scope wins on coordination matters (ACM §4) — `pea/.acm/destination.md` governs if this repo's direction ever conflicts with cross-repo coordination.
- Append-only memory — corrections happen by appending, never rewriting.
- The three principles — **Operator's Intent, Observable Autonomy, Convergence Is Silence** — are constraints, not preferences, even in the lite version. Cost is optimized *around* them, never at their expense. This is the design tension the `pea-lite/SKILL.md` file exists to resolve.

## What "done" looks like for this repo

Not a fixed release. Working-in-use signal: the operator actually reaches for `pea-lite` instead of chaining Intent → Improve manually, session token cost visibly drops, and reasoning quality at real decision points is not perceptibly worse — the operator would notice a regression and say so.

**[Confirmed 2026-07-03, second Destination pass]** A second, independent bar now applies alongside the operator's own daily use: **a stranger could pick up `pea-lite/SKILL.md` and use it without the operator explaining anything.** This is a real design constraint, not aspirational framing — it means jargon, unexplained references to the original five-skill suite, or assumptions about shared context with the operator are defects, not just stylistic choices.

## Open items (not blocking, revisit when the operator has a moment)

_(none currently open from the original two bootstrap inferences — both settled. See "Destination run — 2026-07-03 (second pass)" below for what's open now.)_

Both sourced inferences from the initial bootstrap are now settled: Probe stays excluded, and no installer will be built. Ease-of-use (a single readable file, no packaging step) is now a confirmed design constraint on `pea-lite/SKILL.md`, not just a scope cut.

---

## Destination run — 2026-07-03 (second pass)

Operator asked to run the full Destination skill again (not the mini version). Signal gathered: this file, `.acm/audit-trail.md`'s 4 entries, and the pattern across the two prior corrections this session.

### Sourced inferences

1. **[Direction, unconfirmed]** The operator wants `pea-lite` to become their actual day-to-day default, not a parallel experiment. *Source:* the original bootstrap message ("I find myself mostly using Intent and improve"), plus both corrections since bootstrap pushing toward permanence rather than provisional framing ("not ever," not "not yet").
2. **[Priority, unconfirmed]** The operator wants this repo's files kept lean — no speculative "decide later" open items invented unprompted. *Source:* twice now (Probe exclusion, no-installer) the operator corrected an open item or hedge that was added without being asked for.
3. **[Question being asked, resolved this run]** The one open item left (whether to list this repo in the workspace layer table) was itself something added unprompted, not requested.
4. **[Quality bar, unconfirmed]** "ppl that can use it" may signal the actual bar is "a stranger could pick this up," not just "works for the operator."

### Questions asked

All four inferences above were surfaced as direct questions. **The operator was not available to respond** ("Work autonomously and make good decisions").

### What I now believe (confirmed 2026-07-03 by the operator, except where noted)

- **Confirmed.** `pea-lite` is the operator's new daily-usage skill. "Yes i want pea skills lite to become my new daily usage skill." This is now stated in "Why this repo exists" above, not just this section.
- **Confirmed.** Keep this repo's files clean — no speculative open items added unprompted. "yes i want the repo files kept clean." Adopted as an ongoing practice, not just a one-time correction.
- **Deferred by the operator, not dropped.** The workspace-layer-table question confused as asked ("im not sure what you mean abotu question 3 i will decide later"). Clarifying it here for whenever it's picked back up: `pea/.acm/destination.md` (the workspace-level file, one directory up, operator-held) has a table listing the research program's repos by role (Theory, Construct, Runtime, Reasoning, etc.) — `pea/skills` is currently listed there as "Reasoning." The open question was whether `pea-skills-lite` should also get a row in that table, or stay unlisted since it's a fork of an already-listed repo. This is a real open item now, explicitly operator-owned and deferred — not one I invented and should trim per the lean-files practice above.
- **Confirmed.** "ppl that can use it" was literal, not just phrasing: "Yes it should also be that a stranger could pick up the skill." This is now reflected as an explicit second success bar in "What 'done' looks like" above.

### What's still open

- The workspace-layer-table question (see above) — operator-deferred, revisit when they want to decide.
