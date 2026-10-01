---
title: Glossary
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Glossary

## Purpose
Shared definitions for terms used across this repo, such as product names, domain terms and user roles. Read this whenever a term is unclear. Other files link here rather than redefining terms.

## Content

### App
The Kotlin Multiplatform platform, on Android and iOS. Use "app" rather than "mobile". See [`platforms/app/`](../platforms/app/README.md).

### Client Admin
The highest level of user access on the customer side. Client Admins configure settings for their organisation, such as its MFA policy.

### eRUC
Short for the "eRUC for All" project: EROAD's consumer product for New Zealand vehicle owners. It has its own brand and style guide, and is out of scope for this repo.

### Feature area
A group of related flows, such as identity, with its own folder in `platforms/*/flows/`. Finer-grained than a [product segment](#product-segment).

### Flow
A task with a start and an outcome, such as signing in. See [surface](#surface) for places without a fixed start or end.

### MFA
Multi-factor authentication. Off by default; a [Client Admin](#client-admin) can make it optional or mandatory for their organisation.

### Mobile
Avoid. Web is also used on phones, so "mobile" is ambiguous. Say [app](#app) or [web](#web), or name the device if that is what you mean.

### Organisation setting
A setting a [Client Admin](#client-admin) chooses for their whole organisation that changes how flows behave for other users. Described in each flow area's `configuration.md`.

### Product segment
A grouping that every EROAD product and platform feature fits into, each with a value statement and north star: [Core Fleet](../domain/product-segments/core-fleet.md), [Vehicle and Driver](../domain/product-segments/vehicle-and-driver.md), [Data and Intelligence](../domain/product-segments/data-and-intelligence.md), [Safety](../domain/product-segments/safety.md), [Regulatory](../domain/product-segments/regulatory.md), [Operational Efficiency](../domain/product-segments/operational-efficiency.md). See [`domain/product-segments/`](../domain/product-segments/README.md).

### Step
Part of a [flow](#flow) that the user does not choose to do on its own, such as an MFA challenge. Steps shared by more than one flow have their own file.

### Surface
A place users work in and return to, with no fixed start or end, such as a dashboard, map, list or settings page. See [flow](#flow).

### Web
The React platform, used in a browser on any device, including phones. See [`platforms/web/`](../platforms/web/README.md).

Other terms to be completed by UX.

## Related files
- [`domain/product-overview.md`](../domain/product-overview.md)
- [`cross-platform/shared-entities.md`](../cross-platform/shared-entities.md)
