---
name: accessibility-review
description: Audit a Rātā/EROAD screen, flow, or component against the WCAG 2.1 AA requirements in foundations/accessibility-standards.md (A11Y-1 through A11Y-10), across web (React/AntD), Android, and iOS (KMP/Material 3). Use when asked to check, review, verify, or improve accessibility, contrast, keyboard support, screen-reader support, touch targets, or WCAG compliance for a Rātā surface.
allowed-tools: Read, Glob, Grep, Task
---

# Accessibility Review (Rātā)

Structured audit against Rātā's normative accessibility spec, not a
generic accessibility checklist. WCAG 2.1 AA is both a legal obligation and
a usability requirement here: EROAD's B2B users work in the field, under
time pressure, on shared devices, and cannot be assumed to have full
vision, hearing, motor function, or connectivity.

## Before reviewing anything

Read these in full; they are the normative source of truth this skill
operationalises, and they override anything below if the two ever
disagree:

- [`foundations/accessibility-standards.md`](../../../foundations/accessibility-standards.md):
  the actual requirements (A11Y-1 to A11Y-10), each stated as an
  outcome first, then Web/Android/iOS mechanism where it differs. Every
  **MUST** is mandatory and verifiable; every **SHOULD** needs a
  justification to skip.
- [`platforms/README.md`](../../../platforms/README.md):
  confirms which surface(s) are in scope (web/React/AntD vs. Android/iOS on
  shared KMP/Material 3) and what's common vs. platform-specific.

Do not substitute this skill's summary table below for the full spec. It's
a navigation aid, not a replacement. Quote the specific A11Y-N requirement
(and WCAG success criterion, where named) in every finding.

## Workflow

1. **Scope**: identify which surface(s) (Web / Android / iOS) and which
   screen(s)/flow(s)/component(s) are in review.
2. **Walk the checklist**: go through A11Y-1 → A11Y-10 in
   `accessibility-standards.md` for each surface in scope. For each requirement,
   check the outcome first, then the platform-specific mechanism that
   applies to your surface(s):

   | ID | Outcome | Typical failure mode |
   |----|---------|------------------------|
   | A11Y-1 | Semantic structure, accessible names | `<div>`/`<span>` used as buttons; missing labels |
   | A11Y-2 | Text alternatives | Missing alt text; decorative images not marked; no captions/transcripts |
   | A11Y-3 | Colour and contrast | Text/icon contrast below 4.5:1 / 3:1; colour as the only signal |
   | A11Y-4 | Text resizing to 200% | Fixed px text sizing; layout breaks on zoom |
   | A11Y-5 | Layout, responsiveness, input | Touch targets under 44×44 (48×48dp Android); keyboard traps; no visible focus indicator |
   | A11Y-6 | Content and language | Unexplained jargon; internal terminology exposed to users |
   | A11Y-7 | Forms and validation | Placeholder-only labels; errors indicated by colour alone |
   | A11Y-8 | Navigation | No skip-to-content link (web); inconsistent nav patterns |
   | A11Y-9 | Modals and dialogs | Focus not moved into/out of modal; no keyboard-accessible dismiss |
   | A11Y-10 | Verification | Not tested with automated tooling + manual AT check before release |

3. **Verify, don't just inspect**: where possible, actually test rather
   than eyeball:

   | Surface | Automated | Manual assistive technology |
   |---------|-----------|-------------------------------|
   | Web | axe / Accessibility Insights / Lighthouse | Keyboard-only pass + NVDA/JAWS/VoiceOver |
   | Android | Accessibility Scanner | TalkBack |
   | iOS | Xcode Accessibility Inspector | VoiceOver |

4. **Log each issue** using the template in
   [`references/report-template.md`](./references/report-template.md).
5. **Consolidate and prioritise**: every MUST-level failure is at least
   Serious; anything that fully blocks an assistive-technology user from
   completing a task is Critical.

## Severity / impact scale

Distinct from the heuristic-evaluation severity scale: this one is about
conformance and who is blocked, not general usability:

| Impact | Definition | Action |
|--------|------------|--------|
| **Critical** | Fails a MUST; blocks an assistive-technology user from completing a task with no workaround | Fix before release / blocker |
| **Serious** | Fails a MUST; degrades the experience significantly or has an awkward workaround | High priority |
| **Moderate** | Fails a SHOULD, or a MUST with a reasonable workaround | Medium priority |
| **Minor** | Cosmetic or edge-case conformance gap | Low priority |

## Guardrails

- **Cite the requirement, not just "not accessible".** Every finding must
  reference the specific A11Y-N id (and WCAG success criterion where
  `accessibility-standards.md` names one), so it's traceable and verifiable.
- **Don't invent new components to fix a finding.** If remediation implies
  a new/changed component or a change to a baseline (AntD/Material 3)
  component's behaviour, route it through
  [`foundations/component-governance.md`](../../../foundations/component-governance.md)
  (CG-1 resolution order) rather than designing a fix inline. Any resulting
  component change must still meet `accessibility-standards.md` per CG-5.
- **Use design tokens, don't hand-pick colours.** Contrast fixes should be
  checked against [`foundations/tokens/values-interim.md`](../../../foundations/tokens/values-interim.md)
  and its palette-extension process if the existing palette can't meet the
  ratio, not a one-off custom colour.
- **Don't conflate platforms.** State the outcome once; give Web, Android,
  and iOS mechanisms separately when they differ, per `platforms/README.md`. A
  fix verified on web does not imply the mobile equivalent is fixed.
- **This repository is read-only source of truth.** This skill produces
  findings and remediation guidance, not committed changes to this repo or
  to `ui-library`.

## Related skills

- `heuristic-evaluation`: for general usability findings. Accessibility
  findings belong here, not there.
