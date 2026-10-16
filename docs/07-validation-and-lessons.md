# 07. Validation and Lessons Learned

[← Project overview](../README.md) | [Screenshot catalog](../screenshots/README.md)

## Testing Summary

| Area | Verified result |
| --- | --- |
| Identity and licensing | 20 employees created and licensed through a security group |
| Administration | Selected role permissions and restrictions tested |
| Conditional Access | Report-only evaluations reviewed; policies not enforced |
| SharePoint | IT Support member allowed; Sales nonmember denied |
| Intune | Windows VM enrolled, Defender PUA policy applied, Company Portal installed |
| BitLocker | 100% encrypted, protection enabled, recovery record backed up |
| Compliance | BitLocker, Windows Firewall, and Secure Boot checks passed |

## Troubleshooting Experience

- **License assignment:** An initial `@odata.bind` error cleared after retrying. Its root cause was not confirmed.
- **Defender access:** The portal initially showed loading and permission issues; the Alerts page became available after setup progressed.
- **BitLocker:** Removing the attached bootable Windows ISO resolved an encryption setup issue.
- **Policy verification:** Used Intune deployment results, Windows Security, sign-in logs, and individual compliance checks rather than relying on configuration screens alone.

## Project Limitations

This was a personal proof of concept using fictional employees, a Microsoft 365 Business Premium trial, and **one** Windows VM. Conditional Access was not enforced; SharePoint uploads were not a complete migration; independent emergency-access authentication and live BitLocker recovery were not tested.

## Next Improvements

- Validate emergency-access readiness and authentication methods before considering an enforced Conditional Access rollout.
- Test meaningful SharePoint file migrations with content verification.
- Expand endpoint testing to Windows updates, Autopilot, additional applications, and multiple devices.

## Key Takeaway

The project reinforced the importance of **testing the outcome**, not just confirming that a configuration was created.
