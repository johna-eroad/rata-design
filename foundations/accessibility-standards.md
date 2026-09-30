---
title: Accessibility standards
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: https://eroad.atlassian.net/wiki/spaces/UD/pages/2152105802/Accessibility
---

# Accessibility

> Source of truth: [EROAD Accessibility (Confluence)](https://eroad.atlassian.net/wiki/spaces/UD/pages/2152105802/Accessibility)
> Last synced: 2026-05-19 (page version 14)
> Applies across all Rātā surfaces. See [`platforms/README.md`](../platforms/README.md) for
> the web (React/AntD) vs. app (KMP/Material 3) split referenced below.

## Context

The Rātā Design System must conform to **WCAG 2.1 Level AA** on every
surface it ships on: responsive web, Android, and iOS. This is both a
legal/ethical obligation and a usability requirement: our B2B users often
work in the field, under time pressure, on shared devices, and cannot be
assumed to have full vision, hearing, motor function, or connectivity.

The section below is normative: every requirement uses **MUST** (mandatory,
verifiable, no exceptions), **SHOULD** (strong default; deviations must be
justified), or **MAY** (optional/recommended). Each requirement states the
**outcome** first (applies to every platform), then, where the mechanism
differs, gives the **Web**, **Android**, and **iOS** implementation
separately. Treat this as acceptance criteria for any design or
implementation work, human or agent-generated.

## Requirements
### A11Y-1: Semantic structure
Outcome: every screen has a structure and every control has a name that
assistive technology can read and navigate.

- MUST use a single logical heading/content hierarchy per screen (no skipped levels).
- MUST give every interactive element (button, link, input, custom control) an accessible name.
    - **Web:** use semantic HTML elements (`<button>`, `<nav>`, `<main>`, headings, lists, form controls) instead of generic `<div>`/`<span>` with simulated behaviour. Add ARIA attributes only to fill gaps semantic HTML cannot cover (e.g. `aria-live` for dynamic regions), not  as a substitute for semantic elements. Provide the accessible name via a visible label, `aria-label`, or `aria-labelledby`.
    - **Android:** use platform-native views/Compose semantics with a correct role, and set `contentDescription` (or Compose`semantics { contentDescription = ... }`) for every control and informative image.
    - **iOS:** use native/KMP UI elements with correct accessibility traits, and set `accessibilityLabel` for every control and informative image.
### A11Y-2: Text alternatives
Outcome: no information is conveyed only through content assistive
technology cannot perceive.

- MUST provide a descriptive text alternative for every informative image, icon, or non-text content element (**Web:** `alt` text; **Android:** `contentDescription`; **iOS:** `accessibilityLabel`).
- MUST mark purely decorative images so assistive technology skips them (**Web:** `alt=""`; **Android:** `contentDescription=null` /`importantForAccessibility="no"`; **iOS:** \`isAccessibilityElement = false\`).
- MUST provide captions and transcripts for pre-recorded audio/video content; MUST provide audio descriptions where video conveys information not present in the audio track.
### A11Y-3: Colour and contrast
Outcome: content and controls remain perceivable and distinguishable for
users with low vision or colour vision deficiencies. Platform-agnostic:
applies identically on web, Android, and iOS.

- MUST meet a contrast ratio of **4.5:1** for normal text against its background.
- MUST meet a contrast ratio of **3:1** for large text (≥18pt, or ≥14pt bold) and for meaningful graphical/UI elements (icons, borders that convey state).
- MUST NOT use colour as the only signal for meaning or state (e.g. error, success, required field). Pair colour with an icon, text label, or pattern.
- SHOULD support a high-contrast and/or colourblind-friendly palette variant where the product context requires it (see the palette-extension process below).
### A11Y-4: Text and resizing
Outcome: users can enlarge text without losing content or function.
Platform-agnostic.

- MUST allow text to be resized/scaled up to **200%** with no loss of content or functionality.
    - **Web:** use relative units (`rem`/`em`/%) for text sizing rather than fixed pixel values, so browser zoom and text-resize settings work.
    - **Android/iOS:** use scalable text units (`sp` on Android, Dynamic Type / scalable fonts on iOS) rather than fixed point sizes, so OS-level text-size settings work.
### A11Y-5: Layout, responsiveness, and input
Outcome: the interface remains usable across screen sizes, zoom/magnification
levels, and input methods.

- MUST support layouts that adapt across screen sizes and devices without loss of content or function (**Web:** responsive breakpoints; \*\*Android/iOS:\*\* device size classes/adaptive layout; see [`platforms/README.md`](../platforms/README.md)).
- MUST provide touch targets of at least **44x44px** (or platform equivalent, e.g. 48x48dp on Android) for interactive elements.
- MUST remain usable when the viewport is magnified (**Web:** screen magnifier compatibility, usable at 400% browser zoom; **Android/iOS:** usable with the OS-level screen magnifier/zoom feature).
- MUST support full keyboard operability on web: every interactive element reachable and operable via keyboard alone, in a logical tab order, with a visible focus indicator at all times.
- MUST support the platform's assistive navigation in the app: full operability via TalkBack (Android) and VoiceOver (iOS), including correct reading order and focus handling for external keyboard/switch control users.
### A11Y-6: Content and language
Outcome: language and instructions are understandable. Platform-agnostic.

- MUST use clear, concise language; avoid unexplained jargon and internal terminology.
- MUST provide explicit instructions and labels for every interactive element and form field. Never rely on placeholder text alone as a label.
### A11Y-7: Forms and validation
Outcome: users can identify and correct input errors without relying on
colour or visual styling alone.

- MUST associate every form control with a visible, programmatically linked label (**Web:** `<label for>`/`aria-labelledby`; **Android/iOS:** a label associated via the platform's accessibility APIs).
- MUST NOT rely solely on colour or visual styling to indicate validation state or errors.
- MUST surface error messages that state what is wrong and how to fix it, associated with the relevant field (**Web:** e.g. `aria-describedby`;
**Android/iOS:** error text exposed to the platform accessibility service
  alongside the field).
### A11Y-8: Navigation
- **Web MUST** provide a "skip to main content" link as the first focusable element on every page.
- MUST keep navigation structure and patterns consistent across the product, respecting each platform's conventions (**Android/iOS:** native back behaviour and platform navigation patterns rather than a web-style skip link, which does not apply).
### A11Y-9: Modals and dialogs
Outcome: focus is managed predictably when a modal/dialog opens and closes.

- MUST move focus into a modal when it opens and return it to the triggering element when it closes.
- MUST trap focus within an open modal (no navigating to background content) on web; MUST equivalently prevent assistive-technology focus from leaving a modal/sheet on Android/iOS.
- MUST provide a clear, accessible control to dismiss the modal (**Web:** close button and `Esc` key; **Android/iOS:** close button and the platform's native dismiss gesture/back action).
### A11Y-10: Verification
- MUST be tested against WCAG 2.1 AA success criteria before release:
    - **Web:** automated tooling plus manual keyboard and screen-reader (NVDA/VoiceOver/JAWS) checks.
    - **Android:** automated tooling (e.g. Accessibility Scanner) plus manual TalkBack checks.
    - **iOS:** automated tooling (e.g. Xcode Accessibility Inspector) plus manual VoiceOver checks.
- SHOULD be re-verified whenever a component's markup/layout, styling, or interaction pattern changes.
## Extending the colour system (maintainer process)
Use this process when a product needs an alternative palette (e.g.
high-contrast or colourblind-friendly mode) beyond the default Rātā theme.
This applies to the shared colour tokens that back both the AntD (web) and
Material 3 (app) implementations.

1. Research the relevant colour vision deficiencies (e.g. protanopia, deuteranopia, tritanopia) or contrast needs the palette must serve.
2. Generate a candidate palette that meets the A11Y-3 contrast ratios using a tool such as [Color Safe](http://colorsafe.co/) or [Adobe Color](https://color.adobe.com/create/color-accessibility).
3. Define the palette as an override of the shared design tokens, then map it into each platform's baseline: the [Ant Design theme customisation options](https://ant.design/docs/react/customize-theme) for web, and the Material 3 colour scheme/theme APIs for the KMP app.
4. Provide a user-facing mechanism (settings/accessibility panel) to switch between the default and alternative palette at runtime, on every platform it needs to be available.
5. Verify the palette with users who have the relevant colour vision deficiency, or simulate it with a tool such as [Color Oracle](https://colororacle.org/).
6. Document the new palette and how to switch to it alongside the rest of the design system's theme documentation.
## Further reading (non-normative)

- [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
- [W3C Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/)
- [A11y Project](https://www.a11yproject.com/)
- [Inclusive Design Principles](https://inclusivedesignprinciples.org/)
- [WebAIM](https://webaim.org/)
- [Color Safe](http://colorsafe.co/)
- [Color Oracle](https://colororacle.org/)
- [Accessibility for Teams (US federal government)](https://accessibility.digital.gov/)
- [Google Material Design Accessibility](https://material.io/design/usability/accessibility.html)
- [Microsoft Inclusive Design Toolkit](https://www.microsoft.com/design/inclusive/)
- [Android accessibility developer guide](https://developer.android.com/guide/topics/ui/accessibility)
- [Apple Human Interface Guidelines: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)