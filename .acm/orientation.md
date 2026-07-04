# orientation.md — auditonomy-skill (renamed 2026-07-04, was think-it-through-skill, originally pea-skills-lite)

_Last updated: 2026-07-04 (run: rate-the-skill-mini-orient, 6 entries since last update — overdue by 1)_

## Scorecard (baseline — 2026-07-04, run: formalize-10-metric-scoring)

**Read this as a plateau diagnostic, not a target.** Void the moment the destination or focus shifts (per SKILL.md step 2's plateau rule); the *delta* on the next rating is the signal, not the absolute numbers below.

| # | Measurement | Score /10 | Evidence | Bounded improvement suggestion |
|---|---|---|---|---|
| 1 | Mechanism integrity | 9 | 0 broken mechanisms across 24 trail entries; both renames and the frontmatter fix were identity/compliance-only. | Only the still-pending real independent code-repo test can move this to 10 — no new tooling; destination already deprioritizes mechanism-completeness vs. reasoning quality. |
| 2 | Reasoning-depth parity vs. full suite | 7 | Three concrete gaps closed 2026-07-04 (contradiction case, anti-anchoring questions, clean-trail suspicion check) by direct text comparison; never re-verified under real task pressure since. | Run the still-pending independent-target test; no new ceremony section needed. |
| 3 | Explanation-layer clarity (stranger-pickup) | 8 | `probe`, `record.py`, `freshness guard` glossed this run (were unglossed 4th time running). One prior cold-read's other 7 defects (§4, `.acm-root`, etc.) stayed closed since their own repair. | Next stranger cold-read should re-test whether these three new glosses actually land, not just that they exist. |
| 4 | Cost / tier calibration | 8 | Tiers actually vary across entries (Micro/Standard/Full genuinely different weights), not habitual Tier 3. | None owed structurally; the existing step-4 cost-drift check is the right mechanism — keep using it, don't add a new one. |
| 5 | Trail self-scheduling compliance | 6 | The every-5th mini-orient trigger was missed once (fired at entry 6, not 5), only because the operator asked for a rating. | Fold the entry-count check into step 3 (Trail-append time) rather than leaving it for step 4 to notice later — a wording change, not new tooling. |
| 6 | External validation coverage | 4 | Only non-self-referential use to date: `think-it-through` (this skill's prior name) on `c:/git/linkedin`, this same session — real but not yet read back into this file as verified fact. | Read `linkedin/.acm/audit-trail.md` directly before the next full Orient and fold it into a claim, instead of asserting it from memory. |
| 7 | Destination-boundary adherence | 9 | No installer, no Probe folding, lean files — all confirmed constraints, honored across every entry including this one's own suggestions column. | None needed — a maintenance bar; this scorecard's own suggestions were checked against it before being listed. |
| 8 | Identity stability (naming churn) | 6 | Two renames in two days (`pea-lite`\u2192`think-it-through`\u2192`auditonomy`); some version churn (2.2.0\u21922.5.0) came from identity, not substance. | None owed now \u2014 `auditonomy` is operator-confirmed, not up for a 3rd round; just weigh future rename requests against the opportunity cost of the still-larger untested-target item. |
| 9 | Self-audit honesty (anti-rationalization) | 8 | Blind spots disclosed every entry; the folder-move mishap was disclosed rather than smoothed over; the "named 4x, fixed 0x" pattern was surfaced rather than hidden. | Watch that disclosure itself doesn't become a substitute for fixing \u2014 metric 10 is the check on this. |
| 10 | Finding \u2192 fix conversion rate | 6 | The `probe`/`record.py`/`freshness-guard` gloss gap was named 4 times before being fixed this run (5th mention). Fixed, but slowly. | Going forward: a finding named twice without action should trigger an explicit fix-or-won't-fix decision, not a 3rd unchanged renaming. |

**Plateau average: 7.1/10.** Lowest two: external validation coverage (4) and trail self-scheduling compliance (6, tied with identity stability and finding\u2192fix rate) \u2014 both already named as the top candidate next moves below, not new information created by averaging.

## Current claims

1. **The mechanism layer remains zero-corrections across all 24 trail entries to date.** Neither of the two renames (`pea-lite`→`think-it-through`→`auditonomy`) nor the frontmatter-compliance fix broke or altered a mechanism — both renames were pure identity changes, disclosed as such in their own entries. The explanation-layer finding-class (claim below) remains the *only* defect class ever found.

2. **The explanation-layer finding-class is still open in the current file, not fixed.** `record.py`, `freshness guard`, and `probe` all still appear in `auditonomy/SKILL.md` (v2.4.0) unglossed — the same defect shape as the lens glosses, marker glosses, and the original cold-read's 7 defects. Every audit that has looked for this class has found a new instance of it; none has been the last. Named again this run, still not acted on — judged low-priority relative to reasoning-depth work each time, not forgotten.

3. **Reasoning-depth parity work (2026-07-04) closed three concrete, named gaps against the full suite** — an internal-contradiction case in step 1, two anti-anchoring questions in step 2's challenge, and a suspicious-clean-trail check in step 4 — found by direct side-by-side comparison against the current `pea/skills` suite text, not by internal audit. Comparison-against-source is now the more reliable finding method than self-audit alone, per that entry's own reflection.

4. **The real independent-target test is still the single most-repeated open item across the whole arc** (named in at least 4 separate entries' candidate next moves) — every prior application of this skill has been the skill auditing, renaming, or upgrading *itself*. **New datapoint, not yet folded into a claim:** this skill (as `think-it-through`) was used this session on an external target (`c:/git/linkedin`, a LinkedIn post revision) with a real falsifiable-hypothesis-per-round loop — the first genuine external-use evidence in the arc. That work lives in `linkedin`'s own `.acm/audit-trail.md`, not here; it should be read and folded into this claim on the next full Orient, not asserted from memory here.

5. **[New this run] The mini-orient's own every-5th-entry trigger was missed once.** It should have fired at entry 5 after this file's prior header (`## ... rename-pea-lite-to-think-it-through`, the 5th entry since 2026-07-03's cold-read-verification-and-defect-repair) and did not run until entry 6, triggered only by an operator's direct "rate my skill" ask rather than the mechanism firing on its own. This is a new finding-class, distinct from claim 2: a **process/schedule compliance gap**, not a text-explanation gap — the step is well-specified on paper but was not self-triggering in practice this session.

## What the next runs should test

- **Real code repo, structural stakes** — still the only fully untested surface for this skill's *own* file. Deferred across the whole arc.
- Whether the `linkedin` external-use datapoint (claim 4) actually demonstrates reasoning-depth parity when read closely, or just looks like it did from the outside — the next full Orient should read that repo's trail directly rather than take this run's characterization on faith.
- Whether naming the missed-trigger gap (claim 5) once is enough to prevent recurrence, or whether the trigger check itself needs to become part of some earlier, more mechanical step (e.g. counted at Trail-append time, not left to be noticed later).

## Active operational rules

- Before claiming the stranger-pickup bar is met, run a zero-context reader against the file. Author verification only covers mechanism-preservation.
- Before encoding an unconfirmed inference into a committed file, ask first if answerable in one turn (carried from previous orientation — still the operative bootstrap discipline).
- Scores shown to the operator are framed as plateau-relative diagnostics, disposable on destination-shift.
- **[New]** Don't assert a cross-repo claim (like claim 4's external-use datapoint) as settled from memory alone — read the source repo's own trail before folding it into a claim as fact.

