# Improve

Improve is a single agent skill for understanding a target's purpose, changing what limits it most, validating the result, and preserving evidence that another agent can challenge.

It is designed for delegated work without assuming unlimited authority. You define the destination and any actions that always require approval. The agent chooses the route only within that boundary, narrates its interpretation and decision, and records each substantive iteration in the target repository's append-only `.acm/audit-trail.md`.

## Repository layout

The repository is named `work-skill`. Its sole installable Agent Skill artifact is the `improve` directory:

```text
work-skill/
  .acm/
    audit-trail.md
    destination.md
  .acm-root
  improve/
    SKILL.md
  README.md
```

Repository identity and installable skill identity are intentionally separate. The skill directory basename and the `name: improve` frontmatter agree, while repository-level ACM files remain at the repository root.

## Install

Copy this repository's `improve` directory into the skills location for an agent host that supports Agent Skills. The source and installed paths are:

```text
<repository-root>/improve/SKILL.md
<agent-skills>/improve/SKILL.md
```

No package, runtime, or project-specific Destination is required.

## First run

Ask the agent to use Improve on a real target and state the outcome you care about:

```text
Use Improve on this repository. Find and implement the highest-leverage change
toward making the command-line errors useful to a first-time user.
```

By default, the agent pauses twice: once to confirm what it understood before examination, and once before implementing its proposed change. You can delegate either routine pause explicitly for a run:

```text
Use Improve on this repository. I delegate routine intent confirmation and
implementation selection for this run. Do not publish, delete data, change the
project's destination, or reduce evidence without asking me.
```

During the run you should see the interpretation, the selected limitation, a prediction, the action, focused validation, and a final result line. Durable detail is appended to `.acm/audit-trail.md`; existing entries are never rewritten.

## Optional durable direction

For work that continues across sessions, add `.acm/destination.md` to the target repository and describe the purpose, durable constraints, authority boundaries, and unresolved questions that genuinely change route selection. Add an empty `.acm-root` at the highest directory whose memory may govern the target when parent context must not be crossed.

Destination remains operator-owned. Improve may identify a question that needs your decision, but it cannot answer or alter that direction on your behalf.

## What to inspect

After a run, the final result line tells you what changed and whether validation passed. The target's `.acm/audit-trail.md` explains why the route was chosen, what evidence could falsify it, what was rejected, what was learned, and what remains uncertain. That separation keeps routine use short without hiding autonomous reasoning.
