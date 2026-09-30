---
title: Frontmatter schema
platform: all
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/5042110686
---

# Frontmatter schema

Every markdown file in this repo starts with this frontmatter, so agents can judge a file's relevance and freshness, and skip placeholders.

```yaml
---
title: [File title]
platform: web | app | cross-platform | all
status: placeholder | draft | review | approved | deprecated
owner-team: ux | engineering
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: [Link to Confluence, Figma or engineering repo, or TBC]
---
```

## Fields

| Field | Values | Meaning |
| --- | --- | --- |
| `title` | Free text | The file's title, matching its first heading. |
| `platform` | `web`, `app`, `cross-platform`, `all` | Who the guidance applies to. Use `all` for `foundations/`, `domain/`, `research/`, `agent/` and `decisions/` unless the file is about one platform. Use `cross-platform` only in `cross-platform/`. |
| `status` | See below | How far the content can be trusted. |
| `owner-team` | `ux`, `engineering` | The team that owns the content. Should match [CODEOWNERS](../CODEOWNERS). |
| `owner` | Name or `TBC` | The person accountable for the file. |
| `reviewer` | Name or `TBC` | The person who approves changes. |
| `last-reviewed` | `YYYY-MM-DD` or `TBC` | When the owner last confirmed the file is accurate. |
| `source` | URL, repo path or `TBC` | Where the content comes from, if it lives or started somewhere else. |

## Status values

| Status | Meaning | How agents treat it |
| --- | --- | --- |
| `placeholder` | Structure only, no guidance yet | Skip it, and say the guidance is missing. |
| `draft` | Being written | Use it as provisional, and say so. |
| `review` | Ready for review | Use it, noting it is not yet approved. |
| `approved` | Signed off | Use it. |
| `deprecated` | No longer in force | Do not use it. Follow any link to its replacement. |

## Exceptions

- `CODEOWNERS` and `CHANGELOG.md` have no frontmatter.
- `SKILL.md` files in `agent/skills/` keep only the Agent Skills frontmatter (`name`, `description`, `allowed-tools`), because extra keys can stop skills loading. Their owner is set in [CODEOWNERS](../CODEOWNERS).
- Files in `agent/templates/` carry their own frontmatter, plus the frontmatter to copy inside a fenced block.

## Related files
- [`CONTRIBUTING.md`](../CONTRIBUTING.md)
- [`AGENTS.md`](../AGENTS.md)
