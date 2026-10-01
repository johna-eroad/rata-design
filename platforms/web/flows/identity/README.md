---
title: Identity flows (web)
platform: web
status: placeholder
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Identity flows

## Scope
How back-office web users get into and stay in the product: signing in, recovering access, multi-factor authentication (MFA) and sessions. Scope details to be completed by UX.

## Users
To be completed by UX.

## Flow map
How the flows connect, and the order users usually meet them, to be completed by UX.

- [Sign in](sign-in.md)
- [First-time invited user](first-time-invited-user.md)
- [Password recovery](password-recovery.md)
- [Manage MFA](manage-mfa.md)
- [Sessions and reauthentication](session-and-reauthentication.md)

### Shared steps
Written once and used by more than one flow:

- [MFA challenge](steps/mfa-challenge.md)
- [MFA enrolment](steps/mfa-enrolment.md)

## Configuration
These flows behave differently depending on the organisation's MFA policy, set by a Client Admin. Read [`configuration.md`](configuration.md) first.

## Entry points
To be completed by UX.

## Surfaces
To be completed by UX.

## Shared states
- [Cannot complete sign-in](states.md#cannot-complete-sign-in)
- [Blocked login](states.md#blocked-login)
- [Unexpected error](states.md#unexpected-error)
- [No MFA access](states.md#no-mfa-access)
- [Access unavailable](states.md#access-unavailable)
- [Grace period active](states.md#grace-period-active)
- [Grace period expired](states.md#grace-period-expired)

## Related files
- [`platforms/web/flows/organisation-access/README.md`](../organisation-access/README.md)
- [`platforms/web/flows/README.md`](../README.md)
- [`platforms/web/states.md`](../../states.md)
