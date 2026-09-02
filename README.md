# Rātā Design

ERoad Rātā design system specifications and documentation.

This repository is intentionally not a code or build project. It is a documentation-first standards repository for the Rātā design system. Its purpose is to hold the authoritative design specifications, implementation guidance, AI skills, and agent definitions that keep product work aligned to the design system across human teams and AI-assisted builders.

## Repository purpose

Rātā Design exists to provide a shared source of truth for:

- product and interface standards
- visual and interaction specifications
- language and content guidance
- design principles and quality criteria
- reusable AI skills for design and build work
- agent instructions and behavioural guardrails

The repository is designed for clarity, reviewability, and agent-readability rather than for shipping application code.

## Repository structure

- `docs/` — general documentation, process guidance, and shared standards
- `specifications/` — authoritative design specifications and criteria
- `skills/` — reusable skills and capability definitions for human and AI contributors
- `agents/` — agent instructions, conventions, and operational guardrails

## Operating principles

- Design decisions belong in this repository, not in ad hoc implementation notes.
- Specifications should be explicit, reviewable, and versionable.
- AI agents should use the repository as the canonical source of system intent.
- Product work should align to the design system before implementation begins.
- This repository is read-only source of truth for any AI design tool that
  consumes it (e.g. Claude Design). Such tools MUST NOT commit changes back
  to this repository or to any shared component repository (e.g.
  `ui-library`). Their output is exploratory prototype material only, to be
  routed through the approved processes in
  [`specifications/component-governance.md`](./specifications/component-governance.md)
  before it becomes part of the system.

## Contributing

Add or update documentation in the most relevant section. Keep content explicit, factual, and aligned to the design system. If a change affects implementation requirements, document the source of truth here before shipping related product work.
