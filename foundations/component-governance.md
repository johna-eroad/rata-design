---
title: Component governance
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/2684617150/Component+usage+and+design+system+update+process
---

# Component Governance

> Source of truth: [Component usage and design system update process (Confluence)](https://eroad.atlassian.net/wiki/spaces/UD/pages/2684617150/Component+usage+and+design+system+update+process)
> Last synced: 2026-05-19 (page version 10)
> Web reference implementation: `@eroad/ui-library` in `eroad/myeroad-portal`,
> `packages/ui-library/`. Component reference: [Storybook](https://storybook.eroad.io/).
> App (Android and iOS, KMP/Material 3) equivalent process: not yet documented
> (see [Platform status](#platform-status)).

## Context

Rātā's component layer is a mix of custom Rātā components and baseline
library components (AntD on web; Material 3 on app; see
[`platforms/README.md`](../platforms/README.md)). Every component, custom or baseline,
must be considered and designed within the baseline system, not as an
independent one-off. This document governs how a component need is
resolved and how changes enter the design system, so design and
implementation work (human or agent-generated) stays consistent and
doesn't silently fork the system.

This repository does **not** hold component code or API documentation;
that lives in [Storybook](https://storybook.eroad.io/) (web) and the
app equivalent. This document governs *process*: where to look, when a
change is allowed, and what's required to get one approved.

## Requirements

### CG-1: Resolution order
Before creating or modifying any component, resolve the need in this order
and stop at the first match:

1. MUST check Storybook (web: `storybook.eroad.io`) for an existing component and its available properties.
2. If not available in Storybook, MUST check the baseline library (web: [Ant Design](https://ant.design/components/overview)) for a component or property that meets the requirement.
3. If neither has a solution, MUST raise a new component request ([CG-3](#cg-3-request-types)). Do not build an ad hoc, undocumented component to work around the gap.
### CG-2: No baseline library modification
- MUST NOT modify a baseline library component (web: AntD) directly, due to complexity and ongoing maintenance cost.
- Any change to a baseline component's behaviour or appearance that cannot be achieved via its existing props MUST instead be built and treated as a new custom component ([CG-3](#cg-3-request-types), "New custom component").
### CG-3: Request types
Two request types exist, with different requirements:

**Small component change** (a baseline library prop/behaviour addition, or
a new property brought into the Rātā system):
- MUST have the use case approved at a Design Review Session (DRS) before a ticket is raised.
- MUST be tracked as a Foundation (FED) ticket containing: component and prop details, user justification, and usage guidance.
- Exception: a prop addition needed purely for internal development with no UI impact (e.g. an `onClick` handler with no visual change) only requires informing the design/UX team; it does not require DRS review or a full FED ticket.
**New custom component** (a component or interaction pattern that does not
exist in the baseline library):
- MUST have the use case approved at a Design Review Session (DRS) before a ticket is raised.
- MUST be tracked as a FED ticket containing: a detailed design specification including interaction design, user justification backed by user validation (e.g. a usability test), cost justification, and usage guidance.
### CG-4: Ownership
- A component change MUST be delivered as part of the initiative/product work that needs it, tied to that initiative's normal development process.
- The Foundation team supports new custom component requests but does not own or deliver every change on the requesting team's behalf.
### CG-5: Verification
- A new or changed component MUST meet the accessibility requirements in [`accessibility-standards.md`](./accessibility-standards.md) and use tokens per [`tokens/values-interim.md`](./tokens/values-interim.md) before it is considered complete.
- A new or changed component SHOULD be added to Storybook (web) or the app equivalent as part of the same piece of work, so CG-1's resolution order stays accurate for the next person or agent.
### CG-6: AI-generated prototypes are not approved changes
- A prototype or mockup produced by an AI design tool (e.g. Claude Design) using this repository as reference MUST be treated as exploratory input only, not an approved design system change.
- Such a tool MUST NOT commit changes to this repository or to any shared component repository (e.g. `@eroad/ui-library`). This repository stays read-only source of truth for anything that consumes it.
- Any new or changed component surfaced in an AI-generated prototype MUST still go through the resolution order ([CG-1](#cg-1-resolution-order)) and, where it applies, the request process ([CG-3](#cg-3-request-types)) before it is implemented.
## Platform status

- **Web:** fully documented above. Process and terminology (AntD, Storybook, FED, DRS) are drawn directly from the current process.
- **App (Android and iOS):** an equivalent process (baseline: Material 3) is assumed to exist per [`platforms/README.md`](../platforms/README.md), but has not yet been confirmed or ported into this document. Treat CG-1 through CG-4 as **web-specific until confirmed**. Do not assume the FED/DRS process or "never modify the baseline library" rule applies unchanged to app without checking.
## Further reading (non-normative)

- [EROAD Design system (Confluence)](https://eroad.atlassian.net/wiki/spaces/UD/pages/2152104185/EROAD+Design+system)
- [Storybook](https://storybook.eroad.io/)
- [Ant Design components](https://ant.design/components/overview)
- [Foundation (FED) Jira project](https://eroad.atlassian.net/jira/software/c/projects/FED/list)
