# learning.md — work-skill

_Derived view of the audit trail up to entry `trail-means-records-and-sealing-docs` (repository revision 4911fa3), read against the current destination (2026-11-21). Refreshed 2026-11-21 by the same agent that made the recent changes; not an independent evaluation. Replaces the 2026-08-17 synthesis._

## Current claims

- **Work's identity is settled and simpler than in August.** It is the single skill a person names to use the Principles of Earned Autonomy in lightweight form and a shared ACM; the PEA skills suite is the full alternative over the same memory. The August confusion between repository, skill and method names has not recurred. Falsifiable if any text again describes Work as part of the suite, or requires an `.acm/` in the target.
- **The memory contract moved out of the target.** The skill resolves a bound scope in a shared ACM by root commit through `~/.acm/memories`, reports unbound, ambiguous or unavailable memory instead of guessing, and treats an in-target `.acm/` as legacy (this repository's own trail is legacy by the author's choice). Falsifiable by a run in a fresh clone that fails to find, or silently invents, its memory.
- **The main design risk is now the skill's own size.** It grew from 10.7 to 13.8 KB in one day (binding, unbound handling, legacy memory, path and task scopes, monthly sealing), while its destination makes leanness a first-class constraint and reserves any reduction of memory or evidence capability to the author. Falsifiable if a shorter text keeps every guarantee and a fresh agent follows it correctly.
- **Evidence-lifecycle hardening is the same three-leg contract in a new form.** Checkpoint and completion are now two linked records (`completes:`) instead of an appended entry; open-checkpoint detection is unchanged. Still only structurally tested: no genuinely abandoned mid-run checkpoint has been recovered by a later run.
- **Every silence claim is still same-family, single-session.** Nothing about Work has been evaluated by a different model family. The independent review in progress today covers the ACM specification, not this skill.
- **No fresh agent has used the installed skill unassisted against a bound scope.** The quality bar "name the skill after cloning the shared ACM and it works" is untested; mechanics were checked by script only.

## What the next runs should test

1. A fresh agent, given only the installed Work skill and a clone of the shared ACM, runs on a real repository unaided, and a person watches where it first fails (setting up the registry is the likeliest step).
2. A different-family cold read of `work/SKILL.md` for undefined referents and for text that can be cut without losing a guarantee. The August arc showed only a cold read finds undefined-referent defects.
3. Recover a genuinely abandoned checkpoint, not a same-session simulation.
4. Shorten the skill and compare a fresh agent's behaviour before and after.

## Active operational rules

- Before another prose fix to `work/SKILL.md`, get cold-read behavioural evidence from a stateless agent; same-session review has a demonstrated blind spot for undefined referents.
- For every authorized Change, write the checkpoint record through the prediction before the first mutation and never rewrite it; record completion, correction or reversal as new records (legacy memory: append).
- At the start of a run, check for an open checkpoint and complete or explicitly supersede it.
- Treat any single-session silence in this trail as "same-family, single-session" and say so whenever it is repeated.
- Do not import the suite's heavier tooling (`record.py`, freshness guards, the `generated/` files) into this repository; the destination favours leanness.
- Do not treat harness captures as part of the skill: the independent-evidence integration is not built and was removed from the text.