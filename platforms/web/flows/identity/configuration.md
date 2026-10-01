---
title: Identity configuration (web)
platform: web
status: draft
owner-team: ux
owner: TBC
reviewer: TBC
last-reviewed: TBC
source: TBC
---

# Identity configuration

## Purpose
Organisation settings that change how identity flows behave. Read this before working on any identity flow, because the right behaviour depends on these settings.

## Applies to
Web (back-office) users. Whether these settings also affect app users has not been worked through yet. Do not assume they do.

## MFA policy

**Set by:** a Client Admin, in Admin > My Organisation > Access. See [Configure MFA](../organisation-access/configure-mfa.md).

**Default:** off. MFA is not enabled unless a Client Admin turns it on for their organisation.

**Options:**
- **Off:** MFA is not used.
- **Optional:** users can choose to set up MFA, and turn it on or off from their own profile (see [Manage MFA](manage-mfa.md)).
- **Mandatory:** every user in the organisation must set up MFA. The Client Admin can set a grace period before set-up is enforced.

Further options and their details to be completed by UX.

### Effect on flows

What each flow does under each policy. Flows link to this table rather than describing the policy themselves. To be completed by UX.

| Policy | User has set up MFA? | [Sign in](sign-in.md) | [First-time invited user](first-time-invited-user.md) | [Sessions and reauthentication](session-and-reauthentication.md) |
| --- | --- | --- | --- | --- |
| Off | Not applicable | TBC | TBC | TBC |
| Optional | No | TBC | TBC | TBC |
| Optional | Yes | TBC | TBC | TBC |
| Mandatory, in grace period | No | TBC | TBC | TBC |
| Mandatory, grace period over | No | TBC | TBC | TBC |
| Mandatory | Yes | TBC | TBC | TBC |

## Related files
- [`README.md`](README.md)
- [`steps/mfa-challenge.md`](steps/mfa-challenge.md)
- [`steps/mfa-enrolment.md`](steps/mfa-enrolment.md)
- [`../organisation-access/README.md`](../organisation-access/README.md)
