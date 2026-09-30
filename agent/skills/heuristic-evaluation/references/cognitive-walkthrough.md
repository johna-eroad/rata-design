---
title: Cognitive walkthrough
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Cognitive Walkthrough (Rātā)

Reference for the `heuristic-evaluation` skill. Use a cognitive walkthrough
instead of (or alongside) the full heuristic pass when the question is
specifically about **learnability**: will a new or infrequent user complete
a specific task successfully, without training?

This matters for Rātā because field/depot users are often infrequent users
of a given screen (e.g. an occasional compliance workflow) under time
pressure, so learnability failures there have real operational cost.

## At each step of the task, ask

1. **Will the user try to achieve the right effect?**
   Is the goal obvious from where they are? Do they know what to do next?
2. **Will the user notice the correct action is available?**
   Is the control visible, not buried in a menu or overflow?
3. **Will the user associate the correct action with the effect they want?**
   Does the label match what an operator (not a developer) would expect?
4. **If they perform the action, will they see progress?**
   Is there feedback confirming it worked (see heuristic #1, visibility of
   system status)?

Any "No" or "Maybe" answer is a learnability barrier: log it the same way
as a heuristic finding, tagged with the relevant heuristic (usually #1, #2,
or #6).

## Template

```markdown
## Cognitive walkthrough: [Task name]

**Task:** [What the user is trying to accomplish]
**User profile:** [Role (driver / fleet manager / compliance officer / dispatcher) and experience level]
**Starting point:** [Where the task begins]

### Step 1: [Action]
| Question | Answer | Issue? |
|----------|--------|--------|
| Will user try to achieve the right effect? | [Y/N/Maybe] | [Issue if no] |
| Will user notice the correct action? | [Y/N/Maybe] | [Issue if no] |
| Will user associate action with effect? | [Y/N/Maybe] | [Issue if no] |
| Will user see progress? | [Y/N/Maybe] | [Issue if no] |

**Notes:** [Additional observations]

### Step 2: [Action]
[Continue pattern for each step in the task]

---

## Summary

**Success likelihood:** [High/Medium/Low]
**Key barriers:**
1. [Barrier]

**Recommendations:**
1. [Improvement]
```
