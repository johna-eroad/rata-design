---
title: "0004: Do not hold research findings in this repo"
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# 0004: Do not hold research findings in this repo

**Date:** 2026-10-01
**Owner:** TBC
**Supersedes:** None

## Context
The first structure included `research/findings/` (one file per finding) and `research/sources.md`, so agents could read the evidence behind design work. EROAD has a large volume of research, and a finding read on its own lacks the context UX used to weigh it: who was studied, in what situation, and which findings outweigh others.

## Decision
- Remove `research/` and the research finding template.
- UX folds research into journeys, personas, jobs to be done, patterns and decisions. These are what agents act on.
- Personas, user types and jobs to be done keep an Evidence section that links to the original research, for tracing decisions back only.

## Alternatives considered
- Keep findings, tagged by platform, user type and segment, with a lifecycle for retiring old ones. Rejected because agents could still misread individual findings and build the wrong thing.
- Keep only an index of sources. Rejected because it still points agents at raw research to interpret.

## Consequences
- Agents act only on synthesised guidance, so misreading isolated findings is no longer a risk.
- Agents cannot answer "what does the research say about X?" from this repo. People should go to the original research instead.
- Evidence links must be kept current by the file's owner.
