# Work

Work is a single agent skill: the Principles of Earned Autonomy in a lightweight edition, and the skill that lets an agent use a Shared Agent Context Memory (SACM) properly. It understands a target's purpose, changes what limits it most, validates the result, and records evidence another agent can challenge.

Name it in a prompt and it is designed to work without reading the SACM specification; that bar is stated, not yet demonstrated. The [Principles of Earned Autonomy skills suite](https://github.com/ntholm86/principles-of-earned-autonomy-skills-suite) is the full alternative; both work with the same shared SACM.

It is designed for delegated work without assuming unlimited authority. You define the mission and any actions that always require approval. The agent chooses the route only within that boundary, narrates its interpretation and decision, and records each substantive iteration in the shared SACM.

## Install

Copy this repository's `work` directory into the skills location for an agent host that supports Agent Skills:

```text
<repository-root>/work/SKILL.md  ->  <agent-skills>/work/SKILL.md
```

No package or runtime is required.

## Connect the shared SACM (once per machine)

The memory lives in its own repository, the shared SACM, never inside the repositories you work on. Clone it once and add its absolute path as one line in `~/.acm/memories` (Windows: `%USERPROFILE%\.acm\memories`; UTF-8, with or without a BOM).

The skill identifies a repository of work by its root commit and finds its scope in the shared SACM (`repositories/<id>/repository.json`), so renaming a clone keeps its memory and two same-named repositories are never mixed up. If a repository is not bound yet, the skill says so, offers to bind it with your confirmation, and records nothing in the meantime; it never creates a hidden local memory. Repositories that still carry an `.acm/` folder from earlier ACM versions keep working as legacy memory.

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
project's mission, or reduce evidence without asking me.
```

During the run you should see the interpretation, the selected limitation, a prediction, the action, focused validation, and a final result line. Durable detail is written to the repository's scope in the shared SACM as create-only records (`records/<time>-<slug>.md`); a record's content is never changed, so several people and agents can record at once without overwriting each other.

## Optional durable direction

For work that continues across sessions, add `mission.md` to the repository's scope in the shared SACM and describe the purpose, durable constraints, authority boundaries, and unresolved questions that genuinely change route selection, plus a `## Human gate` section saying where a human reviews the work and what the agent may do before that review and without it (a mandate that does not state its gate is incomplete). A `mission.md` at the shared SACM's root governs every repository in it.

Mission remains operator-owned. Work may identify a question that needs your decision, but it cannot answer or alter that direction on your behalf.

## What to inspect

After a run, the final result line tells you what changed and whether validation passed. The trail records in the shared SACM explain why the route was chosen, what evidence could falsify it, what was rejected, what was learned, and what remains uncertain.

## Conformance

Work follows the SACM specification's current text (v0.7.1) and claims no conformance level; the specification's checks are specified tests, and none has been run against Work by an independent evaluator. Work is prose, so everything below is an instruction to the agent, not something Work enforces. **Stated in the skill:** the mandate gate and its confirmation (R-02, R-09), trust ordering and memory content as data (R-01, R-03), authority across scopes and mid-work changes (R-10), degraded memory reported, with no competing local trace and no queued record called accepted (R-11), memory in its own repository, never in the target (R-12), scope resolution, escaping, moves and no escape from the memory repository (R-14, R-15; the agent resolves by reading, no tool returns the whole chain), the record header including `format: 1` and every governing mandate revision read (R-16), the policy asked for before recording and erasure and extraction needing the operator's authorization (R-07, R-08; R-21 applies only as that prohibition, Work having no extraction pipeline), and convergence evidence recorded with the evaluator and its independence (R-17). **Partly met:** derived views kept by small dated sourced items with an author and a stated uncertainty, but checked for freshness by comparing the newest record id, which lists `records/` (R-19); binding by root commit, with a fork or copy detected only when the binding lists `locators` (R-13; a binding without locators binds by root commit alone); create-only records with collisions reported (R-18; atomic acceptance and the difference between a record written and one the memory accepted rest on the memory repository); a bounded, stated start-up read (R-20; finding an open checkpoint reads every record header in the narrowest scope and the freshness check lists its `records/`, so those steps grow with the scope); a run with no mission, governed by the operator's confirmed prompt alone and recorded as `mandate: none` (R-09's missing-mandate check is not met for that run), and the checkpoint before the first change, which the memory has accepted then only if the memory-wide mission lets the agent commit it (R-09, R-11, R-18). **Not met:** independent evidence capture (R-04, which needs a separate component) and with it the evidence half of R-03, since Work reads no evidence tier, and structural protection of records and mandates against the agent that writes the memory (R-05, R-06): the memory repository must provide it, and the suite's optional `memory_check.py --history` detects an edited, deleted or renamed record after the fact without stopping a writer who can rewrite the repository. R-07 is met only once the memory's principal has set a policy; Work asks and does not set one. **Legacy mode** (an in-repository `.acm/`) does not meet R-05, R-11, R-12, R-13, R-16 or R-18, and has no path scopes (R-14, R-15). Untested: that a fresh agent following the skill behaves correctly against a real bound scope.

## This repository

The repository is named `work-skill`; its sole installable artifact is the `work` directory, whose basename matches the `name: work` frontmatter. Its own development memory is kept in the author's private memory repository (scope `work-skill`), not in this repository; the earlier in-repository `.acm/` remains in git history up to commit 105a1dc.

---

Author: [Nils Wendelboe Holmager](https://nilsholmager.com/) · [Project context and connected work](https://nilsholmager.com/research/work-skill/)
