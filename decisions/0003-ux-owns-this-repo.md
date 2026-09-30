---
title: "0003: UX owns everything in this repo"
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# 0003: UX owns everything in this repo

**Date:** 2026-10-01
**Owner:** TBC
**Supersedes:** None

## Context
The first version of the structure made engineering the owner of the engineering placeholders (token source, components, engineering guidance and repo integration), both in frontmatter and in CODEOWNERS.

## Decision
UX owns every file in this repo. Engineering owns code, which lives in engineering repos. Where this repo holds engineering guidance, engineering provides the input and UX owns the file.

## Alternatives considered
- Engineering owns the engineering placeholders in this repo. Rejected because ownership of this repo should sit with one team.

## Consequences
- `owner-team` is always `ux`, and CODEOWNERS lists only UX.
- Engineering input is gathered through each placeholder's open questions and through review requests, not code ownership.
