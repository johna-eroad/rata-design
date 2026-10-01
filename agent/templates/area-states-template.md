---
title: Area states template
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Area states template

Shared states for a flow area: states that more than one flow in the area can lead to. Create it as `platforms/<platform>/flows/<area>/states.md`. Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Area name] states
platform: web | app
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# [Area name] states

## Purpose
The states shared by flows in this area. Flows link here rather than redefining these states.

## [State name]
- **When it happens:** [condition]
- **Reached from:** [links to flows]
- **What the user sees:** [message and available actions]
- **How to recover:** [next step, or who to contact]

Repeat this section for each shared state.

## Related files
- Link to the area README.
- Link to the platform's `states.md`.
````
