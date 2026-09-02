# Skills

This directory captures reusable skills that support design and implementation work for the Rātā design system.

Skills may include:

- capability definitions
- required knowledge areas
- quality checks and validation expectations
- prompts or reusable guidance for human and AI contributors

These materials should help teams and agents perform work consistent with the design system without relying on undocumented conventions.

Skills in this repository follow the [Agent Skills format](https://github.com/anthropics/skills): each skill is a folder containing a `SKILL.md` (frontmatter `name` + trigger `description`, plus guidance) and, where useful, a `references/` subfolder for larger templates loaded only when needed. Skills defer to `specifications/` as the normative source of truth rather than duplicating it — if a skill and a specification ever disagree, the specification wins.

## Contents

- [`heuristic-evaluation/`](./heuristic-evaluation/) — conducts a usability
  heuristic evaluation (Nielsen's 10) of a Rātā screen or flow, read through
  EROAD's B2B/field-operations design principles rather than generic
  consumer-app conventions.
- [`accessibility-review/`](./accessibility-review/) — audits a Rātā screen,
  flow, or component against the WCAG 2.1 AA requirements in
  [`specifications/accessibility.md`](../specifications/accessibility.md),
  across web (React/AntD), Android, and iOS (KMP/Material 3).
