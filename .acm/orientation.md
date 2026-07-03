# orientation.md — pea-skills-lite

_Last updated: 2026-07-03 (run: orient-was-bootstrap-too-fast; brief fold-in note added after first external test, same day)_

## Current claims

1. **The core mechanism design has held up; the framing/scope layer hasn't.** Across all 6 trail entries, the actual mechanism — fused-intent step, three-tier trail (Micro/Standard/Full), mini-orient-every-5th-entry, mini-destination-bootstrap — has needed zero corrections. Every correction so far (Probe exclusion, installer permanence, daily-use scope, audience) was about the *destination/framing* the agent wrote around that mechanism, not the mechanism itself. The operator's original mandate (5 enumerated verbatim requirements) was specific enough that fast core construction was appropriate; the framing layer was not equally specified, and was filled by agent inference instead of being asked about first.

2. **Yes — the bootstrap ran faster than its own confirmation loop, in a specific, falsifiable way: confirmation-seeking lagged behind artifact-construction.** The agent formed sourced inferences correctly (labeled `[Inference, unconfirmed]`), but then built the full `destination.md`, `pea-lite/SKILL.md`, and `README.md` around those unconfirmed inferences in the same pass, and committed them — rather than pausing to ask the Probe/installer/scope/audience questions *before* writing files that encoded assumed answers. Destination's own "when to invoke" guidance names exactly this situation ("a long autonomous run is about to start... the destination is the input that determines whether the run will produce useful work or precisely-executed wrong work") as a moment to run the full conversational Destination process *first*. The agent instead folded a condensed, inference-based version into the bootstrap itself and only ran the full process retroactively, after being explicitly told to. This is the concrete shape of "too fast": not reckless code, but front-loaded construction and back-loaded confirmation.

3. **The trail shows genuine self-correction, not post-hoc rationalization — which is separate from, and does not excuse, claim 2.** Entry 5 explicitly reverses entry 4's "dropped" resolution on the workspace-listing question once the operator's actual answer came back, and names the reversal as a correction to a named prior `[!REALIZATION]` rather than quietly absorbing it. A trail this young showing an honest self-correction is a good sign for trail integrity — but it is evidence *of* claim 2 (something had to be corrected) as much as it is evidence of good trail hygiene.

4. **Partially resolved.** `pea-lite` has now run once on a real external target (`c:\git\linkedin`, 2026-07-03): fresh mini-Destination bootstrap, one confirmed inference before acting (not after), a genuine silence outcome on the editorial-review portion, and — notably — the run caught and disclosed an anomaly (`TRAIL/.gitkeep` unexpectedly missing, cause unconfirmed) rather than absorbing it silently. That's a good first data point specifically against claim 2's finding (ask-before-building held this time). But it is one run, on a two-file markdown repo with no code and no structural complexity — it does not yet test the depth-tier judgment call under real pressure (competing plausible interpretations, higher stakes, larger surface area). The claim is downgraded from "completely unvalidated" to "validated once, on the easiest possible case."

## What the next runs should test

- ~~Run `pea-lite` on an actual, unrelated target repo.~~ **Done 2026-07-03** (`linkedin/`) — see claim 4. Superseded by a sharper version: run it on a real *code* repo with actual structural stakes, not another small markdown-only target, to test the depth-tier call under real pressure.
- When a genuinely ambiguous scope question comes up for this repo again, ask before writing it into a committed file — not after. This is the direct operational fix for claim 2. (First external run followed this correctly — one data point, not a closed loop.)

## Active operational rules

- **Before encoding an unconfirmed inference into a file that will be committed, ask first if the question is answerable in one turn.** Labeling an inference `[Inference, unconfirmed]` is not sufficient discipline on its own if the surrounding file is written as though the answer is already known — the label and the file's actual content drifted apart in the first bootstrap.
- **Do not restate "run pea-lite on a real target repo" as a candidate next move a fourth time without either doing it or explaining why it keeps being deferred.** Repetition without action or explanation is itself a finding-class worth naming, not just re-listing.

## Loop-effectiveness notes

Triggered by direct operator question ("Did you start making the pea-lite skill too fast?").

- **`[!REALIZATION]`** Yes, specifically as described in claim 2: the agent built committed artifacts around unconfirmed inferences instead of asking before constructing them. The mandate's core (the mechanism) was well-specified enough that fast construction of *that* was correct; the surrounding destination narrative was not equally well-specified and should have been confirmed before, not after, being written down as if settled.
- **What this loop would structurally miss:** anything where the operator's signal is genuinely thin and the agent has no strong mandate to lean on — the same fast-construction habit applied to a less-specified request would produce more than cosmetic corrections. This repo got lucky in the sense that the core mandate was unusually explicit; that should not be read as validation of the pattern itself.
- **Silence bound:** not claiming convergence or readiness here — this is a critique, not a silence declaration, so no bar-naming is required by 5a.

