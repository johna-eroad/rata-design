---
title: Surface template
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Surface template

A surface is a place users work in and return to, with no fixed start or end (for example a dashboard, map, list or settings page). Create one in `platforms/<platform>/surfaces/`, named with a descriptive slug. Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Surface name]
platform: web | app
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: [Link to the Figma file or prototype, or TBC]
---

# [Surface name]

## Purpose
What this surface is for, in one or two sentences.

## Users
Links to the user types who use it.

## Jobs supported
Links to files in `../jobs-to-be-done/`.

## Content
What the surface shows, in priority order. Describe meaning and priority, not layout.

## Actions
What users can do here, and where each action leads (a flow, another surface, or an in-place change).

## States
Empty, loading, partial, stale and error states. Link to `../states.md` for platform-wide rules.

## Entry points
How users arrive here.

## Flows started here
Links to flows that start from this surface.

## Examples
Links to Figma files and prototypes.

## Related files

````
