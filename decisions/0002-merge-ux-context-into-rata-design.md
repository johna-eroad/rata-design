---
title: 0002: Build the UX context structure in this repo
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/5042110686
---

# 0002: Build the UX context structure in this repo

**Date:** 2026-10-01
**Owner:** TBC
**Supersedes:** None

## Context
The UX context repo was proposed as a new repository called `ux-context`. This repo (`rata-design`) already held design principles, accessibility standards, component governance, token values, visual references and agent skills.

## Decision
Apply the UX context structure to this repo instead of creating a second one. Existing content moves into the new folders, keeping its Git history.

## Alternatives considered
- A separate `ux-context` repo. Rejected to avoid two overlapping sources of truth for agents.

## Consequences
- Old paths under `specifications/`, `skills/`, `docs/` and `agents/` no longer exist. Anything linking to them (including copies of the skills installed elsewhere) needs updating.
- The repo may be renamed later; that is a separate decision.
