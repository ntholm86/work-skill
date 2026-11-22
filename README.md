# Work

Work is a single agent skill: the Principles of Earned Autonomy in a lightweight edition, and the skill that lets an agent use a shared Agent Context Memory (ACM) properly. It understands a target's purpose, changes what limits it most, validates the result, and records evidence another agent can challenge.

Name it in a prompt and it is designed to work without reading the ACM specification; that bar is stated, not yet demonstrated. The [Principles of Earned Autonomy skills suite](https://github.com/ntholm86/principles-of-earned-autonomy-skills-suite) is the full alternative; both work with the same shared ACM.

It is designed for delegated work without assuming unlimited authority. You define the mission and any actions that always require approval. The agent chooses the route only within that boundary, narrates its interpretation and decision, and records each substantive iteration in the shared ACM.

## Install

Copy this repository's `work` directory into the skills location for an agent host that supports Agent Skills:

```text
<repository-root>/work/SKILL.md  ->  <agent-skills>/work/SKILL.md
```

No package or runtime is required.

## Connect the shared ACM (once per machine)

The memory lives in its own repository, the shared ACM, never inside the repositories you work on. Clone it once and add its absolute path as one line in `~/.acm/memories` (Windows: `%USERPROFILE%\.acm\memories`; UTF-8, with or without a BOM).

The skill identifies a repository of work by its root commit and finds its scope in the shared ACM (`repositories/<id>/repository.json`), so renaming a clone keeps its memory and two same-named repositories are never mixed up. If a repository is not bound yet, the skill says so, offers to bind it with your confirmation, and records nothing in the meantime; it never creates a hidden local memory. Repositories that still carry an `.acm/` folder from earlier ACM versions keep working as legacy memory.

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

During the run you should see the interpretation, the selected limitation, a prediction, the action, focused validation, and a final result line. Durable detail is written to the repository's scope in the shared ACM as create-only records (`records/<time>-<slug>.md`); a record's content is never changed, so several people and agents can record at once without overwriting each other.

## Optional durable direction

For work that continues across sessions, add `mission.md` to the repository's scope in the shared ACM and describe the purpose, durable constraints, authority boundaries, and unresolved questions that genuinely change route selection, plus a `## Human gate` section saying where a human reviews the work and what the agent may do before that review and without it (a mandate that does not state its gate is incomplete). A `mission.md` at the shared ACM's root governs every repository in it.

Mission remains operator-owned. Work may identify a question that needs your decision, but it cannot answer or alter that direction on your behalf.

## What to inspect

After a run, the final result line tells you what changed and whether validation passed. The trail records in the shared ACM explain why the route was chosen, what evidence could falsify it, what was rejected, what was learned, and what remains uncertain.

## This repository

The repository is named `work-skill`; its sole installable artifact is the `work` directory, whose basename matches the `name: work` frontmatter. Its own development memory is kept in the author's private memory repository (scope `work-skill`), not in this repository; the earlier in-repository `.acm/` remains in git history up to commit 105a1dc.

---

Author: [Nils Wendelboe Holmager](https://nilsholmager.com/) · [Project context and connected work](https://nilsholmager.com/research/work-skill/)
