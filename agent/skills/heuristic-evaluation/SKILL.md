---
name: heuristic-evaluation
description: Conduct a heuristic evaluation of a Rātā/EROAD screen, flow, or prototype using Nielsen's 10 usability heuristics, read through EROAD's B2B field-operations context. Use when asked to critique, review, or find usability issues in a design, assign severity ratings, run a cognitive walkthrough, or produce a heuristic evaluation report for web (React/AntD), Android, or iOS (KMP/Material 3) surfaces.
allowed-tools: Read, Glob, Grep, Task
---

# Heuristic Evaluation (Rātā)

Expert usability review of Rātā product surfaces against Nielsen's 10
heuristics, applied through EROAD's B2B design context, not generic
consumer-app conventions.

## Before evaluating anything

Read these two files in full; they are the source of truth this skill is
built on, and they override anything below if the two ever disagree:

- [`foundations/principles.md`](../../../foundations/principles.md):
  the B2B context (professional operators, time pressure, shared accounts,
  operational consequences) and EROAD's six principles. This is the lens
  every heuristic finding must be read through. It also names Nielsen's 10 as
  our reference framework, so this skill is additive to it, not a
  replacement.
- [`platforms/README.md`](../../../platforms/README.md): confirms
  which surfaces exist (web/React/AntD, Android, iOS; the latter two share a
  KMP/Material 3 implementation) and what's common vs. platform-specific.
  Identify which surface(s) are in scope before you start.

Do not treat accessibility as one heuristic among many. Accessibility issues
(contrast, keyboard/screen-reader operability, touch targets, etc.) have
their own normative spec and their own skill. Use `accessibility-review`
and log them against [`foundations/accessibility-standards.md`](../../../foundations/accessibility-standards.md)
instead of folding them into a heuristic finding.

## The B2B lens

EROAD's users are drivers, fleet managers, compliance officers, and
dispatchers doing paid work under time pressure, often in the field, on
shared accounts. When applying any heuristic below, weigh findings against:

- **Efficiency and clarity outrank delight.** A heuristic violation that
  costs an extra tap is worse here than in a consumer app; a missing
  "delight" moment is not a finding.
- **Consistency and predictability outrank novelty.** Prefer flagging
  inconsistency with existing Rātā patterns over proposing a new pattern.
- **Errors have real operational/financial consequences.** Weight severity
  up for anything touching compliance, HOS, safety, or billing data.
- **Shared accounts and roles.** Consider whether the affected user can even
  see or fix the issue given their role/permissions, not just "the user".

## Nielsen's 10 heuristics: EROAD field-context checklist

| # | Heuristic | Watch for in a B2B/field context | EROAD-relevant example |
|---|-----------|-----------------------------------|-------------------------|
| 1 | Visibility of system status | Long-running or offline-sensitive operations (sync, route calculation, ELD certification) with no feedback | "Syncing 3 of 12 trip logs…" vs. a sync that runs silently and may have failed |
| 2 | Match between system and the real world | Fleet/compliance jargon vs. plain operator language | "Depot", "duty status", "odometer", not "node", "payload", "entity" |
| 3 | User control and freedom | Irreversible actions on compliance/safety records | Undo after marking a defect resolved, vs. permanent deletion of a duty-status record with no confirmation |
| 4 | Consistency and standards | Same action in a different place across compliance vs. dispatch screens | "Flag for review" always in the same toolbar position system-wide |
| 5 | Error prevention | Free-text entry where a constrained input would prevent bad data | Numeric, range-checked odometer entry vs. free-text that silently accepts nonsense |
| 6 | Recognition rather than recall | Operators switching between vehicles/drivers/routes all shift | "Recent vehicles" list vs. re-typing a VIN or driver ID every time |
| 7 | Flexibility and efficiency of use | Repetitive tasks at volume (approvals, dispatch) | Bulk-approve timesheets vs. approving one at a time |
| 8 | Aesthetic and minimalist design | Dashboards with many assets/rows | Surface outlier vehicles first, not an undifferentiated list of 500 |
| 9 | Help users recognise, diagnose, recover from errors | Data-validation errors on compliance-relevant fields | "Odometer reading is lower than the last recorded value (142,300 km). Enter a corrected value." vs. "Invalid input" |
| 10 | Help and documentation | In-context help vs. separate manuals | Inline tooltip explaining an HOS rule outcome, not a link to a PDF |

## Severity rating

Use Nielsen's standard 0–4 scale. Base severity on frequency × impact ×
whether the user can recover easily. Per the B2B lens above, weight up
anything touching compliance, safety, or billing data.

| Rating | Severity | Action |
|--------|----------|--------|
| 0 | Not a problem | None needed |
| 1 | Cosmetic | Fix if time allows |
| 2 | Minor | Low priority |
| 3 | Major | Important to fix |
| 4 | Catastrophic | Must fix before release |

## Workflow

1. **Scope**: identify the surface(s) in scope (web/Android/iOS) and the
   flow(s) or screen(s) being evaluated.
2. **Two passes**: an unstructured first pass (initial impressions), then a
   systematic second pass against each of the 10 heuristics above.
3. **Log each issue** using the template in
   [`references/report-template.md`](./references/report-template.md):
   location, heuristic, severity, evidence, EROAD-context impact,
   recommendation.
4. **Consolidate**: merge duplicate findings, group by heuristic or
   location, prioritise by severity.
5. **Report**: use the report skeleton in
   [`references/report-template.md`](./references/report-template.md).

For a learnability-focused alternative (does a new user complete a specific
task successfully?), run a cognitive walkthrough instead. See
[`references/cognitive-walkthrough.md`](./references/cognitive-walkthrough.md).

## Guardrails

- **Don't recommend new or changed components ad hoc.** If a finding implies
  a new component, pattern, or a change to a baseline (AntD/Material 3)
  component's behaviour, say so in the recommendation but route it through
  [`foundations/component-governance.md`](../../../foundations/component-governance.md)
  (check Storybook → baseline library → raise a request) rather than
  designing it inline.
- **This repository is read-only source of truth.** A heuristic evaluation
  produces findings and recommendations, not committed design or code
  changes to this repo or to `ui-library`.
- **Don't assume "web" means "all platforms".** State findings as
  outcome-level where they apply everywhere, and call out explicitly if a
  finding is web-only or mobile-only.

## Related skills

- `accessibility-review`: for WCAG 2.1 AA conformance findings; use this
  instead of Nielsen heuristic #10/"extended heuristics" for anything
  accessibility-related.
