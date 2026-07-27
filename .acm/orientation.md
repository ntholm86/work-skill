# orientation.md - work-skill

## Work current orientation

**Last updated:** 2026-07-27 (`restore-pea-principles-in-destination-synthesis`, v3.14.1)

**Destination basis:** `Destination correction - 2026-07-27 (session synthesis omitted PEA principles and The One Question — restored)`

### Current rubric

| # | Destination-derived measurement | /10 | Current evidence |
| --- | --- | ---: | --- |
| 1 | Intent fidelity over literal compliance | 9 | Unchanged; the synthesis restates this without new mechanism. |
| 2 | Practical context continuity | 9 | Unchanged. |
| 3 | Temporal and provenance-separated memory | 9 | Unchanged. |
| 4 | Optional harness integration | 8 | Unchanged; no real `.acm/sessions/` evidence exists yet. |
| 5 | Assurance honesty | 9 | Unchanged. |
| 6 | Selective evidence cost | 9 | Unchanged. |
| 7 | Operator consent and privacy | 9 | Unchanged. |
| 8 | Route neutrality and standalone portability | 9 | Unchanged. |
| 9 | Improve-grade decision reasoning | 9 | Unchanged. |
| 10 | Observable Autonomy | 8 | Unchanged. |
| 11 | Todo sourced from Destination, not rubric-dominated | 7 | Unchanged; still instruction-complete, still unexercised. |
| 12 | First-contact Orient is optional, not mandatory | 7 | Unchanged; still instruction-complete, still unexercised. |
| 13 | Cross-model convergence awareness | 6 | New. The principle already existed in Destination and README; this run operationalized it into the mechanism (Orient trigger 3, step 6's actual Model-field check and switch-request behavior). Lower-rated than rows 11-12 because it depends on reading Trail history for a pattern across several entries — a more complex behavior to execute correctly than a single-run check, and entirely unexercised: no run has yet actually detected a same-model plateau and asked for a switch. |

**PEA-principle mapping, made explicit by this correction:** row 1 (Intent fidelity) measures Operator's Intent; row 10 (Observable Autonomy) measures Observable Autonomy directly; row 13 (Cross-model convergence) measures Convergence Is Silence. All three PEA principles were already being measured; only the prose synthesis had failed to name this lineage.

**Plateau: 8.5/10.** Rows 1-12 carry over unchanged from the prior Orient (this synthesis restates confirmed direction rather than opening new mechanism scope, except for convergence awareness). Row 13 is new and rated lower than 11/12 given its higher execution complexity. The average moves down slightly (8.7 -> 8.5) purely from adding one harder, less-proven row — not a regression in anything previously working.

### Rubric changes

Added row 13 because the operator's confirmed correction makes cross-model convergence an independently observable dimension distinct from anything already tracked: rows 11-12 are about a single run's own reasoning; row 13 is about the mechanism recognizing a *pattern across multiple runs and models* and acting on it (requesting a switch), which is a qualitatively different and harder capability. All other rows are retained without re-derivation: the session synthesis explicitly restates existing confirmed direction rather than introducing new scope for them.

### Current claims

1. **The prior synthesis closed a real legibility gap but was itself incomplete.** It consolidated three scattered Destination sections without a full top-to-bottom read, so it omitted the three PEA principles and The One Question. The correction restores that lineage explicitly; the rubric's substance never actually drifted (see PEA-principle mapping above), only the prose did.
2. **Cross-model convergence was a principle without a mechanism until this session.** Destination and README already said "independent models converging... is strong evidence," but `work/SKILL.md` had no behavior that read Trail's `Model:` field or acted on a same-model plateau. That gap is now closed at the instruction level.
3. **Three rubric rows (11, 12, 13) now share the same status: instruction-complete, behaviorally unverified.** This is becoming the dominant open theme of this repo's current state — the mechanism text has outpaced its own external exercise across three consecutive sessions of fixes.

### Highest-leverage todo

Unchanged from the prior Orient, and now reinforced by a third unexercised row rather than displaced: stop auditing `work/SKILL.md`'s own text. The next real leverage is external, behavioral verification — run Work against a genuine, unfamiliar target (ideally one that also produces enough Trail history to test the row-13 same-model-plateau detection directly), and confirm whether Orient's first-contact optionality, rubric-decoupled todo generation, and cross-model plateau detection all hold up outside self-editing. This item has no rubric row of its own by design: it is about the discovery method, not the target.

### Active operational rules

- Convergence toward a confirmed Destination is a cross-model claim. Before treating repeated bounded silence as convergence, check recent Trail entries' `Model:` field; if several consecutive silence declarations share one model, name the plateau explicitly and ask the operator to run the next evaluation under a different model.
- The highest-leverage todo is judged by a direct read of Destination and the target's current reality, never by which rubric row is lowest or lacks a candidate move. A todo item with no matching measurement is normal, not a gap.
- Rating a measurement is diagnostic only, for the operator's legibility; it never itself mandates a corresponding candidate move, and an unobservable axis is not an automatic license to invent one.
- First-contact Orient is optional and default-recommended, not mandatory; a confirmed Destination change still voids stale rubric/ratings/todo until a fresh Orient replaces them — these are two distinct rules, never conflate them for symmetry.
- Judge success against the operator's actual purpose, provenance needs, and consequences; literal prompt completion is insufficient when it defeats that purpose.
- Describe context preservation at the workflow level: externalize, reload, detect drift, and recover. Never imply perfect access to or control of hidden model cognition.
- Treat `.acm/sessions/` as optional, independently authored evidence memory. Query relevant sessions only on risk, contradiction, provenance, audit, or challenged self-report; never load all traffic by default.
- Preserve provenance boundaries: the operator authors Destination, Work authors semantic Trail, Orient replaces current state, and the proxy alone authors session JSONL. Preserve disagreements rather than silently reconciling them.
- Do not claim harness-backed assurance without verifying relevant session evidence for this run. Reasoning payloads may be absent, provider-specific, incomplete, or not causally faithful; streaming may release output before final persistence; the harness does not supply intent or authorization.
- Never silently install, update, start, or route traffic through the companion. Use `https://github.com/ntholm86/llm-harness-proxy`; check versions only on setup, explicit assurance need, incompatibility, or stale/unknown state, and ask for operator consent before changing the environment.
- Keep Destination authority with the operator; agent hunches remain sourced questions until confirmed.
- Credit Nils W. Holmager as Work's canonical author on current public and distributable surfaces; model identities are execution provenance.
- Read this top Work current-orientation block before Standard or Full reasoning; consult Trail history only on an explicit escalation trigger.
- For ordinary historical escalation, search relevant realization/reversal markers and read only needed context; reserve the full substantive marker inventory for an actual Orient.
- Keep Improve-grade decision operations constant while domain risk scales evidence and Trail tier scales durable narration.
- Preserve the enclosing mission across instrumental targets through both repository-local Trail records.

### Tested outside-rubric concern

A mechanical Model-field-scanning behavior could become its own quiet numeric constraint (e.g., "always check the last N entries") if implemented carelessly — exactly the bare-cardinal-number pattern fixed twice already in this arc. The instruction as written avoids a hard count ("several consecutive... same model"), deliberately, to not reintroduce that class while operationalizing this one.

### Loop-effectiveness notes

This Orient responds to a correction, not a new mechanism: the prior session-synthesis claimed to restate "the current Destination" but was actually grounded in session working memory, not a full top-to-bottom read, and silently omitted the three PEA principles and The One Question. Notably, the *previous* Orient's own "Watch for" line had already named an adjacent risk ("a future run treating the session-synthesis section as license to skip reading the three earlier dated sections it summarizes") without catching the more basic problem: the synthesis itself was never grounded in a full read when it was written. The operator caught it directly; self-audit did not. Rows 1-13 are retained without re-derivation since the rubric's substance was never wrong, only the prose lineage was unstated.

Watch for: row 13 still being exercised for the first time when a real multi-entry, same-model silence pattern appears in any target's Trail; the three-row unexercised cluster (11, 12, 13) growing further before any external verification happens; and any future claim of "synthesizing" or "restating" Destination in full that is not preceded by an actual complete read of `destination.md` in that same turn.
