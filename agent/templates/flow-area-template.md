---
title: Flow area template
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Flow area template

A flow area groups the flows for one feature area (for example, identity). Create it as `platforms/<platform>/flows/<area>/README.md`. Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Area name] flows
platform: web | app
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# [Area name] flows

## Scope
What this area covers, and what it does not.

## Users
Links to the user types who go through these flows.

## Flow map
Each flow in the area, in the order users usually meet them, with one line on how it connects to the others. Order lives here, not in file names.

## Entry points
Where users enter this area from.

## Surfaces
Links to the surfaces these flows start from or return to.

## Shared states
Link to `states.md` in this folder.

## Related files

````
