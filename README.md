# Work

Work is a single agent skill: the Principles of Earned Autonomy in a lightweight edition, and the skill that lets an agent use a shared Agent Context Memory (ACM) properly. It understands a target's purpose, changes what limits it most, validates the result, and records evidence another agent can challenge.

Name it in a prompt and it works; you do not need to read the ACM specification. The [Principles of Earned Autonomy skills suite](https://github.com/ntholm86/principles-of-earned-autonomy-skills-suite) is the full alternative; both work with the same shared ACM.

It is designed for delegated work without assuming unlimited authority. You define the destination and any actions that always require approval. The agent chooses the route only within that boundary, narrates its interpretation and decision, and records each substantive iteration in the shared ACM.

## Install

Copy this repository's `work` directory into the skills location for an agent host that supports Agent Skills:

```text
<repository-root>/work/SKILL.md  ->  <agent-skills>/work/SKILL.md
```

No package or runtime is required.

## Connect the shared ACM (once per machine)

The memory lives in its own repository, the shared ACM, never inside the repositories you work on. Clone it once and add its absolute path as one line in `~/.acm/memories` (Windows: `%USERPROFILE%\.acm\memories`).

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
project's destination, or reduce evidence without asking me.
```

During the run you should see the interpretation, the selected limitation, a prediction, the action, focused validation, and a final result line. Durable detail is written to the repository's scope in the shared ACM as create-only records (`trail/<time>-<slug>.md`); accepted records are never rewritten, so several people and agents can record at once without overwriting each other.

## Optional durable direction

For work that continues across sessions, add `destination.md` to the repository's scope in the shared ACM and describe the purpose, durable constraints, authority boundaries, and unresolved questions that genuinely change route selection. A `destination.md` at the shared ACM's root governs every repository in it.

Destination remains operator-owned. Work may identify a question that needs your decision, but it cannot answer or alter that direction on your behalf.

## What to inspect

After a run, the final result line tells you what changed and whether validation passed. The trail records in the shared ACM explain why the route was chosen, what evidence could falsify it, what was rejected, what was learned, and what remains uncertain.

## This repository

The repository is named `work-skill`; its sole installable artifact is the `work` directory, whose basename matches the `name: work` frontmatter. Its own development memory is kept public in `.acm/` as research evidence, in the legacy in-repository form.
## Optional independent evidence

The Trail is an agent-authored semantic record. An independent capture mechanism can add a separate evidence tier that the agent cannot author or silently reconcile away. When the two disagree, captured evidence governs only what its observer actually recorded; the disagreement remains visible.

[llm-harness-proxy](https://github.com/ntholm86/llm-harness-proxy) is one optional companion. It writes tamper-evident records of LLM-layer traffic before releasing buffered responses. It can attest what the model received and emitted, including tool calls exposed by the provider, but it does not by itself prove that an executor ran those calls or that the repository reached a claimed final state. Its current default storage is `.harness/sessions/`; target-local `.acm/sessions/` discovery and Trail correlation remain integration work rather than a capability claimed by this skill.

Work remains fully usable without a harness. It never installs, starts, updates, or routes traffic through one without operator consent, and it reads captured sessions selectively rather than treating surveillance cost as a default.

---

Author: [Nils Wendelboe Holmager](https://nilsholmager.com/) · [Project context and connected work](https://nilsholmager.com/research/work-skill/)
