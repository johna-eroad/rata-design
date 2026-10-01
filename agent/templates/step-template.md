---
title: Step template
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Step template

A shared step is part of more than one flow that the user does not choose to do on its own (for example an MFA challenge). Create one in `platforms/<platform>/flows/<area>/steps/` only when more than one flow uses it. A step used by one flow stays inline in that flow. Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Step name]
platform: web | app
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# [Step name]

## Used by
Links to every flow that includes this step, and when each one triggers it.

## What happens
What the user sees and does in this step.

## States
Step-specific states. For shared states, link to the area's `states.md`.

## Hands back to the flow
What the calling flow receives (success, failure or cancelled) and what happens next in each case.

## Related files

````
