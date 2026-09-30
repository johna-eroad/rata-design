---
title: 0001: Keep token values here as an interim measure
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/5042110686
---

# 0001: Keep token values here as an interim measure

**Date:** 2026-10-01
**Owner:** TBC
**Supersedes:** None

## Context
The ownership model says token values live in engineering repos and this repo links to them. Before this restructure, `specifications/design-tokens.md` held the agreed token values and described itself as the source of truth, with a generated JSON companion. Engineering has not yet confirmed where the token source lives (see the open questions in `platforms/*/tokens/README.md`).

## Decision
- Keep the token values in [`foundations/tokens/values-interim.md`](../foundations/tokens/values-interim.md) until engineering confirms the token source.
- Delete `design-tokens.json`, because this repo must not hold token JSON.
- Once the engineering source is linked, replace the interim file with a link and record a new decision that supersedes this one.

## Alternatives considered
- Remove the values now and link to `eroadTheme.ts`. Rejected because mobile has no confirmed source yet, and agents would lose values they rely on today.
- Keep both files unchanged. Rejected because the JSON duplicates values and conflicts with the ownership model.

## Consequences
- Agents can keep using the agreed values in the meantime.
- There are temporarily two places values could drift apart (this file and `eroadTheme.ts`). Discrepancies should be raised, not resolved by guessing.
- Tools that parsed `design-tokens.json` need to read the markdown or the engineering source instead.
