# Specifications

This directory contains the authoritative specifications for the Rātā design system.

## Contents

- [`platforms.md`](./platforms.md) — foundational context on how Rātā spans
  responsive web (React/AntD), Android, and iOS (KMP/Material 3), and what's
  common vs. platform-specific. Read this first.
- [`design-principles.md`](./design-principles.md) — EROAD's core design principles
  (Design for People, Trust, Simplicity, Scalability, Action, Assurance), with
  B2B-specific context for applying them.
- [`accessibility.md`](./accessibility.md) — WCAG 2.1 AA accessibility
  requirements as declarative, testable acceptance criteria, with web vs.
  mobile implementation guidance where mechanisms differ.
- [`design-tokens.md`](./design-tokens.md) — canonical colour, typography,
  spacing, shape, breakpoint, input-sizing, and elevation values that every
  platform's theme must derive from.
- [`component-governance.md`](./component-governance.md) — the process for
  resolving a component need (Storybook → baseline library → new request)
  and getting a component change approved.
- [`visual-references.md`](./visual-references.md) — catalogue of visual
  reference assets (logo, screenshots, icons) in [`assets/`](../assets/)
  used for visual verification and extraction by AI design tools.

Use this space for:

- design principles
- interaction patterns and behavioural requirements
- visual and content standards
- acceptance criteria for design and implementation work
- specification updates that define expected system behaviour

Treat these documents as the canonical contract for aligned design and implementation.
