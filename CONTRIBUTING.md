---
title: Contributing
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Contributing

Thanks for helping keep this repo accurate. Agents treat it as the source of truth, so small, clear, well-labelled changes matter.

## Adding or changing content

1. **Find the right home.** Content true for every user goes in `foundations/`. Anything about a particular platform's users, patterns or flows goes in `platforms/web/` or `platforms/app/`. Moments where web and app users interact go in `cross-platform/`. If in doubt, check the folder's README.
2. **Keep files short and single-topic.** One flow, pattern, persona or decision per file.
3. **Link, don't duplicate.** Link to the [glossary](foundations/glossary.md) rather than redefining terms. Link to engineering repos rather than copying code or token values.
4. **Update frontmatter.** Set `status`, `owner`, `reviewer`, `last-reviewed` and `source` (see [frontmatter schema](agent/frontmatter-schema.md)).
5. **Add a line to the [CHANGELOG](CHANGELOG.md)** for anything agents would notice.

## Templates

Templates for new content live in [`agent/templates/`](agent/templates/): persona, user type, jobs to be done, flow, pattern, handoff, research finding and decision. Each folder README says which one to use.

For files without a dedicated template, use one of these formats:

- **UX stub:** frontmatter (`status: placeholder`, `owner-team: ux`), then `## Purpose`, `## Content` and `## Related files`.
- **Engineering placeholder:** frontmatter (`status: placeholder`, `owner-team: engineering`), then `## Purpose`, `## Open questions for engineering`, `## Decisions made` and `## Related files`.

When you fill in a stub, replace the placeholder text and move `status` to `draft` or `review`.

## Review process

- Open a pull request. [CODEOWNERS](CODEOWNERS) requests a review from the owning team: UX for content, engineering for engineering placeholders.
- A file moves from `draft` to `review` when it is ready, and to `approved` once the reviewer named in its frontmatter signs it off.
- Content synced from Confluence should keep its source link and sync date, and be updated in both places.

## When to log a decision

Add a file to [`decisions/`](decisions/) using the [decision template](agent/templates/decision-template.md) when:

- you choose between real alternatives, and the reasoning would help someone later;
- a change overrides or contradicts existing guidance;
- UX and engineering agree how something is owned or where it lives.

Approved decisions override older guidance, so when a decision changes an existing file, update that file too.

## Writing style

- Professional but friendly.
- NZ English spelling (for example "visualisation", "organisation", "colour").
- No em dashes. Use commas, colons, full stops or parentheses instead.
