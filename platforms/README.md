---
title: Platforms
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Platforms

> Foundational context for how the Rātā Design System is implemented across
> product surfaces. Other specifications should reference this document
> rather than restating platform detail.
## Overview

Rātā is a single design system: one set of design principles, visual
language, and standards (see [`principles.md`](../foundations/principles.md)
and [`accessibility-standards.md`](../foundations/accessibility-standards.md)), implemented on two
platforms with different underlying technology:

| Platform | Runs on | Technology stack | Baseline component library |
| --- | --- | --- | --- |
| Web | Browsers, on any device (including phones) | React | Ant Design (AntD) |
| App | Android and iOS | Kotlin Multiplatform (KMP) | Material Design 3 (Material UI 3) |

Say "app", not "mobile", for the app platform. Web is also used on
phones, so "mobile" is ambiguous. Name Android or iOS only when a
requirement differs between them.

On both web and app, the baseline library is extended with **custom Rātā
components** built on top of it:

- **Web:** AntD + Rātā custom components (React)
- **App (Android and iOS):** Material Design 3 + Rātā custom components (KMP)
## What is common vs. platform-specific

**Common across all platforms** (defined once, applies everywhere):

- Design principles
- Visual language: colour, typography scale, spacing, iconography intent
- Content and language standards (tone, terminology, labelling conventions)
- Accessibility outcomes (e.g. contrast ratios, "don't rely on colour alone", keyboard/switch/assistive-technology operability)
- Interaction intent (what a component is for, when to use it)

**Platform-specific** ("under the hood": same intent, different
implementation):

- Concrete component APIs and markup/code (e.g. AntD React component props vs. Material 3 Compose/KMP APIs)
- Technical accessibility mechanisms (e.g. semantic HTML + ARIA on web vs. platform accessibility services, such as `contentDescription`/TalkBack on Android, `accessibilityLabel`/VoiceOver on iOS)
- Navigation and interaction patterns native to the platform (e.g. browser keyboard navigation vs. native Android and iOS gestures and platform back behaviour)
- Responsive breakpoints (web) vs. device size classes (app)
## How to write specifications given this split

When a specification in this repository states a requirement:

- If the requirement is about **intent, outcome, or standard** (e.g. "must meet 4.5:1 contrast", "must not rely on colour alone"), write it once as platform-agnostic, so it applies to web, Android, and iOS equally.
- If the requirement is about **mechanism** (e.g. "use semantic HTML" or "use `contentDescription`"), state the outcome first, then give the platform-specific implementation for each surface (Web / Android / iOS) separately, so a contributor or agent working in a single stack can find what applies to them without translating web-specific terms.
- Do not assume "web" terminology (HTML, ARIA, DOM, browser) as a proxy for "all platforms". Always check whether a requirement needs an app equivalent.
