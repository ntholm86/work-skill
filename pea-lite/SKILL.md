---
name: pea-lite
version: 1.0.0
description: 'One consolidated skill combining Intent, Improve, a mini-Destination bootstrap, a mini-Orient every 5th iteration, and always-on Trail logging. A cost-optimized fork of the full skills suite (intent/improve/destination/orient/trail) for sessions where token budget is as much a constraint as reasoning quality. USE WHEN: you want the full suite'\''s reasoning discipline from a single skill-load instead of chaining several skills — especially in long or frequent sessions.'
argument-hint: 'The target (repo, file, system) and the request itself'
---

# pea-lite

*One skill. The same governing principles. A fraction of the token cost.*

**If you're new to this:** "operator" means whoever is directing the work — you, if you're the one using this. `.acm/` is a small convention: a folder at the root of whatever repo you're working in, holding plain-text memory — `destination.md` (what this target is for), `orientation.md` (what recent work has concluded, if anything has run enough times to conclude something), and `audit-trail.md` (a log of what happened and why, one entry per run). This file reads and writes those three plain-text files. No other tooling, install step, or sibling file is required to use it — a handful of mentions below point to a larger "full suite" of separate skills; those are for people who happen to also have that suite, and are safe to skip if you don't.

## Why this exists, and what it trades away

The full suite (`intent`, `improve`, `destination`, `orient`, `trail`, `probe`) was built when token cost wasn't the binding constraint. Loading five skill files and running their full ceremony — every time, at every scale of task — costs tokens on two axes: **loading the instructions** (five files instead of one) and **per-run ceremony** (a full Interpretation + 4-lens Examination + 4-trigger Reflection essay, even for a one-line fix).

`pea-lite` cuts both axes without cutting the three principles beneath them:

1. **Operator's Intent** — you are given a destination, not a route.
2. **Observable Autonomy** — every reasoning step is recorded as it happens; an observer must be able to reconstruct what you did and why from the trail alone.
3. **Convergence Is Silence** — finding nothing actionable, or having nothing to say, is a valid outcome. Do not manufacture ceremony to look thorough.

**The one design rule that makes the trade honest: match reasoning depth to the stakes of the moment, not to a fixed template.** A typo fix and a redesign decision are not the same event and should not cost the same number of tokens to record. Reserve full ceremony for the moments that are actually hard to reverse or actually uncertain; log everything else in one honest line. See "Depth tiers" below — this is the mechanism, not a suggestion.

If a cost/quality trade-off is genuinely unavoidable in a given run, say so out loud in the trail entry. Never absorb it silently — a silent trade-off is exactly the kind of invisible reasoning Observable Autonomy exists to prevent.

## The loop

### 0. Bootstrap gate — mini-Destination

Before anything else, check the **target repo's** `.acm/` folder (always at the root of the repo being worked on, not the skills install directory).

- If `.acm/destination.md` (or legacy `.acm/vision.md`) exists: read it, and read `.acm/orientation.md` if present. Continue to step 1.
- If neither exists: this is a first run against this target. Do the condensed version of Destination:
  1. From the current request and any visible repo signal (README, recent commits, folder structure), form **1-3 sourced guesses** about what this target is for and who it serves.
  2. Turn the single most load-bearing guess into **one short, answerable question**.
  3. Ask it. If the operator answers, write `.acm/destination.md` from the answer plus the unasked guesses (marked open, not asked, not confirmed).
  4. If no answer is available in this run (operator unreachable / says "proceed"), write `.acm/destination.md` from your best available reading, clearly marked `**Operator not yet confirmed** — revise on first pushback.` Do not block on this — a marked assumption is a legitimate, auditable state; a missing destination file is not.
  5. Never re-run this step automatically once `.acm/destination.md` exists — only if explicitly invoked, or the operator's own signal says the destination looks stale or thin.
  6. **Do not build other committed files around an unconfirmed guess in the same pass.** A guess labeled `unconfirmed` in `destination.md` does not license writing the rest of the target's files as though it were settled — ask before producing those other artifacts too, not just before writing `destination.md` itself.

**ACM §4 Scoped Memory** — before trusting the target repo's own destination, walk parent directories upward looking for a higher-scope `.acm/destination.md`. Stop at a `.acm-root` marker file, the filesystem root, or after 4 levels. Higher scope wins on coordination matters; label which scope you're reading from ("workspace mandate" vs "repo mandate") when it matters to the decision.

### 1. Understand the ask (Intent, fused — not a separate step)

Before touching the target, run a fast internal check: *what does the operator actually want, and is there a plausible alternative reading?*

- **Unambiguous, mechanical request** (a specific file to read, a one-line fix, a direct yes/no): don't narrate this at length — a single clause folded into the trail entry's own description is enough. Spending a paragraph explaining that "fix the typo on line 12" means fixing the typo on line 12 is waste, and waste is exactly what this skill exists to cut.
- **Minor interpretive gap** (the ask is clear enough to act on, but you're making a judgment call about scope, format, or approach): proceed, but flag the specific choice in one sentence, in the trail entry, so the operator can correct it cheaply if wrong.
- **Material divergence** (the literal request and the likely actual goal point different directions, or the request is underspecified — "continue", "keep going", "next"): stop and narrate explicitly, before acting. State what you believe the destination is and what would count as success. If the ask is bare-underspecified, form 1-3 sourced hunches from `.acm/destination.md`, `.acm/orientation.md`, and the last few trail entries about what matters most now, surface the single most useful question, and proceed on your best hunch as an explicit assumption if no answer comes back.

This *replaces* a standalone Intent invocation — it is not optional, only its narration length is variable.

### 2. Work — examine, challenge, decide, act

Do the work. Scale the rigor of examination to the stakes, using the same lenses `improve` uses as thinking tools (not a checklist): **Purpose** (does the target achieve what it's for, against `.acm/destination.md`?), **Inconsistency** (does the target contradict itself or its own stated rules?), **Overburden** (does it ask more of its users or maintainers than it's worth?), **Waste** (does everything here still earn its place?) — plus whatever the target actually invites (security, performance, correctness...). Name the lenses that were actually load-bearing; skip narrating the ones that weren't.

For anything beyond the most mechanical fix, ask once: *is the target's structure itself wrong, such that no incremental fix will help?* If yes, argue for redesign rather than patching — sketch the alternative, estimate the cost of redesign against the cost of continuing to patch, and stop for the operator's decision rather than redesigning unasked.

Then pick one:
- **A change.** State the single highest-leverage thing to do and why, make a falsifiable pre-commit prediction ("I will do X; I expect Y; I expect Z not to happen"), then act. Verify the outcome against the prediction.
- **An argument for redesign.** Surface it; do not act on it without confirmation.
- **Silence.** Nothing actionable. Name the bar this was tested against and what's still untested — unbounded silence is not a valid form.

If you back out of something mid-run (tried X, reverted after Y showed it was wrong), mark `[!REVERSAL]` — within-run reversals are as much evidence of honest reasoning as cross-run ones, and hiding them inflates the trail's apparent success rate.

### 3. Trail — always, every run, no exceptions

Append one entry to `.acm/audit-trail.md` in the target repo (create it with a one-line header if it doesn't exist yet: `# Audit Trail — <repo name>`). This is the one step that is never skipped, never made optional, regardless of how trivial the run was — a run with no entry is a run that didn't happen, as far as anyone auditing this later can tell.

**Depth tiers — pick the lowest one that's honest:**

- **Tier 1 — Micro** (mechanical, no real decision: typo fix, direct question answered, one obvious command run). One or two lines: what was asked, what was done, outcome. No Decision/Prediction/Reflection scaffolding.

  ```
  ## 2026-07-03 — fix-typo-readme
  Asked to fix "recieve" typo in README. Fixed. No decisions, nothing notable.
  ```

- **Tier 2 — Standard** (a real choice existed between plausible alternatives, or the work could plausibly be second-guessed later). Compact: interpretation (one line, only if it wasn't obvious), decision + one-line prediction, outcome vs. prediction, one line naming the one blind spot or nothing-found. Skip the full 4-trigger reflection ceremony unless one of the triggers below actually fires.

- **Tier 3 — Full** (structural or architectural decisions, redesign arguments, anything the operator would want deeply audited, anything touching an area a past `[!REVERSAL]` or recurring finding-class already flagged). The complete original shape: Interpretation, Examination (lenses named), Challenge, Decision + Prediction, Action, Reflection (falsifiable model-claim, named blind spot, imagined expert pushback), the four across-trail triggers each explicitly evaluated, Candidate Next Moves.

**Escalate a tier** (never de-escalate below what's honest) when: the operator pushes back, the change is hard to reverse, a past `[!REVERSAL]` touched this area, or something about the run surprised you mid-work. When genuinely unsure which tier, pick the higher one — the cost of over-recording a routine entry is small; the cost of under-recording a real decision is a broken audit trail. If the surprise surfaces only after the entry is already committed, don't edit it in place — append a short follow-up entry cross-referencing the original by slug, at whatever tier the new information actually warrants.

Use `[!DECISION]`, `[!REALIZATION]`, and `[!REVERSAL]` markers exactly as the full suite does, at whatever tier — these markers are what makes the trail searchable and are never cut for cost, even in a Tier 1 entry, if one genuinely applies.

**What's cut vs. the full Trail skill, on purpose:** no `history.md`/`learning.md` derived-artifact regeneration, no `record.py` dependency, no writer-splitting (having a second, independent agent write the trail entry so the same agent that made the decision can't also be the one who describes it — a stronger anti-rationalization safeguard than this file uses). None of that is required to use this file. If you separately have access to the full suite's `record.py` tooling, it can run against this same `audit-trail.md` later — the entry header format (`## <date> — <slug>`) and marker vocabulary are kept compatible on purpose — but that's optional, not a dependency of anything above.

### 4. Mini-Orient — every 5 entries since orientation.md was last written

Count `## ` headers in `.acm/audit-trail.md`. If `.acm/orientation.md` doesn't exist yet, count from the start of the trail. If it does exist, count only entries written **after its own dated header** — a repo that already had a long trail before this skill ever touched it should not have its first mini-orient timed by an arbitrary global position in history that predates this loop's involvement. When that count reaches 5 (and every 5 after):

1. Read only the **last ~5-10 entries** (not the full history — that's the deliberate cut vs. real Orient, which reads the whole arc).
2. Form **1-3 falsifiable arc-claims** about what this stretch of work shows is true of the target, or what's changing.
3. Check whether a `[!REVERSAL]` or a recurring finding-class shows up across those entries.
4. If something material emerged: update `.acm/orientation.md` (create if absent) with a short "Current claims" section and a "Watch for" line. If nothing material emerged: say so in one line inside this iteration's own trail entry and do **not** rewrite `orientation.md` just to have written something — a mini-orient with nothing to say should say nothing (Convergence Is Silence applies here too).

No freshness-guard, no `record.py`, no `learning.md` extraction — those are exactly the heavy-tooling pieces this cut removes. If you also have access to the full, separate `orient` skill and the target needs its deeper discipline (quality-bar naming, adversarial audit of the arc, loop-effectiveness review), invoke that instead — this mini-orient is a cheap tripwire, not a replacement for it. If you don't have that skill, the mini-orient above is the ceiling this file offers, and that's a deliberate design choice, not a gap to apologize for.

## Self-check before calling a run done

- Did step 3 (Trail) actually happen? If not, the run isn't done yet, regardless of what else was accomplished.
- Did you pick the lowest honest tier, or did you default to Tier 3 out of habit? Defaulting to Tier 3 every time defeats the entire point of this skill.
- If you cut a corner for cost reasons anywhere in this run, is that cut visible in the trail entry, or did it just happen silently?
- If this run built more than one new committed file around an inference from step 0 or step 1, did you actually ask before building the rest of them — or only label the first one unconfirmed and proceed as if that were enough?
