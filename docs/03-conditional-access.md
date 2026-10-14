# 03 | Conditional Access design and evaluation

[← Project overview](../README.md) | [Evidence catalog](../screenshots/README.md)

## Business requirement

Nitram Technologies needed a design for stronger sign-in controls and the ability to assess policy impact before disrupting legitimate employee access. The new tenant began with **Microsoft Entra Security Defaults enabled** and no custom Conditional Access policies.

## Policies prepared

| Policy | Coverage and control | Observed state |
| --- | --- | --- |
| `CA-001-Require-PWL-MFA-Pilot` | Alex Reyes; **Passwordless MFA** authentication strength | Report-only |
| `CA-002-Require-PWL-MFA-AllUsers` | All users except the designated backup Global Administrator; **Passwordless MFA** strength | Report-only |
| `CA-003-Block-LegacyAuth` | All users except backup Global Administrator; legacy client app categories; **Block access** grant | Report-only |

The pilot limited the initial testing scope. The broad MFA and legacy-client policies were designed for a potential future transition away from Security Defaults but **were never switched On** in this project.

### Evidence: policy scope and controls

<img width="602" height="720" alt="CA-001-Users" src="https://github.com/user-attachments/assets/93957304-0b94-4176-83de-a08e1d624fc3" />
<img width="1617" height="754" alt="CA-001-Grant" src="https://github.com/user-attachments/assets/b37c2742-e0e3-4d08-9b89-160e3c92f03c" />
<img width="609" height="727" alt="CA-002-Users" src="https://github.com/user-attachments/assets/27c6be6a-c104-4a1f-a0f6-9c7c25d02a06" />
<img width="1628" height="762" alt="CA-002-Grant" src="https://github.com/user-attachments/assets/5f7a5f5b-c46e-4ebb-8e8a-18e659cfd0a2" />
<img width="1632" height="759" alt="CA-003-Conditions" src="https://github.com/user-attachments/assets/7d7460db-563e-4d83-955a-3affa10dc7f8" />
<img width="598" height="759" alt="CA-003-Excluded" src="https://github.com/user-attachments/assets/57e1e688-8365-46e4-beee-83d36775d11c" />

## Observations

Sign-in events were evaluated in Microsoft Entra sign-in logs:

<img width="686" height="350" alt="CA-001-Report" src="https://github.com/user-attachments/assets/0e78c645-916c-4fda-b7f5-e8cce6359fc4" />
<img width="694" height="350" alt="CA-002-Report" src="https://github.com/user-attachments/assets/07a08170-8188-4339-9be0-99327bb64251" />

- A **Report-only: Success** event confirmed that the proposed policy conditions and grant requirements would have been met for that event.
- Another event showed **Report-only: User action required**, indicating an additional authentication action would have been needed for a future enforced policy.
- The legacy-client blocking policy did **not** apply to observed modern interactive sign-ins, which is expected for those client conditions.

**Important distinction:** Signing in with Microsoft Authenticator or seeing a Report-only success does **not** mean these Conditional Access policies enforced MFA. Security Defaults and registered authentication methods can affect actual sign-in behavior separately.

## Security and rollout assessment

The backup Global Administrator was excluded from the two broad policies to reduce potential lockout risk. However, **independently secured emergency authentication was not verified** during this lab, and compatible passwordless methods were not confirmed for all 20 employees.

For those reasons, the project stopped at policy configuration and evaluation. It does not claim an enforced passwordless rollout or active blocking of legacy authentication through CA-003.

**Outcome:** Three policy designs were documented and evaluated in Report-only mode, with enforcement readiness explicitly left as future work.
