# Audit Trail — pea-skills-lite

## 2026-07-03 — bootstrap-pea-lite-from-five-skills

**Tier: Full.** Structural/design decision (creating the repo and its one governing skill), and this is the trail's own first entry — it should demonstrate the format it's asking future runs to follow.

**Interpretation of the ask.** Operator's message, quoted for source-fidelity: they created an empty folder `C:\git\pea\pea-skills-lite` and asked to (a) initiate ACM there, (b) initialize a git repo there, and (c) design a single consolidated "lite" skill merging Intent + Improve + a mini-Orient (every 5th iteration) + a mini-Destination (auto-create, ask questions) + always-on Trail — optimized to reduce token cost while preserving reasoning quality. Explicit framing: the full suite was built during a "token bonanza" (token cost wasn't the constraint); now it is, and "quality must be preserved — or the tradeoff must really be worth it." Operator also explicitly invoked "understand my intent" and "capture destination" for this task itself.

Read as: build a genuinely usable, standalone skill — not a stub or a router to the other five files — that a single agent can load once and get the same governing discipline from, at lower per-run token cost. Not read as: deprecate or modify the original `pea/skills` suite (untouched this session), nor as a request to fully productionize this repo (no install scripts, CI, or CHANGELOG built — flagged as an open item, not silently skipped).

**Examination (lenses).**
- *Purpose*, against the workspace destination (`pea/.acm/destination.md`, read as the higher-scope mandate before writing this repo's own destination.md): the workspace positions `skills` as the "Reasoning" layer of a larger research program on trustworthy delegation. A lite fork is consistent with that program's own completion criteria for `ai-steward` — "low cost... cheap models handle routine work" — the same cost-consciousness the operator now wants applied to the manually-invoked skill suite, not just the automated one.
- *Purpose*, against the five source skills (read in full this session): each has real, load-bearing ceremony (Improve's 4-lens examination and 4-trigger reflection; Destination's sourced-inference-then-question flow; Orient's freshness-guard and derived-artifact regeneration; Trail's writer-splitting and history.md/learning.md regeneration). The honest design problem was not "delete the ceremony" but "make the ceremony's cost proportional to the stakes of what's being recorded" — most of a session's iterations are not decisions in the sense the full suite optimizes for.
- *Inconsistency*: none found between the five source files — they're internally coherent, which made the merge tractable (a genuinely conflicting source-skill design would have forced a harder call than tiering).
- *Waste*: the two biggest token costs identified were (1) loading five files instead of one, and (2) applying full-depth ceremony uniformly regardless of triviality. Both are addressed structurally (single file; explicit depth tiers) rather than by cutting any of the three governing principles.

**Challenge.** Considered keeping all five as separate files with one acting as a thin "router" that decides which to invoke. Rejected: the operator said "concenced into a single skill" and "you only use ONE skill" — a router still costs a multi-file load and adds indirection the operator explicitly asked to remove. Also considered leaving Trail's depth uniform (always full-ceremony) and only compressing Intent/Orient/Destination. Rejected: uniform-depth Trail is the single largest per-run cost in the original suite for routine work, and leaving it untouched would have missed the main lever available for the stated goal (lower cost per session).

**Decision `[!DECISION]`.** Built the full repo scaffold in one pass rather than in incremental steps: `.acm/destination.md` (mandate, sourced-inference-flagged), `pea-lite/SKILL.md` (the actual consolidated skill, ~4 sections: bootstrap gate / fused-Intent step / work loop / always-on tiered Trail / mini-Orient), `README.md`, and this trail entry — then a git init and initial commit. Prediction: this repo will be usable as-is for a first real multi-session run without needing another design pass before the 5th iteration exercises the mini-Orient path for the first time. I expect the depth-tier judgment call (which tier a given run deserves) to be the part most likely to need correction once tested against real use, since it's the one genuinely new mechanism not lifted directly from a source skill.

**Action.** Created `.acm/destination.md`, `pea-lite/SKILL.md`, `README.md`; ran `git init` (branch `main`, reusing the already-configured global identity `Nils Holmager <nilsholmager@gmail.com>` — confirmed present via `git config user.name`/`user.email` before relying on it); will commit all of it together with this entry as the initial commit.

**Reflection.**
- *Model of the target, falsifiable:* pea-lite's real bottleneck will not be the merged instructions (those are a one-time load cost) but whether the depth-tier self-check actually holds under pressure — i.e., whether a future run defaults to Tier 3 "to be safe" and quietly reproduces the exact cost problem this repo exists to solve. A future run should be able to say "still true" or name a specific instance where tier-drift happened.
- *Blind spot:* this entry was written by the same reasoning that designed the tiers — I have not yet observed a real Tier 1/Tier 2 entry in the wild, so the boundary between them (stated as "a real choice existed between plausible alternatives" for Tier 2) is untested and may turn out to be harder to judge in the moment than it reads on paper.
- *Imagined expert pushback:* someone who has run the full suite for a long arc would likely ask whether cutting `history.md`/`learning.md` regeneration loses something real at scale — those derived artifacts exist because raw `audit-trail.md` gets expensive to re-read past a certain length. Mini-orient's "read only the last ~5-10 entries" is the mitigation, but it hasn't been tested against a trail long enough for that limit to matter yet.

**Across-trail triggers** (first entry — no prior trail to check):
- *Recurring finding-class:* not applicable, first entry.
- *About to declare silence:* not fired — this run made substantial changes.
- *Contradicts prior `[!REALIZATION]`:* not applicable, no prior entries.
- *Operator explicitly asked:* not fired for macro-reflection specifically, though the operator did ask for the Intent/Destination process to be applied explicitly to this task, which is reflected above.

### Candidate Next Moves

1. Run `pea-lite` for real, on a real target repo, and see whether the depth-tier judgment holds — this is the one untested mechanism and the fastest way to find out if it's right.
2. Confirm or correct the two sourced inferences in `.acm/destination.md` (Probe excluded; personal-use-only scope for now) — low cost to check, meaningfully changes what gets built next if either is wrong.
3. Once real use has happened a few times, decide whether `pea-skills-lite` belongs in `pea/.acm/destination.md`'s workspace-level layer table as a variant of the "Reasoning" layer — not done this session since that file is operator-held.

## 2026-07-03 — confirm-probe-exclusion

Asked whether Probe belongs in the lite consolidation; operator confirmed it doesn't ("I dont think the probe skill is needed in pea-skills-lite"). Updated `.acm/destination.md`'s sourced-inference entry from `[Inference, unconfirmed]` to `[Confirmed 2026-07-03]`. No change needed to `pea-lite/SKILL.md` itself — it already excluded Probe. No decisions, nothing else notable.
