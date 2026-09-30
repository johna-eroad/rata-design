---
title: Visual references
platform: all
status: approved
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Visual references

> Catalogue of visual reference assets in [`assets/`](../assets/). This
> spec exists so AI design tools and human contributors know what each
> asset shows, why it's included, and what it should (and shouldn't) be
> used for. Add an entry here whenever an asset is added to `assets/`, because
> uncatalogued images are not considered part of the design system
> source material.

## Purpose

Text-based token and component specifications are necessary but not
sufficient for visual extraction. Real screenshots, brand marks, and
icon samples let AI design tools (e.g. Claude Design) and human
contributors verify that generated or implemented work actually matches
the system, not just its documented values.

## VR-1: Assets are reference material, not production source

Files in `assets/` are for visual verification and extraction context
only. They are not production-ready exports and must not be imported
directly into application code or component libraries. Production
assets live in the relevant repository (e.g. `ui-library`).

## VR-2: Every asset has a catalogue entry

Every file added to `assets/` must have a corresponding entry below
describing what it shows, the platform/domain it represents (web or
app), and why it was included. Assets without an entry should be
treated as unverified and not relied upon.

## Logo

| Asset | Shows | Notes |
| --- | --- | --- |
| `logo/EROAD_Logo_RGB.png` | EROAD brand mark: red square with white checkerboard "E", RGB colour | Primary lockup. No dark/light or icon-only variants yet. |

## Screenshots

All screenshots are from MyEROAD (web, React/AntD). No app (KMP/Material 3) screenshots yet. This is an open gap; see [`platforms/README.md`](../platforms/README.md).

| Asset | Platform | Shows | Notes |
| --- | --- | --- | --- |
| `screenshots/MyEROAD-Dashboard.png` | Web | Dashboard: card grid of summary widgets (large numeric stat + label, small data tables inside cards, empty state with icon), left icon nav rail, top app bar with clock/help/settings | Good reference for card layout, big-number stat pattern, empty states |
| `screenshots/MyEROAD-SmartRules.png` | Web | Full-width data table (Smart rules) with column sort, header action buttons (History / Subscriptions / + Add), pagination footer | Reference for standard list/table page composition |
| `screenshots/MyEROAD-Replay.png` | Web | Filterable table with thumbnails, coloured event-severity tags/badges, status badges, date-range picker, bulk actions toolbar | Reference for tag/badge colour coding and filter bar pattern |
| `screenshots/MyEROAD-Assets.png` | Web | Data table with status badges (Overdue, Failed, Attention, colour-coded), priority chips, filter row, view toggle, pagination | Reference for status/priority badge colour semantics |
| `screenshots/MyEROAD-Drivers.png` | Web | Summary stat card (breakdown list) above a searchable/filterable data table; feature toggle in top bar | Reference for stat-card + table combination on one page |
| `screenshots/MyEROAD-Map.png` | Web | Split view: filterable list panel + map with pin markers/clustering | Reference for list/map split-pane pattern |
| `screenshots/MyEROAD-Map-OpenDrawer.png` | Web | Map view with a right-side drawer panel open ("Plan route": address inputs, suggestions list, close/reset actions) | Reference for overlay drawer/panel pattern on top of a full-bleed surface |

## Icons

Curated sample from the AntD outlined icon set actually in use, not a full icon export (see `assets/README.md`).

| Asset | Shows | Notes |
| --- | --- | --- |
| `icons/arrow-left.svg`, `icons/arrow-right.svg` | Directional navigation | |
| `icons/bell.svg` | Notifications | |
| `icons/calendar.svg` | Date/scheduling | |
| `icons/check.svg`, `icons/check-circle.svg` | Confirmation / success state | |
| `icons/close.svg` | Dismiss / cancel | |
| `icons/delete.svg` | Destructive action | |
| `icons/download.svg`, `icons/upload.svg` | File transfer | |
| `icons/edit.svg` | Edit action | |
| `icons/exclamation-circle.svg`, `icons/warning.svg`, `icons/info-circle.svg` | Status/alert states (error, warning, info) | |
| `icons/filter.svg` | Filtering | |
| `icons/home.svg` | Primary navigation | |
| `icons/menu.svg` | Navigation toggle | |
| `icons/plus.svg` | Add/create action | |
| `icons/search.svg` | Search | |
| `icons/setting.svg` | Settings/configuration | |
| `icons/user.svg` | Account/profile | |

All are outlined style, consistent stroke weight, representative of the icon style in use across MyEROAD, not an exhaustive set.

## VR-3: Scope

Screenshots should show real, representative product surfaces:
prioritise screens that exercise multiple components and states
(forms, tables, navigation, empty/error states) over single-component
close-ups, since composition and layout patterns are otherwise
undocumented (see open gap noted in `component-governance.md`).
