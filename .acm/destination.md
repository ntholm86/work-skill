# Destination — auditonomy-skill

_Operator: Nils Holmager | Initialised: 2026-07-03_

> Repo-level destination. Governs work specific to this repo. The workspace destination (`../.acm/destination.md`, i.e. `pea/.acm/destination.md`) governs cross-repo coordination and wins on any conflict — see ACM §4 Scoped Memory. Read that file first when reasoning about how this repo fits the wider research program; this file governs what happens *inside* auditonomy-skill (renamed from `pea-skills-lite`, then `think-it-through-skill` — see "Destination run — 2026-07-04 (rename)" and "Destination run — 2026-07-04 (second rename)" below).

---

## The One Question

> What does a **standalone, target-agnostic improvement-reasoning architecture with full auditability** look like — one that can reason about and improve *anything* the model it runs on can reason about, adhering to PEA principles?

*(Superseded framing, kept for the record: "What does the accountability-architecture skill suite look like once the binding constraint is cost-per-unit-of-reasoning-quality, not reasoning quality alone?" — that was the question during this repo's birth as a fork; see "Destination run — 2026-07-04 (standalone reframing)" below for why it no longer leads.)*

## Why this repo exists

**[Reframed 2026-07-04, operator-confirmed — see "Destination run — 2026-07-04 (standalone reframing)" below.]** `auditonomy` is a **standalone skill**: an autonomous improvement-reasoning architecture with full auditability that is *target-agnostic* — it can work on anything the model it runs on can reason about: code, music, letters, books, plans, whatever. Its lineage (below) is a fork of the full suite, but lineage is not identity: the suite comparison was scaffolding during its birth, not its purpose. When this skill is pointed at itself, the thing being improved is **that general capability** — the ability to understand and improve anything — not fidelity to its parent suite.

*Lineage, kept for the record:* The full skills suite (`pea/skills`: intent, improve, destination, orient, trail, probe) was built during what the operator calls the **"token bonanza"** — a period before 2026-07 where token cost was not the binding constraint. In practice, the operator found they mostly invoked two of those six skills — Intent and Improve — for almost everything, and was **"running out of tokens too fast"** using the full multi-skill-invocation discipline. This repo began as a deliberate cost-optimized fork: the same governing principles, delivered as **one consolidated skill** instead of chaining several, so a session pays for one skill-load and one reasoning pass instead of many. That cost discipline remains a real constraint — it just isn't the destination anymore.

**[Confirmed 2026-07-03, second Destination pass]** This is not a side experiment — the operator has confirmed this skill (originally named `pea-lite`, renamed `think-it-through` then `auditonomy` on 2026-07-04) is meant to become their actual daily-usage skill, superseding day-to-day reliance on the full `pea/skills` suite. The full suite remains untouched and available for whatever still warrants its depth (this repo does not delete or deprecate it), but the default reach-for is now `auditonomy`.

## Operator's direct mandate

Source: operator's message, 2026-07-03 (quoted in full in this repo's `.acm/audit-trail.md`, first entry). Verbatim requirements:

1. **One skill, not six.** Improve becomes the base loop; it always applies Intent internally — no separate invocation.
2. **Trail always happens.** Every run appends to `.acm/audit-trail.md` in the target repo. No exceptions, no opt-out.
3. **Mini-Destination.** If `.acm/destination.md` doesn't exist yet in the *target* repo being worked on, ask the operator a short question or two and write it. If it exists, just read it.
4. **Mini-Orient.** Every 5th iteration, do a condensed arc-read (not the full freshness-guard / derived-artifact machinery of real Orient) and note what's changing.
5. **The explicit trade-off:** lower token cost per session, *without* silently lowering reasoning quality at the moments quality actually matters (real decisions). If a cost/quality trade-off is unavoidable, it must be visible and justified in the trail entry, never silently absorbed.
6. **[Confirmed 2026-07-04]** Between the two axes this fork trades on, **reasoning quality outranks mechanism completeness.** Operator's words, verbatim: "capability is one of the most important things for pea-lite... mechanisms are less important... Similar Quality with much less cost is the goal." Concretely: whether `think-it-through` (then named `pea-lite`) carries the full suite's harder tooling (freshness guards on derived artifacts, writer-splitting, ARF/Probe, session-transcript capture) matters far less than whether its three core reasoning moments are *as good* as the suite's — not merely structurally present. The operator named those three moments directly: **Intent** ("understand what and why, not how"), **Improve's examination** ("surroundings" — reading the target's actual context before deciding), and **Orient** ("meta" — arc-level reasoning about the work itself). And explicitly general-purpose: this reasoning quality is what makes the skill work on *any* kind of target, not just software.

## Sourced inferences (not literally stated — offered for confirmation, not blocking)

- **[Confirmed 2026-07-03]** Probe (the 6th original skill — contamination / pattern-matching detection) is intentionally *not* part of the lite consolidation. *Source:* the operator's message names Intent, Improve, mini-Orient, mini-Destination, and Trail explicitly, and never mentions Probe. Operator confirmed directly: "I dont think the probe skill is needed in pea-skills-lite." Probe stays a separate, occasionally-invoked skill outside `think-it-through`, not folded in — settled, not just assumed.
- **[Corrected 2026-07-03]** No installer — permanently, by design, not a temporary v1 scope cut. Operator's own words: "I dont want an installer, its should be so easy its just a skill that ppl can use." Ease-of-adoption is itself part of what "lite" means here: a single self-contained `SKILL.md` a person can read, drop into wherever their agent loads skills from, or paste straight into a prompt — no build step, no script to trust, no packaging ceremony between the file and using it. This supersedes the earlier unconfirmed inference, which had incorrectly framed the lack of an installer as "not yet" rather than "not ever."

## Constraints carried over from the workspace destination

- Higher scope wins on coordination matters (ACM §4) — `pea/.acm/destination.md` governs if this repo's direction ever conflicts with cross-repo coordination.
- Append-only memory — corrections happen by appending, never rewriting.
- The three principles — **Operator's Intent, Observable Autonomy, Convergence Is Silence** — are constraints, not preferences, even in the lite version. Cost is optimized *around* them, never at their expense. This is the design tension the `auditonomy/SKILL.md` file exists to resolve.

## What "done" looks like for this repo

Not a fixed release. Working-in-use signal: the operator actually reaches for `auditonomy` instead of chaining Intent → Improve manually, session token cost visibly drops, and reasoning quality at real decision points is not perceptibly worse — the operator would notice a regression and say so.

**[Confirmed 2026-07-03, second Destination pass]** A second, independent bar now applies alongside the operator's own daily use: **a stranger could pick up `auditonomy/SKILL.md` and use it without the operator explaining anything.** This is a real design constraint, not aspirational framing — it means jargon, unexplained references to the original five-skill suite, or assumptions about shared context with the operator are defects, not just stylistic choices.

## Open items (not blocking, revisit when the operator has a moment)

_(none currently open from the original two bootstrap inferences — both settled. See "Destination run — 2026-07-03 (second pass)" below for what's open now.)_

Both sourced inferences from the initial bootstrap are now settled: Probe stays excluded, and no installer will be built. Ease-of-use (a single readable file, no packaging step) is now a confirmed design constraint on `auditonomy/SKILL.md`, not just a scope cut.

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

---

## Destination run — 2026-07-04 (third pass)

Operator corrected the priority ordering implicit in the prior day's comparative-rating work. That rating had weighted mechanism-completeness (freshness guards, writer-splitting, ARF/Probe, session/transcript capture) as a significant gap against the full suite. The operator's correction: those mechanisms matter comparatively little; what must hold up is **reasoning quality**, specifically in the three moments that carry the actual thinking — interpreting the ask (Intent), examining the target and its surroundings (Improve's step 2), and arc-level meta-reasoning about the work itself (Orient). This is now folded into the confirmed mandate above as point 6, verbatim-sourced.

### What this changes going forward

- Future comparative ratings of `pea-lite` against the full suite should weight **interpretive depth, examination depth, and meta/arc-reasoning depth** as the primary axis — not mechanism parity.
- A legitimate open question this creates, not yet answered: is `pea-lite`'s current step 1 (Intent-fused), step 2 (Work/examine), and step 4 (mini-Orient) text actually *as rigorous* as the full suite's `intent`, `improve` step 2, and `orient` — or only structurally analogous? That assessment has not yet been done under this corrected priority and is the natural next piece of work.

### What's still open

- The workspace-layer-table question — operator-deferred, revisit when they want to decide.
- **New:** the reasoning-quality depth assessment named above — not yet run.

---

## Destination run — 2026-07-04 (rename)

Operator judged the name `pea-lite` a defect in its own right: it tells an outsider nothing about what the skill does, and fails the same stranger-pickup bar this file already holds as a confirmed design constraint. Three rounds of candidate names were proposed and rejected on the operator's own explicit criteria — round 1 rejected for not "sounding useful" on sight, round 2 (`show-your-work`) rejected for not capturing the reasoning-and-generality dimension, round 3 confirmed: **`think-it-through`**. The repo itself was renamed too (operator's explicit choice): `pea-skills-lite` → `think-it-through-skill`, avoiding a redundant nested `think-it-through/think-it-through/SKILL.md` by keeping the skill subfolder as `think-it-through/`.

**What changed:** `pea-lite/` → `think-it-through/` (git mv, history preserved), repo folder `pea-skills-lite` → `think-it-through-skill`, frontmatter `name:` field, the `# think-it-through` H1, the one in-body mention, README.md, and this file's forward-facing prose (mandate, current-state, "what done looks like" sections). Version bumped 2.2.0 → 2.3.0 (a structural/identity change, not a prose polish).

**What was deliberately left alone:** every verbatim operator quote naming `pea-lite` or `pea-skills-lite` (e.g. "capability is one of the most important things for pea-lite...", "I dont think the probe skill is needed in pea-skills-lite", "Yes i want pea skills lite to become my new daily usage skill") — quotes are a historical record of what was literally said and are not rewritten. The two dated "Destination run" sections above (2026-07-03 second pass, 2026-07-04 third pass) are likewise left using the old name throughout, by the same logic applied to `.acm/audit-trail.md`'s append-only rule: they are historical log entries describing what was true and what things were called at that point in time, not living/forward-facing prose.

### What's still open

- The workspace-layer-table question — operator-deferred, if it's ever revisited it should now reference `auditonomy-skill`.
- The reasoning-quality depth assessment (named 2026-07-04, third pass) — still not yet run.
- The real empirical with/without-skill test — still the single most-repeated unresolved item across this whole arc.

---

## Destination run — 2026-07-04 (second rename)

Operator judged `think-it-through` itself not quite right either: it reads as a generic reasoning-discipline slogan, not a name tied to what the skill actually enforces. The correction came in two steps — first toward a made-up word blending Improve/audit/reasoning/autonomy (`Reckonomy`, rejected: too close to the unrelated word "reckoning"), then the operator's own realization: the right word was already named in this skill's own three principles — **Principle 2, Observable Autonomy**. `auditonomy` is a portmanteau of *audit* (the always-on Trail step — what makes the autonomy observable) and *autonomy* itself, naming the skill after the one governing principle that most defines its mechanism, not an arbitrary blend of adjacent themes.

**Action.** OS-level rename of the repo folder (`think-it-through-skill` → `auditonomy-skill`) and the inner skill folder (`think-it-through/` → `auditonomy/`); updated frontmatter `name:`, the H1, and the one in-body mention in SKILL.md; updated README.md throughout; updated this file's forward-facing prose (title, mandate, current-state, "what done looks like" sections). Version 2.3.0 → 2.4.0.

**Operational complication, disclosed.** The folder rename did not go cleanly: a `cmd /c move` failed silently (exit code 1, no message), and a follow-up `Move-Item` failed partway with a permission error deleting `.git`'s read-only pack objects from the source — but only *after* it had already copied `.git`, `.acm/`, and `README.md` to the new destination. This left the repo split across two paths: the intact `.git` (with the working index correctly showing a staged `think-it-through/SKILL.md` → `auditonomy/SKILL.md` rename) in the new `auditonomy-skill/` folder, but the actual `SKILL.md` file itself still physically sitting in the old `think-it-through-skill/auditonomy/` path. Diagnosed via `git status` (showed the rename staged but the destination file "deleted" in the working tree — the tell that the file hadn't actually moved), fixed by moving the one straggler file into place, verified with a clean `git status`, then deleted the confirmed-empty leftover shell. No data was lost; the near-miss is disclosed here rather than smoothed over, per this skill's own Trail discipline.

**Deliberately not touched:** every verbatim quote and every historical dated section above containing the old names `pea-lite`, `pea-skills-lite`, or `think-it-through` — preserved as historical record, same convention as the first rename. `audit-trail.md`'s own historical entries are likewise untouched; a new entry was appended instead.

### What's still open

- The workspace-layer-table question — operator-deferred, if it's ever revisited it should now reference `auditonomy-skill`.
- The reasoning-quality depth assessment (named 2026-07-04, third pass) — still not yet run.
- The real empirical with/without-skill test — still the single most-repeated unresolved item across this whole arc.

---

## Destination run — 2026-07-04 (standalone reframing)

Operator corrected the repo's core identity, prompted by reading the baseline 10-metric scorecard: the measurements ("reasoning-depth parity **vs. full suite**", "mechanism integrity") revealed the working destination had drifted into *"make an economical copy of this other skillset"* — a derivative identity. Operator's correction, near-verbatim: it should be **"standalone"** — *"an autonomous skill with improve reasoning and full auditability that is target-agnostic — can work on anything the model you use can reason about: code, music, letters, books, whatever, anything."* One overall destination point is unchanged from the skillset era: something with the ability to reason about and improve **anything**, adhering to PEA principles.

The self-targeting arc (24+ trail entries of this skill auditing and improving itself) is not self-polish — *"we just happen to point it at itself"*, and what's actually being improved in those runs is the **general improvement-reasoning capability itself**, exactly as was done with the skillset before it. The skill must know this overall purpose when it reasons about itself.

**What this changes:**

- "The One Question" and "Why this repo exists" above — rewritten to lead with standalone identity; the fork framing demoted to lineage-for-the-record.
- **Future scorecards:** measurements must weight *target-agnostic improvement capability* — how well this skill understands and improves arbitrary targets — as the primary axis. Suite-parity metrics are lineage diagnostics at best; a scorecard dominated by them is measuring the scaffolding, not the building. (The baseline scorecard in `orientation.md` stands as an honest record of the plateau *as it was framed then* — per the plateau rule, this destination shift voids it; the next rating starts from this reframed axis.)
- **The external-target test rises further in priority:** under the old framing it was one open item among several; under this one it is the *only* direct test of the actual destination — a target-agnostic improver that has almost never left its own repo is unproven at precisely the thing it is for.

**What this does not change:** the three PEA principles (constraints, not preferences), the cost discipline (real constraint, just not the identity), the no-installer rule, Probe's exclusion, the stranger-pickup bar, lean files. All confirmed constraints, all still binding.

### What's still open

- The workspace-layer-table question — operator-deferred.
- **The external-target test — now the top item by an even wider margin** (see above): point this skill at something that isn't itself and isn't software — a letter, a plan, a piece of writing — and see whether the improvement reasoning holds.
- The reasoning-quality depth assessment — subsumed into the above: the external test *is* that assessment under the corrected framing.
