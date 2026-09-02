# Design Tokens

> Web reference implementation: `eroadTheme.ts` in `eroad/myeroad-portal`,
> `packages/ui-library/src/theme/eroadTheme/` (AntD theme).
> Mobile (Android/iOS, KMP/Material 3) equivalent: not yet documented — see
> [Platform status](#platform-status).
> Applies across all Rātā surfaces — see [`platforms.md`](./platforms.md).
> Machine-readable companion: [`design-tokens.json`](./design-tokens.json).
> This markdown file is the source of truth (see DT-1) — the JSON is
> generated from it and omits one category not yet fully captured here
> (deprecated colour hex values).

## Context

Design tokens are the named, canonical values (colour, typography, spacing,
shape, breakpoints, input sizing, elevation) that back every Rātā surface.
This document is the single source of truth for those values. Product
repos implement a platform-specific theme (the web AntD theme, a mobile
Material 3 theme) that maps onto these tokens — the values are defined
here first, then consumed by product repos, never the reverse.

## Requirements

### DT-1 — Single source of truth
- Product repos MUST derive their theme implementation from the values in
  this document; token values MUST NOT be defined or changed independently
  in a product repo.
- A new or changed token value MUST be proposed and agreed here first, then
  propagated to each platform's theme implementation.

### DT-2 — Reference by token, not raw value
- Components MUST reference a named token (e.g. `primaryBlueDefault`,
  `spacing(2)`, `sizes.md`) for colour, spacing, typography, shape, and
  elevation.
- Components MUST NOT hardcode a raw hex value, pixel value, or font size
  that duplicates a token's value.

### DT-3 — Deprecated tokens
- Tokens marked **Deprecated** (see [Colour](#colour)) MUST NOT be used in
  new work.
- Existing usages SHOULD be migrated to the non-deprecated equivalent when
  the surrounding code is touched.

### DT-4 — Extending the token set
- A genuinely new token (not achievable by composing existing ones) MUST
  follow the same request process as a new component — see
  [`component-governance.md`](./component-governance.md) — since a new
  token is itself a design system change.

## Token categories

### Colour

All colour values below are hex. Roles are grouped by purpose, not
alphabetically, so usage intent is clear.

| Role | Token | Value |
| --- | --- | --- |
| Brand | `eroadBrand` | `#EE3124` |
| Primary action (default) | `primaryBlueDefault` | `#1869B7` |
| Primary action (hover) | `primaryBlueHover` | `#4284C4` |
| Primary action (active) | `primaryBlueActive` | `#124D86` |
| Primary action (pressed) | `primaryBluePressed` | `#1693DE` |
| Surface, level 1 | `surfaceLevel1` | `#F8F8F8` |
| Surface, level 2 | `surfaceLevel2` | `#F1F1F2` |
| Surface, level 3 | `surfaceLevel3` | `#EAEAEB` |
| Surface, overlay | `surfaceOverlay` | `#FFFFFF` |
| Surface, blue hover | `surfaceBlueHover` | `#D8EBFD` |
| Surface, purple | `surfacePurple` | `#F5E6FD` |
| On-surface, body text | `onsurfaceFont` | `#3B434B` |
| On-surface, technical/secondary text | `onsurfaceTechnicalFont` | `#6E7378` |
| On-surface, elevated text | `onsurfaceElevated` | `#1D242C` |
| On-surface, borders | `onsurfaceGrayBorders` | `#C7C9CB` |

**Status colours** (success / warning / critical), each with a surface,
on-surface, and RAG (red/amber/green) variant:

| Role | Token | Value |
| --- | --- | --- |
| Success, on-surface | `onsurfaceSuccessGreen` | `#39771D` |
| Success, surface | `surfaceSuccessGreen` | `#D7F2CA` |
| Warning, on-surface | `onsurfaceWarningOrange` | `#996500` |
| Warning, surface | `surfaceWarningOrange` | `#FFF8EB` |
| Critical, on-surface | `onsurfaceCriticalRed` | `#BD0D00` |
| Critical, surface | `surfaceCriticalRed` | `#FFE5E3` |
| Critical, surface tint | `surfaceCriticalRedTint` | `#FFF1F1` |
| RAG green | `ragGreen` | `#288000` |
| RAG amber | `ragAmber` | `#FAAB00` |
| RAG red | `ragRed` | `#C7362C` |

**Decorative palette** (charts, tags, non-status accents; not for conveying
status/meaning — use the status colours above for that) — each colour has a
default, dark, and light variant:

| Colour | Default | Dark | Light |
| --- | --- | --- | --- |
| Red | `decorativeRed` `#FF584D` | `decorativeRedDark` `#C7362C` | `decorativeRedLight` `#FFB8B2` |
| Orange | `decorativeOrange` `#E86900` | `decorativeOrangeDark` `#B95400` | `decorativeOrangeLight` `#FFBD87` |
| Yellow | `decorativeYellow` `#996900` | `decorativeYellowDark` `#FFA91F` | `decorativeYellowLight` `#FFC547` |
| Blue | `decorativeBlue` `#1693DE` | `decorativeBlueDark` `#056DAD` | `decorativeBlueLight` `#91CEF2` |
| Green | `decorativeGreen` `#53A32E` | `decorativeGreenDark` `#288000` | `decorativeGreenLight` `#8FDB6C` |
| Indigo | `decorativeIndigo` `#687DFF` | `decorativeIndigoDark` `#495AD1` | `decorativeIndigoLight` `#B8C0FF` |
| Teal | `decorativeTeal` `#009E8C` | `decorativeTealDark` `#017A6C` | `decorativeTealLight` `#6EDBBF` |
| Purple | `decorativePurple` `#BF57FF` | `decorativePurpleDark` `#990AF0` | `decorativePurpleLight` `#E2B2FF` |

**Deprecated — do not use in new work** (see [DT-3](#dt-3--deprecated-tokens)):
`deprecatedSurfaceCriticalRed`, `deprecatedRagAmberText` — both fail the
contrast requirements in [`accessibility.md`](./accessibility.md) (A11Y-3)
against their non-deprecated surfaces.

All colour combinations MUST still independently satisfy the contrast
requirements in `accessibility.md` (A11Y-3) — this table defines the palette,
not pre-approved pairings.

### Typography

- Primary font: **Roboto**.
- Weights: `regular` 400, `medium` 500, `bold` 700.

Heading scale:

| Token | Font size | Line height | Weight |
| --- | --- | --- | --- |
| `h1` | 7.2rem | 8rem | bold |
| `h2` | 5.6rem | 6.4rem | bold |
| `h3` | 4.8rem | 5.6rem | bold |
| `h4` | 4.0rem | 4.8rem | bold |
| `h5` | 3.2rem | 4rem | bold |
| `h6` | 2.4rem | 3.2rem | bold |
| `h7` | 1.6rem | 2.4rem | bold |

Body/label size scale (`sizes`):

| Token | Font size | Line height |
| --- | --- | --- |
| `xxl` | 2.4rem | 3.2rem |
| `xl` | 2.0rem | 2.8rem |
| `lg` | 1.8rem | 2.4rem |
| `md` | 1.6rem | 2.4rem |
| `sm` | 1.4rem | 2rem |
| `xs` | 1.2rem | 1.6rem |
| `xxs` | 1.0rem | 1.4rem |

Sizes MUST use relative units (`rem`) on web so they scale with the
browser's text-size setting — required by `accessibility.md` A11Y-4.

### Spacing

Base unit: **4px**. Spacing scale is a multiplier of the base unit:
`spacing(n) = n × 4px`.

| `n` | Value |
| --- | --- |
| 1 | 4px |
| 2 | 8px |
| 3 | 12px |
| 4 | 16px |
| 5 | 20px |

Any spacing value in a design or implementation MUST be expressible as
`spacing(n)` for some whole or half `n`. Arbitrary spacing values (e.g. `13px`)
MUST NOT be used.

### Shape

- Border radius: **0** (square corners) is the current Rātā default across
  components. This is a deliberate design choice, not an unstyled default —
  do not "fix" it by adding rounded corners without a design system change
  request ([DT-4](#dt-4--extending-the-token-set)).

### Breakpoints

| Token | Min width |
| --- | --- |
| `xs` | 0 |
| `sm` | 375px |
| `md` | 768px |
| `lg` | 1024px |
| `xl` | 1280px |

Mobile device size classes are the platform-specific equivalent — see
[`platforms.md`](./platforms.md).

### Input sizing

Applies to inputs, selects, buttons, and similar controls.

| Token | Height |
| --- | --- |
| `small` | 24px |
| `medium` | 32px |
| `large` | 40px |
| `border` | 1px |

All interactive touch targets MUST still meet the minimum target size in
`accessibility.md` (A11Y-5, 44×44px) — pad hit areas where a visual size
below is used for a touch-operated control.

### Elevation (stacking order)

Ascending order — a higher value MUST render above a lower one:

| Layer | z-index |
| --- | --- |
| `layoutHeader` | 1100 |
| `drawer` | 1200 |
| `modal` | 1300 |
| `message` | 1400 |
| `tooltip` | 1500 |

## Platform status

- **Web:** fully implemented — see `eroadTheme.ts` in
  `eroad/myeroad-portal/packages/ui-library`, and the live token reference
  in Storybook (`storybook.eroad.io`, design system category).
- **Mobile (Android/iOS):** a Material 3 theme equivalent (colour scheme,
  type scale, shape, spacing) has not yet been mapped against this
  document. Treat mobile token values as **open** until confirmed — do not
  assume the web values apply 1:1 (e.g. Material 3 uses `dp`/`sp`, not
  `px`/`rem`, and has its own elevation model).

## Further reading (non-normative)

- [Ant Design theme customisation](https://ant.design/docs/react/customize-theme)
- [Material Design 3 — design tokens](https://m3.material.io/foundations/design-tokens/overview)
- [Ant Design colour tokens (Confluence)](https://eroad.atlassian.net/wiki/spaces/UD/pages/2152107017/Colour+Tokens)
