# 07 | Verification, troubleshooting, and next steps

[← Project overview](../README.md) | [Evidence catalog](../screenshots/README.md)

## Validation summary

The table summarizes observed evidence, not assumed production behavior.

| Area | Verification activity | Observed result | Assessment |
| --- | --- | --- | --- |
| Identity | Bulk import and manual creation | 19 imported + 1 manual employee | Passed |
| Licensing | Group-inherited license assignments | 20 Business Premium employees licensed | Passed |
| Delegation | Helpdesk access to password-reset function | Function accessible; reset not executed | Partially validated |
| Security Reader | Sign-in logs / Defender alerts / reset restrictions | Allowed security viewing and denied password reset | Passed for tested actions |
| Conditional Access | Report-only tab for interactive sign-ins | Success and User action required outcomes observed | Evaluated, **not enforced** |
| SharePoint permissions | IT Support member and Sales nonmember | Member allowed; nonmember denied | Passed for tested identities |
| SharePoint documents | Sample upload | Three filenames visible; contents not validated | Upload only |
| Intune enrollment | Device in Intune | Windows VM enrolled and checked in | Passed |
| Defender PUA policy | Deployment report and Windows UI | Succeeded; PUA blocking enabled | Passed |
| Company Portal | Intune app report and local launch | Installed and opened | Passed |
| BitLocker | `manage-bde` result and Intune key record | 100% encrypted, protection On, recovery backed up | Passed |
| Device compliance | Three individual setting checks | Secure Boot, Firewall, BitLocker compliant | Passed |

## Issues encountered

| Observation | Response | What was learned |
| --- | --- | --- |
| Group licensing returned an `@odata.bind` error | Repeated the same assignment, which succeeded | Record what is observed; avoid claiming an unverified root cause |
| Defender initially showed setup/loading screens and an Incidents permission error | Allowed provisioning/setup to progress; verified Gabriel could access Alerts | Role permissions can differ by workload; avoid unnecessary elevation |
| Passwordless sign-in varied across tests | Compared sign-in methods and report-only evaluations | An authentication method used is not proof that Report-only CA enforced it |
| BitLocker rejected a VM with bootable media attached | Removed the installation ISO from the virtual DVD drive and restarted | Virtual hardware and mounted media matter to endpoint-security setup |
| Intune summary statuses initially differed from details | Relied on subsequent per-setting compliance report | Validate the specific control rather than relying only on summary counts |

## Scope boundaries

**Completed and verified:** Identity provisioning, group-based licensing, selected administrative access tests, private-site access tests, Intune enrollment, PUA configuration, Company Portal deployment, BitLocker encryption and recovery-key escrow, compliance checks.

**Configured or simulated only:** Conditional Access Report-only policies; SharePoint sample-file upload as a migration illustration.

**Not performed:** Production-scale rollout, actual server/mailbox migration, file-content integrity checks, enforcement of passwordless MFA for every employee, phishing-resistant independent emergency-access authentication validation, BitLocker recovery drill, Conditional Access compliant-device gating.

## Improvements for a production-oriented second phase

1. Establish and test dedicated emergency-access accounts with independent phishing-resistant authentication before an enforced Conditional Access rollout.
2. Verify employee readiness and authentication-method registration before requiring Passwordless MFA broadly; validate legacy-client impact before blocking.
3. Test SharePoint migration against meaningful documents, metadata, permissions, integrity checks, and a rollback/cutover plan.
4. Expand device tests to multiple hardware types; evaluate Windows Autopilot, local administrator controls, patching, and additional application deployment.
5. Add ongoing security monitoring, alert triage, and device-compliance reporting at a larger scale.

## Takeaway

The most valuable outcome of the lab was learning to **differentiate configuration from enforcement and verification**. A successful policy creation screen is not the same as a successfully applied endpoint setting, and a simulated migration is not a completed business migration. This portfolio records both the working results and the boundaries of the evidence.
