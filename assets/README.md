---
title: Visual reference assets
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Visual reference assets

Source visual material for the Rātā design system. These assets exist so
that AI design tools (e.g. Claude Design) and human contributors can
extract accurate colour, typography, iconography, and layout patterns
directly from real product surfaces, rather than relying on text
descriptions alone.

This directory holds **reference images**, not production assets. It is
not a code or build project. Do not add SVG/icon libraries intended for
import into an application; those belong in the relevant component
library (e.g. `ui-library`).

## Structure

- `logo/`: Rātā / EROAD brand marks (primary lockup, icon-only mark,
  light/dark variants)
- `screenshots/`: real, representative product screens (web and mobile)
  that show components and patterns in context
- `icons/`: representative samples from the icon set in use, to
  illustrate style (stroke weight, corner radius, grid) rather than a
  full icon export

## Conventions

- File names should be descriptive and kebab-case, e.g.
  `web-dashboard-light.png`, `logo-primary-lockup.svg`,
  `icon-set-sample.png`.
- Prefer PNG/SVG. Keep files reasonably sized (compress screenshots;
  this is a documentation repo, not an asset pipeline).
- Each asset should be referenced from a specification (see
  [`foundations/visual-references.md`](../foundations/visual-references.md))
  that explains what it shows and why it's included. Don't add assets
  without a corresponding entry, because an uncatalogued image has no
  declarative value for agentic consumption.
