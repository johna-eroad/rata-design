---
title: "0006: Shared steps and organisation configuration in flow areas"
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# 0006: Shared steps and organisation configuration in flow areas

**Date:** 2026-10-01
**Owner:** TBC
**Supersedes:** None (extends [0005](0005-flows-by-area-and-surfaces.md))

## Context
Scaffolding the web identity area showed two gaps in [decision 0005](0005-flows-by-area-and-surfaces.md). First, an MFA challenge is not something a user sets out to do: it is part of signing in, and possibly other flows. Second, MFA is off by default, and a Client Admin chooses whether it is optional or mandatory (with an optional grace period) for their organisation. That choice changes how sign-in and other flows behave for everyone else.

## Decision
- A flow is something the user sets out to do. Parts of a flow they don't choose are steps. A step used by more than one flow gets its own file in the area's `steps/` folder; otherwise it stays inline.
- Organisation settings that change flows are described once, in the area's `configuration.md`, with a table of their effect on each flow. Flows link to it rather than describing the setting.
- The flow where an admin changes a setting lives in the area matching the IA (for MFA, `organisation-access/`, for Admin > My Organisation > Access) and links back to the configuration file.

## Alternatives considered
- One flow file per scenario, including MFA. Rejected because MFA steps and policy rules would be repeated in several flows.
- Describing the policy inside each flow's variants. Rejected because the rules would drift apart between flows.

## Consequences
- Agents read `configuration.md` first, then the flow, so behaviour stays consistent with organisation settings.
- Where these settings affect app users is still unknown, and will be decided when app identity is worked on.
