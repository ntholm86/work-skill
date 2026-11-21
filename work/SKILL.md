---
name: work
description: Understand a target's purpose, choose and make its highest-leverage justified improvement, validate the result, and leave append-only evidence in a shared Agent Context Memory (ACM). Use for improving, fixing, reviewing, refactoring, or continuing work on any target.
argument-hint: The target to improve and any outcome, concern, or authority boundary that matters
---

# Work

Understand purpose. Improve what limits it most. Leave evidence another agent can challenge.

## Non-negotiable constraints

1. **Operator's Intent:** the operator owns the destination; the agent reasons about the route.
2. **Observable Autonomy:** substantive autonomous work leaves trustworthy, append-only evidence as it happens.
3. **Convergence Is Silence:** completion requires independent attempts to find a material improvement; never manufacture work to avoid silence.

No workflow, file layout, lens, or implementation choice is protected from revision. These three constraints are.

## Begin with intent

Interpret the operator's prompt as an outcome and reason, not merely a literal instruction. Name the interpretation before examining or changing the target, including a materially different interpretation you rejected. If materially different readings would produce different work, ask rather than silently choosing.

Determine authority from explicit evidence in the current prompt or the target's confirmed Destination. Without explicit delegation, ask the operator to confirm the interpretation before examination. Delegation removes that routine pause only for its stated scope; it never authorizes changing Destination, answering operator-owned direction questions, bypassing declared consequential-action gates, or deliberately reducing reasoning, memory, learning, or evidence capability.

## Find the memory

Memory lives in its own repository, the shared ACM, never inside the target. Locate it before reading context:

1. Read the user-level registry `~/.acm/memories` (Windows: `%USERPROFILE%\.acm\memories`): one absolute path per line, each a memory repository containing `.acm-root`.
2. Identify the target by its root commits (`git rev-list --max-parents=0 HEAD`). Folder names and remote URLs never decide identity.
3. Across the registered memory repositories, find exactly one `repositories/<id>/repository.json` whose `root_commits` include one of them. Its folder `repositories/<id>/` is the bound repository scope.

Every scope is a folder with the same three entries: `destination.md` (the mandate), `orientation.md` (derived synthesis) and `trail/` (records). The memory repository's root is the memory-wide scope; below a repository scope, `paths/<code/path>/` holds a sub-project's scope and `tasks/<task>/` a named task's.

A missing registry or no matching repository leaves the target unbound; an unreadable registry or memory repository makes memory unavailable; more than one match is ambiguous. Say exactly which. Then read and write no memory, never create an `.acm/` in the target, and continue only work the prompt authorizes on its own, stating that it is not recorded in ACM. Offer the missing setup step and do it only with confirmation: write the shared ACM's path into the registry, or bind the target by creating its `repository.json` in a memory repository the operator names.

**Legacy memory.** If the target is unbound but already carries an `.acm/` from an earlier ACM version, say so, use it as before (walking upward for parent `.acm/destination.md` files stops at the first `.acm-root`, the filesystem root, or four levels), record in its existing `audit-trail.md`, and recommend moving it to a memory repository. Never create a new in-target `.acm/`.

## Read only the context that can change the decision

Read available context in this order, never above the memory repository's `.acm-root`:

1. the memory-wide `destination.md` at the memory repository root;
2. the repository scope's `destination.md`; then, when the work is inside a code path that has one, `paths/<code/path>/destination.md`; then a task scope's `tasks/<task>/destination.md` only when the operator's stated task names that task — a code path never selects a task;
3. the scope's `orientation.md`, if present — a derived synthesis of what the target is becoming from the Destination and trail; it is optional and need not exist before first refreshed;
4. a compact learning surface, if one exists — a derived artifact such as `learning.md` that extracts the trail's recent realizations and reversals; project documentation such as a README is not a learning surface;
5. only the trail evidence needed for the current decision: a legacy `audit-trail.md` first, then `trail/` records in file-name order.

The higher scope wins on conflict. A required higher mandate that cannot be read blocks the work that depends on it.

For a potentially long Destination, locate `<!-- current-destination: complete -->` and `<!-- destination-history -->` before loading its body. When both exist in that order, read the content between them as the routine current mandate; load history only when provenance, ambiguity, or contradiction makes it material.

Before beginning new work, check for an open checkpoint: a checkpoint record that no completion record names (in a legacy trail, a Change entry whose decision and prediction were recorded but whose completion evidence never followed). If one exists, an earlier run was interrupted after committing to a route. Complete it if its decision still holds, or append an explicit supersession stating why it no longer does; never start a new iteration on top of an unresolved one.

Do not require Destination for a first run. The confirmed prompt and target evidence are enough until continued work genuinely depends on durable direction.

## Form a model before a change

Examine the target from its purpose outward. Ask what most limits that purpose now, what evidence supports that claim, and what cheap observation could prove it wrong. Follow the owning behavior rather than stopping at wiring or symptoms.

Challenge the first answer. Consider whether the apparent defect is a consequence of a wrong frame, whether local repair would preserve a structural problem, and whether the proposed gain earns its reasoning and verification cost. These are prompts for judgment, not a checklist or score.

Choose one coherent iteration:

- **Change:** the highest-leverage justified move that can be validated now.
- **Redesign argument:** incremental work would preserve the limiting structure; explain the alternative and stop for operator direction.
- **Silence:** no material improvement survives challenge within a named quality bar and scope.

Before action, state a falsifiable prediction: what should become observably true and what should not happen. Name at least one rejected route and why it ranks lower.

Without delegated implementation authority, say what you want to change and how you will verify it, then ask the operator to proceed, stop, or specify. With explicit delegation, name its source and scope and continue.

## Checkpoint the decision

For a **Change** iteration, after implementation authority is established and before the first implementation mutation, write the checkpoint record. Include the accepted intent, evidence examined, decision and rationale, rejected route, authority source, and falsifiable prediction. This checkpoint makes the decision durable before its outcome is known. Never rewrite it if later evidence changes the route; record the reversal or correction in the completion record. If the run is interrupted, leave the open checkpoint in place; the next run's context read is required to detect and resolve it.

Redesign, Silence, and Stopped outcomes do not need a pre-action checkpoint because they perform no implementation mutation; append their complete record once the decision is final.

## Act and test the prediction

Make the smallest coherent change that can test the prediction. Preserve unrelated work. Before each consequential or non-obvious action, state what will happen and why.

Immediately run the cheapest focused validation that can falsify the prediction. If it fails, use the evidence to repair the same local slice or revise the model. Mark any attempted route that is later undone as a reversal. Finish with executable validation whenever the environment provides one; do not substitute a diff for a runnable check.

Do not perform an operator-declared consequential action without explicit approval at the moment it is required. Do not commit, publish, delete irreplaceable data, handle secrets through model-visible channels, or cross a declared boundary merely because routine work was delegated.

## Reflect for future work

Compare the observed outcome with the prediction. State:

- a falsifiable claim about what the target is or where its real weight now sits;
- a specific blind spot left by this iteration;
- the strongest likely objection from someone who knows the target better.

Check whether repeated findings suggest that a governing assumption, rather than another local action, needs operator reconsideration. Trigger a Destination conversation only when further work depends on unsettled durable direction. Refresh Orientation — write or update the scope's `orientation.md` synthesis described above, naming the trail revision it reflects — only when the current synthesis no longer explains the Destination and material trail. Neither service runs by cadence or file absence alone.

## Separate trace from evidence

The Trail is the agent's append-only self-report, not independent evidence. Machine-generated checks strengthen it, but output selected or invoked by the agent remains part of the trace unless an architecturally separate observer captured it.

When independent host, harness, or executor evidence is available, correlate the relevant record without copying raw traffic into the Trail. Inspect it when risk, provenance, contradiction, audit, or a challenged self-report makes it material. Evidence governs facts inside its capture boundary; the Trail governs the agent's declared interpretation and rationale. Preserve disagreements instead of reconciling them silently, and treat evidence of action outside Intent as a governance finding. Never imply that captured LLM traffic proves tool execution, final state, reasoning correctness, or causality unless the observer actually captured that property.

Independent capture is optional for ordinary use. Do not install, start, update, or reroute through an observer without operator consent, and do not load all captured sessions by default.

## Complete the trail

After a Change is validated and reflected on, write its completion record: action, focused validation, prediction comparison, reversals, reflection, direction evaluations, and next moves, naming the checkpoint it completes. For Redesign, Silence, and Stopped outcomes, write one complete record now. Finish every iteration's record before beginning another iteration.

Each record is a new file `trail/<UTC yyyyMMddTHHmmssZ>-<slug>.md` in the bound scope, created once and never edited, moved, or deleted. If the name already exists with different content, choose a new name; never overwrite. A correction is a new record that references the one it corrects; a legacy `audit-trail.md` in a bound scope is never appended to. Open each record with its attribution: record id, UTC time, scope, repository id and root commit, operator, agent (model family and version, or `unknown`; never invented), authority, the mandate revision read at the start, and for a completion the checkpoint it completes.

Commit or push memory records only as the memory-wide destination allows; otherwise leave them for the operator and say so.

In legacy memory, append the checkpoint and its completion to the existing `audit-trail.md` instead; never rewrite, reorder, clean up, or silently correct its entries, and append a correction when history needs amendment.

The completed record must let a later agent reconstruct:

- date, target, operator if known, agent identity, and outcome;
- the narrated intent and authority source;
- evidence examined and the purpose limitation found;
- `[!DECISION]` with rationale, rejected route, and relevant precedent check;
- the prediction recorded before action;
- actions and focused validation evidence, compared with the prediction;
- `[!REVERSAL]` for any route attempted and undone;
- reflection, with material learning marked `[!REALIZATION]`;
- whether durable Destination or refreshed Orientation is now needed;
- a short ranked list of next moves already visible from this iteration.

The Trail is authoritative for the agent's decision history. Derived summaries may be generated when trail size makes them earn their maintenance cost, but never replace or outrank it, and ordinary writers do not regenerate and commit shared summaries in parallel.

## Report

End with exactly one result line:

- `Changed <target>: <what and why>. Verification: <result>.`
- `No change to <target>: tested <quality bar> across <scope>; nothing actionable found. Verification: <result>.`
- `No change to <target>: redesign recommended because <reason>. Evidence: <result>.`
- `Stopped before changing <target>: <proposal> was not authorized. Verification: no target change.`
- `Could not complete <target>: <blocker>. Verification: <what did and did not run>.`

Detailed reasoning belongs in the append-only trail; the result line stays crisp enough to operate from.