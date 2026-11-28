# Work

Work is a single agent skill: the Principles of Earned Autonomy (PEA) in a lightweight edition, and the skill that lets an agent use Agent Context Memory (ACM) properly. It understands a target's purpose, changes what limits it most, validates the result, and records evidence another agent can challenge.

Name it in a prompt and it is designed to work without reading the ACM specification; that bar is stated, not yet demonstrated. [Agent Cognition Skills (ACS)](https://github.com/ntholm86/agent-cognition-skills) is the full alternative; both work with the same ACM, called Shared ACM when a team uses it.

It is designed for delegated work without assuming unlimited authority. You define the goal and any actions that always require approval. The agent chooses the route only within that boundary, narrates its interpretation and decision, and records each substantive iteration in ACM.

## Install

Copy this repository's `work` directory into the skills location for an agent host that supports Agent Skills:

```text
<repository-root>/work/SKILL.md  ->  <agent-skills>/work/SKILL.md
```

No package or runtime is required.

## Connect ACM (once per machine)

The memory lives in its own ACM repository, never inside the repositories you work on. A team uses Shared ACM. Clone it once and add its absolute path as one line in `~/.acm/memories` (Windows: `%USERPROFILE%\.acm\memories`; UTF-8, with or without a BOM).

The skill identifies a repository of work by its root commit and finds its scope in ACM (`repositories/<id>/repository.json`), so renaming a clone keeps its memory and two same-named repositories are never mixed up. If a repository is not bound yet, the skill says so, offers to bind it with your confirmation, and records nothing in the meantime; it never creates a hidden local memory. Repositories that still carry an `.acm/` folder from earlier ACM versions keep working as legacy memory.

## First run

Ask the agent to use Work on a real target and state the outcome you care about:

```text
Use the Work skill on this repository. Find and implement the highest-leverage
change toward making the command-line errors useful to a first-time user.
```

By default, the agent pauses twice: once to confirm what it understood before examination, and once before implementing its proposed change. You can delegate either routine pause explicitly for a run:

```text
Use the Work skill on this repository. I delegate routine intent confirmation and
implementation selection for this run. Do not publish, delete data, change the
project's goal, or reduce evidence without asking me.
```

During the run you should see the interpretation, the selected limitation, a prediction, the action, focused validation, and a final result line. Durable detail is written to the repository's ACM scope as create-only records (`records/<time>-<slug>.md`); a record's content is never changed, so several people and agents can record at once without overwriting each other.

## Optional durable direction

For work that continues across sessions, add `goal.md` to the repository's ACM scope and describe the purpose, durable constraints, authority boundaries, and unresolved questions that genuinely change route selection, plus a `## Human gate` section saying where a human reviews the work and what the agent may do before that review and without it (a mandate that does not state its gate is incomplete). A `goal.md` at the ACM repository's root governs every repository in it.

Goal remains operator-owned. Work may identify a question that needs your decision, but it cannot answer or alter that direction on your behalf.

## What to inspect

After a run, the final result line tells you what changed and whether validation passed. The trail records in ACM explain why the route was chosen, what evidence could falsify it, what was rejected, what was learned, and what remains uncertain.

## Conformance

Work follows the ACM specification's current text (v0.8.0) and claims no conformance level; the specification's checks are specified tests, and none has been run against Work by an independent evaluator. Work is prose, so everything below is an instruction to the agent, not something Work enforces. **Stated in the skill:** the mandate gate and its confirmation (R-02, R-09), trust ordering and memory content as data (R-01, R-03), authority across scopes and mid-work changes (R-10), degraded memory reported, with no competing local trace and no queued record called accepted (R-11), memory in its own repository, never in the target (R-12; this repository's git history up to commit 105a1dc still carries its former in-repository `.acm/`), scope resolution, escaping, moves and no escape from the memory repository (R-14, R-15; the agent resolves by reading, no tool returns the whole chain), the record header including `format: 1` and every governing mandate revision read (R-16), the policy asked for before recording and erasure and extraction needing the operator's authorization (R-07, R-08; R-21 applies only as that prohibition, Work having no extraction pipeline), and convergence evidence recorded with the evaluator and its independence (R-17). **Partly met:** derived views kept by small dated sourced items with an author and a stated uncertainty, but checked for freshness by comparing the newest record id, which lists `records/` and does not detect a record written with an older id than the learning names (R-19); binding by root commit, with a fork or copy detected only when the binding lists `locators` (R-13; a binding without locators binds by root commit alone, and a fork that keeps the original as a remote still matches; two bindings sharing a root commit are ambiguous, so a fork cannot be bound separately from its original); create-only records with collisions reported (R-18; atomic acceptance and the difference between a record written and one the memory accepted rest on the memory repository, which meets two clones writing the same name only as a merge conflict that the skill says to keep as two records); a bounded, stated start-up read (R-20; finding an open checkpoint reads every record header in the narrowest scope and the freshness check lists its `records/`, and the optional checker's `--history` scans every record, so those steps grow with the scope or the memory); a run with no goal, governed by the operator's confirmed prompt alone and recorded as `mandate: none` and not a governed interval (R-09's missing-mandate check is not met for that run; with no memory-wide goal the R-07 policy is asked for and records wait), the checkpoint before the first change, which the memory has accepted then only if the memory-wide goal lets the agent commit it, and, in a review-gated Change, the operator's confirmation, which is written down only in the completion record's authority and not before the first change (R-09, R-11, R-18). **Not met:** independent evidence capture (R-04, which needs a separate component) and with it the evidence half of R-03, since Work reads no evidence tier, and structural protection of records and mandates against the agent that writes the memory (R-05, R-06): the memory repository must provide it, and the suite's optional `memory_check.py --history` detects an edited, deleted or renamed record after the fact without stopping a writer who can rewrite the repository. R-07 is met only once the memory's principal has set a policy; Work asks and does not set one. **Legacy mode** (an in-repository `.acm/`) does not meet R-05, R-11, R-12, R-13, R-16 or R-18, and has no path scopes (R-14, R-15). Untested: that a fresh agent following the skill behaves correctly against a real bound scope.

## This repository

The repository is named `work-skill`; its sole installable artifact is the `work` directory, whose basename matches the `name: work` frontmatter. Its own development memory is kept in the author's private memory repository (scope `work-skill`), not in this repository; the earlier in-repository `.acm/` remains in git history up to commit 105a1dc.

---

Author: [Nils Wendelboe Holmager](https://nilsholmager.com/) · [Project context and connected work](https://nilsholmager.com/research/work-skill/)
