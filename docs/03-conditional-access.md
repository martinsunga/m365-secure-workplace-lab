# 03. Identity Security

[← Project overview](../README.md) | [Screenshot catalog](../screenshots/README.md)

## Overview

Configured three Microsoft Entra Conditional Access policies to evaluate stronger authentication and legacy-client restrictions before any enforcement.

## Implementation

| Policy | Purpose | Status |
| --- | --- | --- |
| `CA-001-Require-PWL-MFA-Pilot` | Require Passwordless MFA for pilot user Alex Reyes | Report-only |
| `CA-002-Require-PWL-MFA-AllUsers` | Require Passwordless MFA for all users except the backup Global Administrator | Report-only |
| `CA-003-Block-LegacyAuth` | Block legacy authentication clients, excluding the backup Global Administrator | Report-only |

**Security Defaults remained enabled.** None of these Conditional Access policies was switched to **On**.

## Results

- **CA-001 (pilot):** Reviewed the policy configuration and sign-in evaluation for Alex Reyes.
- **CA-002 (all users):** Reviewed a Report-only evaluation for the main administrator account. This is separate from Alex's pilot policy.
- **CA-003 (legacy authentication):** Configured the legacy-client conditions. Modern interactive sign-ins did not validate legacy-client blocking.
- Sign-in logs showed Report-only outcomes, including **Success** and **User action required**. These results describe policy evaluation, **not enforcement**.

## Evidence

**CA-001: Pilot user and evaluation**

![CA-001 pilot policy user scope](https://github.com/user-attachments/assets/93957304-0b94-4176-83de-a08e1d624fc3)

![CA-001 report-only result for pilot](https://github.com/user-attachments/assets/0e78c645-916c-4fda-b7f5-e8cce6359fc4)

**CA-002: All-users policy evaluation**

![CA-002 report-only evaluation for main administrator](https://github.com/user-attachments/assets/07a08170-8188-4339-9be0-99327bb64251)

**CA-003: Legacy client conditions**

![Legacy authentication client conditions](../screenshots/03-conditional-access/CA-003-Conditions.png)

## Notes

Passwordless readiness for all employees and independent emergency-access sign-in were not fully validated. These policies were deliberately left in Report-only mode.
