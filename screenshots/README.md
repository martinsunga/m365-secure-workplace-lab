# Screenshot evidence catalog

[← Project overview](../README.md)

These screenshots are **supporting implementation evidence**, not a step-by-step tutorial. Some account identifiers are displayed because they belong to fictional lab users. Recovery secrets are not included.

| Evidence | What it demonstrates |
| --- | --- |
| **Identity and licensing** | |
| [01 alex user profile](01-entra-id/01-alex-user-profile.png) | Initial test account after provisioning |
| [02 department security groups](01-entra-id/02-department-security-groups.png) | Six departmental security groups |
| [03 bulk import submission](01-entra-id/03-bulk-import-submission.png) | Bulk user creation submission |
| [04 users after import](01-entra-id/04-users-after-import.png) | Directory after bulk creation |
| [05 it support group members](01-entra-id/05-it-support-group-members.png) | IT Support group membership |
| [06 business premium license group](01-entra-id/06-business-premium-license-group.png) | Dedicated license-assignment group |
| [07 license count assigned](01-entra-id/07-license-count-assigned.png) | 20 / 25 Business Premium licenses assigned |
| **Delegated administration** | |
| [01 helpdesk admin role](02-admin-roles/01-helpdesk-admin-role.png) | Helpdesk Administrator role assignment |
| [02 helpdesk password reset access](02-admin-roles/02-helpdesk-password-reset-access.png) | Helpdesk reset-password control accessible |
| [03 user admin role](02-admin-roles/03-user-admin-role.png) | User Administrator role assignment |
| [04 security reader role](02-admin-roles/04-security-reader-role.png) | Security Reader role assignment |
| [05 billing admin role](02-admin-roles/05-billing-admin-role.png) | Billing Administrator role assignment |
| [06 defender alerts read access](02-admin-roles/06-defender-alerts-read-access.png) | Security Reader access to Defender Alerts |
| [07 security reader reset restriction](02-admin-roles/07-security-reader-reset-restriction.png) | Security Reader cannot reset user password |
| **Conditional Access evaluation** | |
| [01 pilot policy scope](03-conditional-access/01-pilot-policy-scope.png) | Report-only pilot policy targeting |
| [02 pilot passwordless grant](03-conditional-access/02-pilot-passwordless-grant.png) | Pilot passwordless authentication strength |
| [03 all users policy exclusion](03-conditional-access/03-all-users-policy-exclusion.png) | Company-wide policy and backup exclusion |
| [04 all users passwordless grant](03-conditional-access/04-all-users-passwordless-grant.png) | Company-wide passwordless grant requirement |
| [05 legacy auth policy exclusion](03-conditional-access/05-legacy-auth-policy-exclusion.png) | Legacy client blocking scope and backup exclusion |
| [06 legacy client app conditions](03-conditional-access/06-legacy-client-app-conditions.png) | Legacy client application conditions |
| [07 report only success](03-conditional-access/07-report-only-success.png) | Report-only Success outcome |
| **SharePoint collaboration** | |
| [01 private team site details](04-sharepoint/01-private-team-site-details.png) | Private IT Support Team Site configuration |
| [02 team site homepage](04-sharepoint/02-team-site-homepage.png) | Team Site home page |
| [03 local source files](04-sharepoint/03-local-source-files.png) | Local sample files for upload simulation |
| [04 sharepoint uploaded files](04-sharepoint/04-sharepoint-uploaded-files.png) | SharePoint Documents library after upload |
| [05 authorized user files](04-sharepoint/05-authorized-user-files.png) | Authorized member can view library |
| [06 unauthorized access denied](04-sharepoint/06-unauthorized-access-denied.png) | Nonmember sees access restriction |
| **Intune, encryption, and compliance** | |
| [01 enrolled windows vm](05-intune/01-enrolled-windows-vm.png) | Entra-joined and Intune-managed VM |
| [02 managed windows device group](05-intune/02-managed-windows-device-group.png) | Managed Windows device security group |
| [03 defender policy configuration](05-intune/03-defender-policy-configuration.png) | Defender configuration-policy settings |
| [04 defender policy succeeded](05-intune/04-defender-policy-succeeded.png) | PUA policy deployment succeeded |
| [05 windows pua protection](05-intune/05-windows-pua-protection.png) | Windows PUA blocking and organizational control |
| [06 company portal required assignment](05-intune/06-company-portal-required-assignment.png) | Required Company Portal assignment |
| [07 company portal installed report](05-intune/07-company-portal-installed-report.png) | Intune app installed status |
| [08 company portal on vm](05-intune/08-company-portal-on-vm.png) | Company Portal open on managed VM |
| [09 bitlocker policy](05-intune/09-bitlocker-policy.png) | BitLocker configuration policy |
| [10 device config success](05-intune/10-device-config-success.png) | Device configuration profiles succeeded |
| [11 recovery key backed up REDACTED](05-intune/11-recovery-key-backed-up-REDACTED.png) | Recovery key backup record; secret redacted |
| [12 bitlocker protection on](05-intune/12-bitlocker-protection-on.png) | BitLocker encryption status on VM |
| [13 compliance settings passed](05-intune/13-compliance-settings-passed.png) | Per-setting compliance report |

**Validation note:** Screenshots show specific lab observations at the time captured. Report-only policies were not enforced, and SharePoint sample-file contents were not validated.