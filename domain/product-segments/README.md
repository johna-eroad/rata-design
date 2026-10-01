---
title: Product segments
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Product segments

Every EROAD product and platform feature fits into a product segment. Each segment has a value statement (what it offers customers) and a north star (what it aims to become). Read this when you need to know which segment a task belongs to, or what that segment is trying to achieve.

## Segments

| Segment | Slug | North star |
| --- | --- | --- |
| [Core Fleet](core-fleet.md) | `core-fleet` | To be the indispensable operational backbone of every fleet, where real-time visibility, seamless connectivity and intuitive management empower every fleet operator to make faster, smarter decisions every single day. |
| [Vehicle and Driver](vehicle-and-driver.md) | `vehicle-and-driver` | To seamlessly bridge the physical and digital worlds of every driver and vehicle, delivering a best-in-class connected experience that is device-agnostic, intuitive and reliable, so that no asset or driver is ever outside the ecosystem, regardless of how they connect. |
| [Data and Intelligence](data-and-intelligence.md) | `data-and-intelligence` | To be the trusted data intelligence layer of the fleet industry, connecting ecosystems, surfacing insights and empowering operators and partners to make decisions that create lasting competitive advantage from the wealth of data their fleets generate. |
| [Safety](safety.md) | `safety` | To eliminate preventable accidents and protect every driver on every journey, creating a world where data-driven coaching, intelligent monitoring and proactive risk management make fleet operations safer for drivers, passengers and the communities they travel through. |
| [Regulatory](regulatory.md) | `regulatory` | To make fleet compliance effortless and invisible, freeing operators from the burden of ever-changing regulations so they can focus on running their business with complete confidence that they are always audit-ready, wherever they operate. |
| [Operational Efficiency](operational-efficiency.md) | `operational-efficiency` | To unlock the maximum productive potential of every fleet asset, driver and load, where intelligent automation, real-time monitoring and deep analytics eliminate waste, reduce downtime and drive measurable profitability across every operation. |

## How to use segments

- **Tag content by segment.** Add the slug to the `segments` field in the frontmatter of personas, user types, jobs to be done, flows, patterns, handoffs and research findings (see [frontmatter schema](../../agent/frontmatter-schema.md)). Content can belong to more than one segment.
- **Frame trade-offs.** When choosing between options, prefer the one that moves the segment towards its north star.
- **Segments span platforms.** Most segments serve both web and app users. Segment files describe purpose, not user experience: user, pattern and flow guidance stays in `platforms/web/` and `platforms/app/`.

## Out of scope: eRUC

eRUC (short for the "eRUC for All" project) is EROAD's consumer product for New Zealand vehicle owners. It has its own brand identity and style guide, and is not covered by this repo. Do not apply guidance from this repo to eRUC work.

## Source

The official value statements and north stars are still being written. The text here is adapted to this repo's writing style. Update it when the official version is published.

## Related files
- [`domain/product-overview.md`](../product-overview.md)
- [`foundations/glossary.md`](../../foundations/glossary.md)
