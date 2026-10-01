---
title: Agent guide
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/5042110686
---

# Agent guide

Start here. This file tells you how to use this repo.

## What this repo is

A structured source of truth about EROAD's users, design principles, design system guidance and platform conventions. It exists so that AI-assisted design and code output matches how we build. It holds UX guidance, not code: code and token values live in engineering repos, and this repo links to them.

## How to navigate

1. **Foundations first.** Read what applies to every user in [`foundations/`](foundations/): [principles](foundations/principles.md), [accessibility standards](foundations/accessibility-standards.md), [component governance](foundations/component-governance.md) and the [glossary](foundations/glossary.md).
2. **Then the relevant platform.** Read [`platforms/README.md`](platforms/README.md), then the platform your task is for:
   - [`platforms/web/`](platforms/web/README.md): web, built in React with Ant Design. For example, dispatchers.
   - [`platforms/app/`](platforms/app/README.md): app, built in Kotlin Multiplatform with Material 3, on Android and iOS. For example, drivers.
3. **Then cross-platform, if the task involves both web and app users.** Read [`cross-platform/`](cross-platform/), for example when a dispatcher assigns a job that a driver receives.
4. **Use supporting context as needed:** [`domain/product-segments/`](domain/product-segments/README.md) for the product segment a task belongs to and its north star, [`domain/`](domain/) for other business and regulatory context, [`decisions/`](decisions/) for recorded decisions, and [`agent/skills/`](agent/skills/README.md) for reusable review skills.

## Terminology

- Say **app** for the Kotlin Multiplatform platform, never "mobile". Web is also used on phones, so "mobile" is ambiguous. Name Android or iOS only when something differs between them.
- Say **web** for the React platform, on any device.
- If a request says "mobile", ask whether it means the app or web on a phone.

## Precedence rules

- Platform guidance overrides foundations.
- Approved decisions in [`decisions/`](decisions/) override older guidance.
- Skip any file with `status: placeholder`. Treat `status: draft` as provisional, and `status: deprecated` as no longer in force. See [`agent/frontmatter-schema.md`](agent/frontmatter-schema.md).
- Never apply web user or pattern guidance to app, or app guidance to web.
- Product segments span both platforms. A segment's north star frames trade-offs, but user, pattern and flow guidance still comes from the platform.
- Evidence links (to research, studies or analytics) are for tracing decisions back, not requirements. Do not follow them to work out what to build. If guidance seems to conflict with research you have been given, say so and ask.
- eRUC is out of scope. It has its own brand and style guide, so do not apply this repo's guidance to it.

## Which accessibility file to read

- **Design requirements:** `platforms/*/accessibility.md`, which builds on [`foundations/accessibility-standards.md`](foundations/accessibility-standards.md).
- **Implementation:** `platforms/*/engineering/accessibility.md`.

## Ownership

Code and token values live in engineering repos. Follow the links in `platforms/*/tokens/README.md` and `platforms/*/components/README.md` rather than inventing values or component APIs. Until engineering links the token source, use the interim values in [`foundations/tokens/values-interim.md`](foundations/tokens/values-interim.md) (see [decision 0001](decisions/0001-interim-token-values.md)).

This repo is read-only for AI design tools that consume it. Do not commit changes to it, or to any shared component repo, from a design tool. Prototypes you produce are exploratory input, not approved changes (see CG-6 in [component governance](foundations/component-governance.md)).

## When guidance is missing

If the guidance you need is missing, is a placeholder, or conflicts with another file, say so and ask. Do not guess, and do not fill the gap with generic conventions or guidance from the other platform.
