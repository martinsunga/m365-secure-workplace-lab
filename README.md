# Microsoft 365 Implementation Project

I built a simulated Microsoft 365 environment for **Nitram Technologies**, a fictional IT services company with 20 employees.

The goal of this project was to gain hands-on experience in Microsoft 365 administration, covering identity and access management, security, collaboration, and endpoint management.

Throughout the implementation, I tested user permissions, validated security configurations, deployed applications through Intune, and documented the results.

## Implementation Overview

| Area | Implementation | Results |
| --- | --- | --- |
| **Identity Management** | Created 20 employee accounts in Microsoft Entra ID using manual and bulk provisioning | 20 users successfully created across six departments |
| **License Management** | Configured group-based Microsoft 365 Business Premium licensing | All 20 employees received inherited licenses |
| **Administrative Roles** | Assigned Helpdesk, User, Security Reader, and Billing Administrator roles | Tested selected administrative permissions and restrictions |
| **Conditional Access** | Configured passwordless MFA and legacy authentication policies | Evaluated in Report-only mode; not enforced |
| **SharePoint Online** | Created a private IT Support team site | Verified authorized and unauthorized user access |
| **Microsoft Intune** | Enrolled a Windows 11 virtual machine and configured endpoint protection | Device successfully enrolled and security settings applied |
| **Application Deployment** | Deployed Company Portal as a required application | Installation verified on the managed device |
| **BitLocker & Compliance** | Configured disk encryption and device compliance requirements | BitLocker protection enabled; Firewall, Secure Boot, and BitLocker compliance checks passed |

## Project Documentation

The following documentation provides details about the implementation, technical decisions, testing, and results.

| Documentation | Description |
| --- | --- |
| [01. Identity and Licensing](docs/01-identity-and-licensing.md) | User provisioning, security groups, and group-based licensing |
| [02. Delegated Administration](docs/02-admin-roles.md) | Administrative role assignments and permission testing |
| [03. Identity Security](docs/03-conditional-access.md) | Conditional Access configuration and Report-only testing |
| [04. SharePoint Collaboration](docs/04-sharepoint.md) | Team site configuration and access validation |
| [05. Intune Endpoint Management](docs/05-intune.md) | Windows enrollment, security policies, and application deployment |
| [06. BitLocker and Compliance](docs/06-bitlocker-and-compliance.md) | Device encryption, recovery-key backup, and compliance testing |
| [07. Validation and Lessons Learned](docs/07-validation-and-lessons.md) | Testing results, troubleshooting, and areas for improvement |

[View the screenshot evidence catalog](screenshots/README.md)

## Project Scope and Limitations

This project was implemented in a **Microsoft 365 Business Premium trial environment** using fictional employee accounts and a Windows 11 virtual machine.

- **Conditional Access:** Policies remained in Report-only mode while Microsoft Entra Security Defaults stayed enabled.
- **SharePoint:** File uploads and access permissions were tested, but a complete data migration was not performed.
- **Endpoint Management:** Intune deployment and compliance testing were performed on one Windows 11 virtual machine.
- **Recovery Testing:** BitLocker recovery-key backup was verified, but an actual recovery scenario was not performed.

The project demonstrates a small-business proof of concept rather than a complete production deployment.

## Technologies Used

Microsoft 365 · Microsoft Entra ID · Microsoft Intune · Microsoft Defender · SharePoint Online · Windows 11 Enterprise Evaluation · Hyper-V · GitHub
