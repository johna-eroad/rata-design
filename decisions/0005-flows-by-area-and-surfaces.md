---
title: "0005: Structure flows by feature area, and add surfaces"
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# 0005: Structure flows by feature area, and add surfaces

**Date:** 2026-10-01
**Owner:** TBC
**Supersedes:** None

## Context
Flows were planned as one file per journey in `platforms/*/flows/`. Working locally on identity (sign in, password recovery, MFA), designers used numbered folders per scenario, each with its own problem, states, wireframes and prototype. That works for exploration but does not scale: several folders described failure states rather than flows, shared states were duplicated, numbering broke when scenarios were added, and parts of the product (dashboards, the map, lists) have no start or end point.

## Decision
- Group flows into feature area folders (`platforms/*/flows/<area>/`), each with a README containing a flow map, one file per flow, and a `states.md` for states shared across the area.
- Name files with descriptive slugs, not numbers. Handle variants inside a flow.
- Add `platforms/*/surfaces/` for places users work in without a fixed start or end.
- Link to wireframes and prototypes rather than storing them in the repo.
- Tag flows and surfaces with product segments in frontmatter, rather than using segments as folders, because areas are finer-grained.
- Keep each platform's flows separate, including identity, until we know how similar back office and driver experiences are.

## Alternatives considered
- One folder per scenario, as used locally. Rejected because shared states get duplicated and numbering does not scale.
- Folders by product segment. Rejected because segments are too broad for flows.
- Shared identity rules in one cross-platform file. Deferred until we know how much web and app identity have in common.

## Consequences
- Agents find one definition of each shared state, so screens stay consistent.
- Designers moving local work into the repo need to split it into flows, shared states and links to design files.
- If web and app identity turn out to share rules, a later decision can move those rules to a shared file.
