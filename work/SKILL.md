---
name: work
description: 'A standalone, target-agnostic improvement-reasoning skill with full auditability: it can examine and improve anything the model can reason about — code, documents, plans, music, letters, anything — while recording material decisions and their outcomes in an auditable trail. One consolidated loop: Intent, Improve, a condensed Destination process that escalates to a deeper interview when thin, one Orient operation that derives and rates a destination-grounded rubric on first contact and later need-signals, and always-on Trail logging. USE WHEN: you want disciplined, auditable improvement reasoning on any target at a single skill-load, especially in long or frequent sessions where token budget is a real constraint.'
argument-hint: 'The target (repo, file, system) and the request itself'
metadata:
  version: "3.5.0"
---

# work

*Auditable autonomy: reason about anything, improve anything, show the decisions — cheap enough to use every day, without losing the quality.*

**If you're new to this:** "operator" means whoever directs the work — you, if you're the one using this file. "Subagent" means a separate helper agent dispatched with its own fresh context; if your tooling has none, every mention of them is skippable. `.acm/` is short for Agent Context Memory — a small convention: a folder at the root of whatever repo is being worked on, holding plain-text memory in three files — `destination.md` (what this target is for), `orientation.md` (what recent work has concluded, once enough runs exist to conclude anything), and `audit-trail.md` (what happened and why, one entry per run). This file reads and writes those three files and needs nothing else: no tooling, no install step, no sibling files. A few passages below mention a larger "full suite" of separate skills; they exist for people who also have that suite and are safe to skip if you don't.

## Why this exists, and what it trades away

`work` is a standalone skill: an improvement-reasoning architecture that works on any target — a codebase, a letter, a plan, a book, a piece of music — and leaves a full audit trail of how it reasoned. "Target" below always means *whatever is being worked on*, not just software. Its lineage is a consolidation of a larger suite, and that lineage explains its shape:

The full suite (`intent`, `improve`, `destination`, `orient`, `trail`, `probe` — a sixth skill, contamination/pattern-matching detection, deliberately not folded into this fork) was built when token cost wasn't the binding constraint. It costs tokens on two axes: **loading** (five instruction files instead of one) and **ceremony** (a full interpretation + four-lens examination + reflection essay on every run, even a one-line fix).

`work` cuts both axes without cutting the three principles beneath them:

1. **Operator's Intent** — you are given a destination, not a route.
2. **Observable Autonomy** — every material decision is recorded before action and its outcome afterward; an observer must be able to reconstruct what you did and why from the trail alone.
3. **Convergence Is Silence** — finding nothing actionable is a valid outcome. Never manufacture ceremony to look thorough.

**The one rule that makes the trade honest: match reasoning depth to the stakes of the moment, not to a fixed template.** A typo fix and a redesign decision are not the same event and must not cost the same number of tokens to record. Spend full ceremony only on moments that are genuinely hard to reverse or genuinely uncertain; log everything else in one honest line. The depth tiers in step 3 are the mechanism for this — not a suggestion.

And if a cost/quality trade-off is ever genuinely unavoidable in a run, say so in the trail entry. A silent trade-off is exactly the invisible reasoning Observable Autonomy exists to prevent.

## The loop

Four ordinary stages run in sequence — **Destination** (step 0, first contact or a real direction trigger), **understand** (step 1), **work** (step 2), and **Trail** (step 3). **Orient** (step 4) is one operation called from that sequence on first contact and whenever later evidence signals that the target needs re-orientation.

Before the first action, classify the run using step 3's depth tiers: Micro only when the ask is mechanical and contains no real choice; otherwise Standard or Full. If unsure, classify it as decision-bearing. This one early classification controls both the bootstrap cost and when Trail opens.

**One loop, one shape.** This sequence runs identically whether the target is this skill's own repo or any external target — self-targeting is never a special case. The one exception is stakes, not target type: a genuinely small, mechanical ask (the kind that will tier as Micro in step 3) does not create a missing `destination.md` or `orientation.md`. Trail still happens under step 3, creating `.acm/audit-trail.md` if needed; Observable Autonomy is never the skipped cost. Destination and first-contact Orient are required before Tier 2 or 3 work begins, not before a one-line fix.

**Design constraints.** Apply DRY, KISS, and YAGNI to this workflow and to the target: one authoritative definition of each operation, the simplest structure that preserves the destination, and no mechanism without present evidence of need. Prefer designs that make invalid states impossible over reminders that ask agents to avoid them. This file cannot mechanically enforce its own write ordering, so where it can only prescribe an invariant — especially Trail-before-action — it says so rather than claiming a structural guarantee.

**The skill leads this workflow, not the operator.** Assume the operator is new to this file: they should never need to remember to invoke a step. The loop decides when its own moments are due — a destination question, an arc-read, a trail entry — announces in one line what it's doing and why, and names the one decision that belongs to the operator at that moment (confirm a destination, rule on a proposal, answer a question). Hand-holding is part of the job: a workflow the operator has to drive from memory is a workflow that won't happen.

### 0. Destination gate

Before anything else, check the **target repo's** `.acm/` folder (always at the root of the repo being worked on — never the skills install directory).

- If the ask is genuinely Micro, skip this gate and Orient; proceed to step 1 and still complete Trail. Do not create missing destination or orientation files for the Micro run. This exemption also applies when an existing destination is unconfirmed: perform only the mechanical ask, without treating that destination as guidance for broader work.
- If `.acm/destination.md` exists (or the legacy name `.acm/vision.md`): read it, plus `.acm/orientation.md` if present. If the destination is marked unconfirmed, complete a Trail entry for this attempt and stop before Orient or ordinary work; ask the operator to confirm or correct it. For Tier 2 or 3 work, if the confirmed destination exists but `orientation.md` does not, run Orient (step 4) in first-contact mode before step 1; otherwise continue to step 1.
- If neither exists, this is a first run against this target. Run the condensed Destination:
  1. From the request and any visible repo signal (README, recent commits, folder structure), form **1-3 sourced guesses** about what this target is for and who it serves.
  2. Turn the single most load-bearing guess into **one short, answerable question**.
  3. Ask it. If the operator answers, write `.acm/destination.md` from the answer plus the unasked guesses (marked open — not asked, not confirmed). Plain markdown, no special format: what the target is for, who it serves, any confirmed constraints, then an "Open" list holding the unasked guesses. If this condensed pass leaves the destination clearly too thin for the stakes of the ask (an architectural decision, a redesign, anything Tier 3-shaped), escalate: form **2-5 sourced inferences** instead of one, cited to specific evidence, and surface them **one at a time in priority order** rather than batched — the deeper interview method the full `destination` skill uses (`pea/skills/destination/SKILL.md`), approximated inline if you don't have that file loaded. Collapse back to the condensed one-question shape once the thin spot is addressed; this is an escalation for one moment, not a standing heavier mode.
  4. If no answer is available this run (operator unreachable, or says "proceed"), write `.acm/destination.md` from your best reading, clearly marked unconfirmed — the recommended phrase, verbatim: `**Operator not yet confirmed** — revise on first pushback.` Any wording works as long as the unconfirmed status is impossible to miss. Don't block: a marked assumption is a legitimate, auditable state; a missing destination file is not.
  5. Once `.acm/destination.md` exists, re-run this step only on a real trigger — never merely because time passed or a session is new. Three triggers are legitimate: explicit invocation; the operator's own signal that the destination is stale or thin; or **the loop's own evidence** that the destination is exhausted or wrong — a plateaued scorecard whose coverage diff (step 4) came back empty, or observed reality contradicting what `destination.md` claims. A self-triggered run may ask and propose, never settle: its output enters `destination.md` as an appended, dated proposal marked unconfirmed until the operator rules, and step 1's pre-commit read-back applies in full — the skill owns detecting that the destination needs revisiting; the operator owns what it becomes.
  6. **Do not build other committed files around an unconfirmed guess in the same pass.** A guess labeled `unconfirmed` in `destination.md` does not license writing the rest of the target's files as though it were settled — ask before producing those artifacts too.

After Destination is newly confirmed or materially changed, run Orient (step 4) before further Tier 2 or 3 work. A destination change voids the old rubric and ratings; Orient derives the replacement from the new destination rather than carrying stale measurements forward.

**Scoped memory.** Before trusting the target repo's own destination, walk parent directories upward looking for a higher-scope `.acm/destination.md`. Stop at a `.acm-root` marker file (an empty file an operator drops at the top of a workspace to say "don't look higher"), the filesystem root, or after 4 levels. Higher scope wins on coordination matters. When the difference matters to a decision, label which scope you're reading from ("workspace mandate" vs. "repo mandate").

### 1. Understand the ask (Intent, fused)

Before touching the target, run one fast check: *what does the operator actually want, and is there a plausible alternative reading?* Three cases, three narration costs:

- **Unambiguous and mechanical** (a named file, a one-line fix, a direct yes/no): don't narrate at length — one clause inside the trail entry's own description is enough. A paragraph explaining that "fix the typo on line 12" means fixing the typo on line 12 is waste, and waste is what this skill exists to cut.
- **Minor interpretive gap** (clear enough to act, but you're making a judgment call on scope, format, or approach): proceed, and flag the specific choice in one sentence in the trail entry, so a wrong call is cheap to correct.
- **Material divergence** (the literal request and the likely goal point different directions, or the ask is bare — "continue", "keep going", "next"): stop and narrate before acting. State what you believe the destination is, what would count as success, and at least one alternative reading you considered and rejected, with why — if you can't name one, you likely pattern-matched instead of interpreting. For a bare ask, form 1-3 sourced hunches from `.acm/destination.md`, `.acm/orientation.md`, the last few trail entries, and what the conversation itself has emphasized, corrected, or redirected toward, about what matters most now; surface the single most useful question; and if no answer comes back, proceed on your best hunch as an explicit assumption.
- **Internal contradiction** (the request conflicts with itself, or with something the operator stated earlier): name the contradiction explicitly rather than silently resolving it by picking one side. Surface both readings and let the operator adjudicate — a confidently-executed resolution of a contradiction the operator never saw is a distinct failure from misreading a clear-enough ask.

One class of edit always gets its interpretation read back to the operator **before** committing, not after: anything touching `.acm/destination.md` or the target's own statement of what it is. A misreading at that layer is cheap to catch before commit and compounding after — every downstream run inherits it.

This step replaces a standalone Intent invocation. It is never optional — only its narration length varies.

### 2. Work — examine, challenge, decide, act

Do the work, scaling the rigor of examination to the stakes. Four lenses are available as thinking tools, not a checklist: **Purpose** (does the target achieve what it's for, against `.acm/destination.md`?), **Inconsistency** (does it contradict itself or its own stated rules?), **Overburden** (does it ask more of its users or maintainers than it's worth?), **Waste** (does everything here still earn its place?) — plus whatever the target itself invites (security, performance, correctness...). Name the lenses that were actually load-bearing; don't narrate the ones that weren't. When the examination is a fidelity audit — checking a derivative against its source (a consolidation against its suite, a summary against its document, a port against its original) — compare against the source directly; self-review of the derivative alone reliably misses what was dropped.

The rubric and ratings belong exclusively to Orient (step 4), not to a second scoring path here. Treat them as temporary diagnostics of the current plateau — void when the destination or focus shifts, never standing targets to optimize toward. An explicit "rate this" request triggers Orient; it does not create a separate measurement procedure. A metric that outlives its plateau starts prescribing a route.

For anything beyond a mechanical fix, pause on this before deciding: *What am I not seeing? Am I anchored on the most obvious finding and missing a subtler, more important one?* Then the redesign question: *is the target's structure itself wrong, so that no incremental fix will help?* If the structure itself is wrong, don't patch — argue for redesign: sketch the alternative, weigh redesign cost against the cost of continuing to patch, and stop for the operator's decision.

Then pick exactly one outcome:

- **A change.** Name the single highest-leverage thing and why. Make a falsifiable prediction before acting ("I will do X; I expect Y; I expect Z *not* to happen"), act, then verify the outcome against the prediction.
- **An argument for redesign.** Surface it. Do not act on it without confirmation.
- **Silence.** Nothing actionable — a valid outcome, but bound it: name the bar this was tested against and what remains untested. Unbounded silence is not a valid form.

If you back out of something mid-run (tried X, reverted when Y proved it wrong), mark it `[!REVERSAL]`. Within-run reversals are as much evidence of honest reasoning as cross-run ones; hiding them inflates the trail's apparent success rate.

### 3. Trail — always, every run, no exceptions

Record one entry in `.acm/audit-trail.md` in the target repo, using the header format `## <date> — <slug>` (create the file with a one-line header if absent: `# Audit Trail — <repo name>`, where the repo name is simply the name of the folder holding this `.acm/`). Prefer the em-dash separator; where a write path cannot carry the em-dash safely (some terminal transports corrupt it), an ASCII `--` separator is the accepted fallback — never a mojibake-corrupted entry. For Tier 1, append the complete entry after the mechanical action. For Tier 2 or 3, open the entry immediately after deciding and **before acting**: append all pre-action reasoning required by the selected tier — interpretation when needed, decision, and falsifiable prediction, plus examination and challenge for Tier 3. After verification, append the outcome, blind spot or reflection, any next move, and cost line to that same entry. Never reconstruct the pre-action segment after seeing the result; the two appends are what make the reasoning and prediction auditable rather than merely retrospective. This is the one step never skipped and never optional, however trivial the run: a run with no completed entry is a run that didn't happen, as far as anyone auditing later can tell.

Before closing the entry, evaluate every Orient trigger in step 4. If one fired, record the trigger and Orient prediction before updating `orientation.md`, run Orient in this same run, then append its outcome and close the entry. An explicit orientation or rating request takes this route immediately after step 1: open Trail, run Orient, and finish without manufacturing an ordinary target change.

**Depth tiers — pick the lowest one that's honest:**

- **Tier 1 — Micro** (mechanical, no real decision: typo fix, direct question answered, one obvious command). One or two lines: what was asked, what was done, outcome. No decision/prediction/reflection scaffolding, and no next-move line — work with no real decision rarely implies a meaningful next step.

  ```
  ## 2026-07-03 — fix-typo-readme
  Asked to fix "recieve" typo in README. Fixed. No decisions, nothing notable.
  Cost: light — 2 tool ops, 1 file.
  ```

- **Tier 2 — Standard** (a real choice existed between plausible alternatives, or the work could plausibly be second-guessed later). Compact: interpretation in one line (only if it wasn't obvious), decision plus a one-line prediction, outcome vs. prediction, one line naming the blind spot (or the nothing-found), and one line naming the most obvious next-step candidate if one stands out — skip it if none does; silence is valid here too. Skip the full reflection ceremony unless one of the escalation triggers below fires.

  ```
  ## 2026-07-03 — split-config-loader
  Read "clean up config handling" as splitting the loader, not rewriting it. [!DECISION] — rewrite was plausible but riskier.
  Predicted the split leaves all 12 tests green; it did.
  Blind spot: no test covers the env-override path. Next: cover it.
  Cost: moderate — 9 tool ops, 4 files, no subagent.
  ```

- **Tier 3 — Full** (structural or architectural decisions, redesign arguments, anything the operator would want deeply audited, anything touching an area a past `[!REVERSAL]` or a recurring finding-class — the same kind of defect turning up across separate runs — already flagged). The complete shape: interpretation, examination with lenses named, challenge, decision + prediction, action, reflection (a falsifiable claim about the target, a named blind spot, an imagined expert's pushback), the four across-trail triggers each explicitly evaluated — *did the operator ask for a deeper audit? is a recurring finding-class present? does this run contradict a prior `[!REALIZATION]`? is a silence declaration imminent?* — and candidate next moves.

**Escalate a tier — never de-escalate below what's honest — when:** the operator pushes back, the change is hard to reverse, a past `[!REVERSAL]` touched this area, or something about the run surprised you mid-work. Genuinely unsure which tier? Take the higher one: over-recording a routine entry costs little; under-recording a real decision breaks the audit trail. If a surprise surfaces only after the entry is committed, don't edit it in place — append a short follow-up entry cross-referencing the original by slug, at whatever tier the new information warrants.

If a run honestly began as Micro but reveals a real choice, stop before any further action and reclassify it. Open a Standard or Full Trail entry that discloses the already-completed mechanical action and records the newly discovered decision and prediction before acting on that decision. The original mechanical action did not retroactively contain a choice; the newly discovered one does, and cannot proceed without its pre-action record.

**Cost line — every entry, every tier.** End each entry with one line of observed run cost: a bucket (light / moderate / heavy) plus the countable proxies behind it — tool operations, files read or written, subagents dispatched. Count the proxies roughly but consistently from run to run — the trend across entries is what Orient reads, not the unit definition. Use real token counts only if the platform actually exposes them; **never invent a token number** — a plausible-looking count with no source is fabricated telemetry in the one file that must never lie. And the cost line is telemetry to reflect on, never a target to minimize: cutting honest depth to make the line look cheaper is the de-escalation this step already forbids, now with a number attached.

**Markers** make the trail searchable and are never cut for cost, at any tier, when one genuinely applies:

- `[!DECISION]` — a genuine choice between plausible alternatives; the moment a future audit wants to find first.
- `[!REALIZATION]` — something shifted in what this run understood about the target that wasn't known going in.
- `[!REVERSAL]` — an attempted approach was backed out of after it proved wrong.

**Cut from the full Trail skill, on purpose:** derived-artifact regeneration (`history.md`/`learning.md` — rebuilt summary files the full suite maintains alongside its trail), the `record.py` tooling (the full suite's script that runs that regeneration and enforces entry formatting), and writer-splitting (a second, independent agent writing the trail entry, so the agent that decided isn't also the one describing — a stronger anti-rationalization safeguard than this file uses). None of it is required here. The entry header format (`## <date> — <slug>`, em-dash form) and the marker vocabulary are kept compatible with that tooling on purpose, so it can be run against this same `audit-trail.md` later if you have it — optional, never a dependency. Know the bound: that tooling's parser currently reads only the em-dash form, so entries written with the `--` fallback are invisible to it until it learns the fallback.

### 4. Orient — one operation, invoked on first contact and later signals

Orient answers one question: **where is this target relative to its confirmed destination, according to the evidence available now?** It owns the destination-derived rubric, ratings, arc-claims, and candidate next moves. There is no bootstrap variant, condensed variant, or separate scorer: invocation context changes the evidence available, never the procedure or output contract.

Run Orient in the current run when any of these fires:

- **First contact** — Tier 2 or 3 work has a confirmed destination but no `orientation.md`, including a target with no Trail history. Run Orient before ordinary work.
- **The destination changed** — the previous rubric is void. Run Orient before ordinary work and derive a replacement rubric from the confirmed destination.
- **The operator asks for orientation or a rating** — both requests invoke this operation.

- **The arc contradicts itself** — this run hit a `[!REVERSAL]` or a missed prediction in territory recent entries treated as settled, or the same finding-class has now turned up across separate runs.
- **The operator pushed back** — a correction means the arc misread something; check what else the misreading touched before building on it.
- **A stretch just closed** — a tracked open item converted, a phase completed, or the next move is genuinely unclear: natural arc boundaries are where an arc-read pays best.
- **`orientation.md` reads stale** — its claims are contradicted by what recent entries actually show, or cost lines look like they're drifting without the stakes drifting with them.
- **Backstop:** none of the later-run signals above has fired across about **5 completed entries this loop wrote after the entry containing the most recent Orient**. The 5 is deliberately arbitrary — a cheap tripwire, not the logic. It exists because the run that most needs Orient is often the one least able to notice it; the signals above are the real trigger, the counter only catches what judgment misses.

**Trail timing.** Orient writes `orientation.md`, so it is an auditable action. For first contact, destination change, or a standalone orientation/rating request, open the Tier 2 or 3 Trail entry with the trigger, evidence plan, and falsifiable prediction before running Orient. For a signal discovered during ordinary work, record the trigger before updating `orientation.md`, then close the same Trail entry after Orient. This ordering is prescribed and auditable, but Markdown cannot make retrospective writing mechanically impossible; independent capture is required for that stronger guarantee.

**Multi-writer trails.** On targets whose `.acm/` is also written by other agents or target tooling, the backstop counts only entries this loop wrote. Other entries remain evidence to read, not a schedule this loop can breach. Where target machinery owns `orientation.md`, append a dated Orient addendum instead of overwriting owner sections.

1. **Read the destination and inspect the current target.** Derive roughly **5-10 measurements** from the destination's actual obligations, including cost or ceremony where the destination makes it material. Apply DRY, KISS, YAGNI, and correctness-by-construction as examination lenses when relevant; they do not replace target-specific measurements.
2. **Read the available arc evidence.** On first contact, state that no prior arc exists and use direct target evidence. On later invocations, read only the last **~5-10 relevant Trail entries** by default. Expand to the full arc only when the trigger or stakes require it; YAGNI forbids paying whole-history cost by habit.
3. **Rate every measurement.** Use a consistent scale such as `/10`; cite the file, test, target observation, or Trail entry supporting each rating; show the delta when a comparable prior rating exists; and give exactly one destination-compatible improvement candidate per measurement. Never fabricate evidence. If an axis is genuinely unobservable, rate it `not evidenced`, explain what evidence is missing, and treat obtaining that evidence as the candidate move — never leave an unexplained blank.
4. **Test the frame.** Check destination obligations against the measurement set; uncovered obligations become measurements or work. Check reversals, recurring finding-classes, missed predictions, suspiciously clean history, ignored candidate moves, and cost drift. If ratings flatline under an unchanged destination, distinguish exhausted territory from coarse measurements. An empty destination-coverage diff plus a served plateau triggers Destination (step 0, trigger 5); Orient may propose that question but cannot redefine the destination.
5. **Write one coherent orientation.** Update `.acm/orientation.md` with the dated rubric and ratings, **1-3 falsifiable Current claims**, the highest-leverage candidate next moves or todo, active operational rules that recent evidence supports, a **Watch for** line, and loop-effectiveness notes when warranted. On first contact the claims describe current target evidence rather than a nonexistent historical arc. Scores remain temporary plateau diagnostics and become void when destination or focus changes.
6. **Bound silence.** If Orient finds nothing actionable, still record the ratings and state exactly which quality bar and surfaces reached silence, plus what remains untested. Do not manufacture a change merely to move a score.

No freshness guard (the full suite's staleness check, flagging when a derived artifact like `history.md` no longer matches the trail it was built from), no `record.py`, no `learning.md` extraction — exactly the heavy tooling this cut removes. If you separately have the full `orient` skill and the target needs whole-arc derived-artifact discipline, invoke that instead. The operation above remains Work's single Orient contract.

## Self-check before calling a run done

- Did step 3 (Trail) actually happen? If not, the run isn't done, whatever else was accomplished.
- For a Tier 2 or 3 run, was all pre-action reasoning required by its tier appended before action (including examination and challenge for Tier 3), with the outcome appended only after verification?
- At first contact and Trail-append time, did you check every Orient trigger and the ~5-entry backstop? If one fired, did the same Orient operation run in this run, refresh destination-derived ratings, and record its result? A due-but-skipped Orient or a separately improvised scorer is a breach, not a deferral.
- Did you pick the lowest honest tier — or default to Tier 3 out of habit? Habitual Tier 3 defeats the entire point of this skill.
- If you cut a corner for cost anywhere in this run, is the cut visible in the trail entry — or did it happen silently?
- If this run built more than one new committed file around an inference from step 0 or step 1, did you ask before building the rest — or only label the first one unconfirmed and proceed as if that were enough?
