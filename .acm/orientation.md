# orientation.md — work-skill

_Last updated: 2026-08-17 (run: first-orientation-synthesis)_

## Current claims

- **The three-namespace identity confusion (repo name / skill-invocation name / method name) is resolved, not recurring.** Entries `align-skill-folder-with-adopted-identity`, `restore-repository-and-separate-skill-layout`, and `rename-invocation-identity-to-work` conflated these three levels across three iterations and one explicit `[!REVERSAL]`, but no confusion between them has recurred in the six entries since. Falsifiable if a future run treats `work` (the invocation identity), `work-skill` (the repository), or `Improve` (the method) as interchangeable, or invents a fourth level (e.g. a package/distribution name).

- **Evidence-lifecycle hardening is now a consistent three-leg contract, but only structurally tested.** Authorship (`distinguish-trace-from-independent-evidence`), write-timing (`make-change-decisions-durable-before-action`), and read-time detection (`detect-open-checkpoints-before-new-work`) each closed a gap the previous leg exposed. None has been tested against a genuinely abandoned mid-run checkpoint — every test so far has been either simulated by the same informed session or absent entirely. Falsifiable if a real interruption (not a same-session simulation) shows the next run failing to detect or correctly resolve an open checkpoint.

- **"Undefined `.acm/` artifact referent" is this arc's most productive same-family finding-class, and it was invisible to every review method except cold-executor observation.** The learning-surface referent (`cold-read-observation-and-learning-surface-referent`) and the Orientation referent (`define-orientation-referent`) were both caught only by a stateless subagent with no shared context — not by author-session structural checks, and not by the same-day fifteen-candidate adversarial cold review (`bounded-silence-adversarial-cold-review`), which missed the Orientation gap entirely despite running the same day and explicitly checking "trail format" and "authority-gate structure." Falsifiable if a future self-review or single-pass adversarial review, without a cold-executor step, independently catches an equivalent referent gap before a cold test does.

- **Every "silence" claim in this trail to date is same-family, single-session silence — not the convergence the Destination actually requires.** The Destination's convergence lease requires three fresh-session evaluations from distinct model families; this trail has supplied only same-family (Copilot/Claude) evidence throughout, including the bounded silence in `bounded-silence-adversarial-cold-review`. That entry itself named this limitation. No entry since has closed it.

- **The Orientation mechanism has gone from undefined, to defined, to exercised (this entry) within one continuous arc — but this is its first invocation, so its actual usefulness is untested.** It is not yet known whether a future fresh run will actually consult this file before deciding what to do, or whether the synthesis here holds up against the next several entries' evidence rather than needing early revision.

## What the next runs should test

Synthesized from the last several entries' own Candidate Next Moves, which have repeated the same top item without it ever being fulfilled:

1. **Obtain a fresh-session evaluation from a genuinely distinct model family.** This has been the top-ranked candidate in at least three consecutive entries (`fresh-session-bounded-orientation-silence`, `bounded-silence-adversarial-cold-review`, `define-orientation-referent`) and has never been supplied. Every evaluation so far — cold-executor, adversarial reviewer, and this session itself — shares the same model family and host. This is the single highest-leverage remaining test because it is the only one that can actually move the Destination's convergence lease forward.
2. **Deliberately induce and test recovery from a genuinely abandoned checkpoint**, not a same-session simulation, to test the evidence-lifecycle claim above.
3. **Compare claimed reads against `llm-harness-proxy` captured traffic** to test the confabulation finding (`cold-read-observation-and-learning-surface-referent`): a cold executor reached correct conclusions while citing a wrong entry date and an invented slug. This is a direct threat to trusting any self-reported Trail claim, including this orientation synthesis's own reading of the arc.
4. **Commit the currently uncommitted Orientation-referent fix** (from `define-orientation-referent`, and this file) under separate operator authorization, so that any future silence or convergence claim applies to the published text rather than a local worktree.
5. **Re-derive this file again once several more entries accumulate**, and check whether the claims above held or needed correction — that comparison is itself evidence about whether the Orientation mechanism is working as intended.

## Active operational rules

- Before authoring another prose fix to `work/SKILL.md`, get cold-executor (stateless subagent, no shared context) behavioral evidence first. Same-session self-review and even a same-day adversarial cold review have a demonstrated blind spot for undefined-referent defects; only an independent cold read caught them.
- For every authorized Change iteration, append the Trail entry through Prediction *before* the first target mutation, and never rewrite that checkpoint afterward — append completion, correction, or `[!REVERSAL]` instead.
- At the start of every run, check the trail tail for an open (incomplete) checkpoint before starting new work; complete it or explicitly supersede it, never stack a new iteration on top of it.
- Treat any single-session silence or convergence claim in this trail as scoped to "same-family, single-session" only. Do not treat it as satisfying the Destination's three-family convergence lease, and say so explicitly whenever a silence claim is repeated or extended.
- Do not read `.acm/destination.md`'s historical prose about "Retrospect" / "retrospect.md" as describing a live mechanism — its own "Historical reconciliation" section explicitly marks that vocabulary superseded. The live contract has only `orientation.md` and (if present) `learning.md`.
- Do not import the sibling `pea/skills` suite's heavier Orient tooling (`record.py`, mandatory freshness-guard scripts, `history.md`/`learning-archive.md`) into this repository. This repository's Destination explicitly favors leanness; this file itself was produced without any of that tooling and that omission is intentional, not a gap.

## Loop-effectiveness notes

The same-day sequence — author-session structural check, then cold-executor test, then a fifteen-candidate adversarial cold review, and only *then* a fresh session finding something all three missed — suggests no single review layer used so far has been sufficient on its own. Self-review missed both undefined-referent gaps. The adversarial reviewer, sharing the same model family and host as every other evaluator, still missed the Orientation gap despite explicitly checking adjacent concerns (trail format, authority-gate structure). The demonstrated pattern is that *stacking distinct methods across distinct sessions* has found real defects, while any single method run once has not. This is itself a candidate limitation worth naming: this arc has not yet tested whether a distinct model family would catch something all of the same-family methods above missed, or whether it would simply agree with this file's claims.
