---
title: Heuristic evaluation report template
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Heuristic Evaluation: Issue and Report Templates

Reference templates for the `heuristic-evaluation` skill. Load this file
only when you're ready to log findings or write up a report.

## Issue template

Use one of these per finding.

```markdown
## Issue: [Short title]

**Surface:** [Web / Android / iOS: name the screen or flow]
**Location:** [Specific screen, component, or step]
**Heuristic:** #[N]: [Heuristic name]
**Severity:** [0–4]

### Description
[What is the problem?]

### Evidence
[Screenshot, screen description, or reproduction steps]

### EROAD-context impact
[Who is affected (driver / fleet manager / compliance officer / dispatcher),
and what is the operational consequence? Reference the design principle(s)
this violates, e.g. "Design for Trust" or "Design for Action".]

### Recommendation
[Suggested fix. If it implies a new/changed component, note that it must go
through component-governance.md before being designed or built.]
```

## Report skeleton

```markdown
# Heuristic Evaluation Report: [Product/Feature]

## Executive summary

**Surface(s):** [Web / Android / iOS]
**Evaluation date:** [Date]
**Evaluator(s):** [Name(s)]
**Total issues found:** [N]

### Issues by severity
| Severity | Count |
|----------|-------|
| Catastrophic (4) | [N] |
| Major (3) | [N] |
| Minor (2) | [N] |
| Cosmetic (1) | [N] |

### Issues by heuristic
| Heuristic | Count |
|-----------|-------|
| #1 Visibility of system status | [N] |
| ... | ... |

---

## Detailed findings

[One issue block per finding, grouped by severity (highest first), using
the issue template above.]

---

## Recommendations

### Immediate action (severity 4)
1. [Action item]

### High priority (severity 3)
1. [Action item]

### Medium/low priority (severity 1–2)
1. [Action item]

---

## Methodology

This evaluation applied Nielsen's 10 usability heuristics, read through
EROAD's B2B design principles (see `foundations/principles.md`),
across [N] pass(es) by [N] evaluator(s).
```
