---
title: Accessibility review report template
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Accessibility Review: Issue and Report Templates

Reference templates for the `accessibility-review` skill. Load this file
only when you're ready to log findings or write up a report.

## Issue template

```markdown
## Issue: [Short title]

**Surface:** [Web / Android / iOS: name the screen, flow, or component]
**Location:** [Specific screen, component, or state]
**Requirement:** A11Y-[N]: [requirement outcome, from accessibility-standards.md]
**WCAG success criterion:** [e.g. 1.4.3 Contrast (Minimum), if applicable]
**Impact:** [Critical / Serious / Moderate / Minor]

### Description
[What is the problem? Which user(s)/assistive technology are affected?]

### Evidence
[Screenshot, contrast ratio measurement, screen-reader transcript, or
reproduction steps. Note the tool used, e.g. axe, Accessibility Scanner,
VoiceOver.]

### Who is blocked
[e.g. "Screen-reader users cannot determine the current duty status because
the status indicator relies on colour alone (fails A11Y-3)."]

### Recommendation
[Suggested fix, referencing design tokens where relevant. If it implies a
new/changed component, note that it must go through
component-governance.md before being designed or built.]
```

## Report skeleton

```markdown
# Accessibility Review Report: [Product/Feature]

## Executive summary

**Surface(s):** [Web / Android / iOS]
**Review date:** [Date]
**Reviewer(s):** [Name(s)]
**Conformance target:** WCAG 2.1 AA (per foundations/accessibility-standards.md)
**Total issues found:** [N]

### Issues by impact
| Impact | Count |
|--------|-------|
| Critical | [N] |
| Serious | [N] |
| Moderate | [N] |
| Minor | [N] |

### Issues by requirement
| Requirement | Count |
|--------------|-------|
| A11Y-1 Semantic structure | [N] |
| A11Y-2 Text alternatives | [N] |
| ... | ... |

---

## Detailed findings

[One issue block per finding, grouped by impact (Critical first), using
the issue template above.]

---

## Recommendations

### Fix before release (Critical)
1. [Action item]

### High priority (Serious)
1. [Action item]

### Medium/low priority (Moderate/Minor)
1. [Action item]

---

## Verification performed

[List the automated tools and manual assistive-technology passes actually
run, per surface (see the verification table in SKILL.md). Note any
requirement that could not be verified and why.]

## Methodology

This review was conducted against `foundations/accessibility-standards.md`
(A11Y-1 to A11Y-10, WCAG 2.1 AA) for [surface(s)], using [tools/AT used].
