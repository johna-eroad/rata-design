---
title: Configuration template
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Configuration template

Describes organisation settings that change how an area's flows behave (for example an MFA policy set by a Client Admin). Create it as `platforms/<platform>/flows/<area>/configuration.md`. Describe each setting once here; flows link to it rather than describing the setting themselves. Copy everything inside the block below into a new file, fill in each section, and delete any guidance text. See [`frontmatter-schema.md`](../frontmatter-schema.md) for the frontmatter fields.

````markdown
---
title: [Area name] configuration
platform: web | app
status: draft
owner-team: ux
segments: [segment-slug]
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# [Area name] configuration

## Purpose
The settings that change how this area's flows behave.

## Applies to
Which platform and users these settings affect, and anything not yet confirmed.

## [Setting name]
**Set by:** [user type, and where in the IA]

**Default:** [value]

**Options:**
- **[Option]:** [what it means]

### Effect on flows
A table with one row per option (and any user condition that matters) and one column per affected flow.

Repeat this section for each setting.

## Related files
Link to the flow where the setting is configured.
````
