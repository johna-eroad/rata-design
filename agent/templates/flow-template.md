---
title: Flow template
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Flow template

A flow is a task with a start and an outcome. Create one in `platforms/<platform>/flows/<area>/`, named with a descriptive slug (no numbers). Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Flow name]
platform: web | app
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: [Link to the Figma file or prototype, or TBC]
---

# [Flow name]

## Problem
What the user is trying to do, and what gets in their way today.

## User
Link to the user type.

## Trigger
What starts this flow.

## Entry points
Where the user can start this flow from: surfaces, other flows or notifications.

## Variants
Versions of this flow that differ by user, account or setting (for example, signing in with an EROAD username or a company account). Describe each difference here rather than creating a separate flow, unless the variants share almost nothing. If an organisation setting changes the flow, link to the area's `configuration.md` rather than describing the setting here.

## Steps
1. [Step]
2. [Step]

For a step shared with other flows, link to its file in `steps/`.

## States
States specific to this flow. For states shared across the area (such as errors or blocked access), link to the area's `states.md` rather than redefining them.

## Exits and next flows
Where the user ends up on success, failure or cancel, and which flows or surfaces come next.

## Success criteria


## Surfaces
Links to the surfaces this flow passes through or returns to.

## Related handoffs
Links to files in `cross-platform/handoffs/`.

## Examples
Links to Figma files and prototypes. Do not copy wireframes or prototype code into this repo.

## Related files

````
