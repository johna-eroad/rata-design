# Changelog

All notable changes to this repo are recorded here, newest first.

## 2026-10-01 (research)

### Removed
- `research/` and the research finding template ([decision 0004](decisions/0004-no-research-findings.md)). Research is folded into design work, which links to it as evidence.

### Changed
- Evidence sections in the persona, user type and jobs-to-be-done templates are for tracing decisions back only. `AGENTS.md` tells agents not to use them to work out requirements.

## 2026-10-01 (product segments)

### Added
- Product segments in `domain/product-segments/`: Core Fleet, Vehicle and Driver, Data and Intelligence, Safety, Regulatory and Operational Efficiency, with value statements and north stars adapted to repo style.
- Optional `segments` frontmatter field, added to the schema and content templates.
- Glossary entries for product segment and eRUC, and segment rules in `AGENTS.md`. eRUC is marked out of scope.

## 2026-10-01 (terminology and ownership)

### Changed
- Use "app", not "mobile", for the Kotlin Multiplatform platform. Added the rule to `AGENTS.md`, `CONTRIBUTING.md` and the glossary, and updated existing content.
- UX now owns every file in this repo ([decision 0003](decisions/0003-ux-owns-this-repo.md)). Engineering placeholders are `owner-team: ux`, and CODEOWNERS lists only UX.

## 2026-10-01 (initial structure)

### Added
- UX context structure: `AGENTS.md`, `CLAUDE.md`, `CONTRIBUTING.md`, `CODEOWNERS` and this changelog.
- Folders for `domain/`, `cross-platform/`, `research/`, `platforms/web/`, `platforms/app/`, `agent/` and `decisions/`, with README files explaining what belongs in each.
- UX stubs and engineering placeholders (with open questions) for content still to be written.
- Templates in `agent/templates/` and the frontmatter schema in `agent/frontmatter-schema.md`.
- Decisions [0001](decisions/0001-interim-token-values.md) (interim token values) and [0002](decisions/0002-merge-ux-context-into-rata-design.md) (build the structure in this repo).
- Frontmatter on every markdown file except skill definitions.

### Changed
- Moved `specifications/design-principles.md` to `foundations/principles.md`.
- Moved `specifications/accessibility.md` to `foundations/accessibility-standards.md`.
- Moved `specifications/component-governance.md` to `foundations/component-governance.md`.
- Moved `specifications/visual-references.md` to `foundations/visual-references.md`.
- Moved `specifications/design-tokens.md` to `foundations/tokens/values-interim.md`, reframed as interim.
- Moved `specifications/platforms.md` to `platforms/README.md`.
- Moved `skills/` to `agent/skills/`.
- Rewrote `README.md` and updated internal links to the new paths.
- Replaced em dashes in existing content, keeping the meaning the same.

### Removed
- `specifications/design-tokens.json`, because token values belong in engineering repos (see decision 0001).
- `specifications/README.md`, `docs/README.md` and `agents/README.md`, replaced by `AGENTS.md` and `README.md`.
