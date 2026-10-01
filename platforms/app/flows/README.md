---
title: App flows
platform: app
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# App flows

## What belongs here
Flows for app users. A flow is a task with a start and an outcome, such as signing in or recovering a password. Places users work in without a fixed start or end (dashboards, maps, lists, settings) are [surfaces](../surfaces/README.md), not flows.

## Structure

```
flows/
└── <area>/                  one folder per feature area, for example identity
    ├── README.md            scope, users and a flow map (uses the flow area template)
    ├── <flow>.md            one file per flow (uses the flow template)
    └── states.md            states shared by flows in the area (uses the area states template)
```

## Rules

- **Group by feature area.** Areas are finer-grained than [product segments](../../../domain/product-segments/README.md). Tag flows with their segment in frontmatter rather than using segments as folders.
- **Name files with descriptive slugs, not numbers.** The order users meet flows in lives in the area README's flow map.
- **Variants go inside a flow.** For example, signing in with an EROAD username or a company account is one flow with two variants, unless the variants share almost nothing.
- **Shared states are written once.** Errors, blocked access and similar states that several flows can reach go in the area's `states.md`, and flows link to them.
- **Link to design files, don't copy them.** Wireframes and prototypes stay in Figma or the prototype host, linked from each flow's `source` and Examples section.
- **Keep platforms separate.** If web users have a similar flow, it lives in `platforms/web/flows/`. Where the two platforms interact, link to the handoff in `cross-platform/handoffs/`.

## Owner
UX.

## Templates
- [`flow-area-template.md`](../../../agent/templates/flow-area-template.md) for each area's README
- [`flow-template.md`](../../../agent/templates/flow-template.md) for each flow
- [`area-states-template.md`](../../../agent/templates/area-states-template.md) for each area's `states.md`

## Related files
- [`platforms/app/surfaces/README.md`](../surfaces/README.md)
- [`platforms/app/states.md`](../states.md)
- [`platforms/app/README.md`](../README.md)
- [`foundations/glossary.md`](../../../foundations/glossary.md)
