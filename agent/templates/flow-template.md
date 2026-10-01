---
title: Flow template
platform: all
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Flow template

Create a canonical user journey in `platforms/<platform>/flows/`. Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Flow name]
platform: web | app
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# [Flow name]

## Trigger
What starts this flow.

## User
Link to the user type.

## Steps
1. [Step]
2. [Step]

## States
Loading, empty, error, partial, offline and success states for each step. Link to `../states.md`.

## Success criteria

## Related handoffs
Links to files in `cross-platform/handoffs/`.

## Related files

````
