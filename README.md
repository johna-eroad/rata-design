---
title: Rātā Design
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/5042110686
---

# Rātā Design

The UX context for EROAD's products: who our users are, the principles we design by, how to use the Rātā design system, and the conventions for each platform. It gives AI agents (and people) one structured source of truth, so AI-assisted design and code output matches how we build.

This is a documentation repo, not a code or build project. Agents should start at [AGENTS.md](AGENTS.md).

## Structure

| Folder | What it holds |
| --- | --- |
| [`foundations/`](foundations/) | Only what is true for every user: principles, UX goals, glossary, voice and tone, accessibility standards, component governance and token architecture |
| [`domain/`](domain/) | Product, market, regulatory and ecosystem context |
| [`cross-platform/`](cross-platform/) | Moments where web and app users interact, and the entities both sides see |
| [`research/`](research/) | Research findings and sources |
| [`platforms/web/`](platforms/web/README.md) | Web (React): users, personas, jobs to be done, patterns, flows, content, states and engineering guidance |
| [`platforms/app/`](platforms/app/README.md) | App (Kotlin Multiplatform): the same, for app users |
| [`agent/`](agent/) | Skills, templates, evals, the frontmatter schema and repo integration |
| [`decisions/`](decisions/) | Decision log with rationale |
| [`assets/`](assets/README.md) | Visual reference images, catalogued in [`foundations/visual-references.md`](foundations/visual-references.md) |

Web and app serve different users with different jobs (for example, dispatchers use web and drivers use app), so user, experience and pattern content stays inside each platform.

## Ownership model

| Area | Owner | Where it lives |
| --- | --- | --- |
| Token decisions, naming, meaning and usage rules | UX | This repo |
| Token source files, build pipeline and published packages | Engineering | Engineering repos |
| Patterns, use cases, journeys and flows | UX | This repo |
| Users, personas, archetypes and jobs to be done | UX | This repo |
| Principles, content and accessibility requirements | UX | This repo |
| Component code and Figma Code Connect mappings | Engineering | Engineering repos |
| Engineering conventions and implementation guidance | Engineering (input) | Engineering repos, or this repo as UX-owned files. To be confirmed |

Everything in this repo is owned by UX (see [decision 0003](decisions/0003-ux-owns-this-repo.md)). Where engineering guidance is kept here, engineering provides the input and UX owns the file.

There is only one source of truth for any value or piece of code. This repo links to engineering repos rather than duplicating them. Token values are held here for now as an interim measure (see [decision 0001](decisions/0001-interim-token-values.md)).

This repo is read-only for AI design tools that consume it (for example Claude Design). Their output is exploratory and goes through [component governance](foundations/component-governance.md) before it becomes part of the system.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to add or change content, use the templates and frontmatter, get changes reviewed, and log decisions. Owners are listed in [CODEOWNERS](CODEOWNERS), and changes are recorded in the [CHANGELOG](CHANGELOG.md).

## Background

The structure and the open questions for engineering are described on Confluence: [UX Context Repo: Structure and Engineering Input](https://eroad.atlassian.net/wiki/spaces/UD/pages/5042110686).
