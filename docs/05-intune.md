# 05. Intune Endpoint Management

[← Project overview](../README.md) | [Screenshot catalog](../screenshots/README.md)

## Overview

Used Microsoft Intune to manage a Windows 11 virtual machine, apply endpoint protection settings, and deploy an application.

## Implementation

- Created a Windows 11 Enterprise Evaluation VM using Hyper-V.
- Joined the VM to Microsoft Entra ID and enrolled it in Intune through automatic enrollment.
- Scoped automatic enrollment to the `SG-ITSupport` user group.
- Created `SG-ManagedWindows` to target device-based deployments.
- Applied `WIN-001-Defender-PUA-Protection` to block potentially unwanted applications.
- Assigned **Company Portal** as a required Microsoft Store application.

## Results

| Validation | Result |
| --- | --- |
| Windows device enrollment | VM appeared as managed in Intune |
| Defender PUA policy | Reported **Succeeded**; blocking visible in Windows Security |
| Company Portal | Reported **Installed** and launched on the VM |

## Evidence

**Enrolled Windows device**

![Windows VM managed in Intune](../screenshots/05-intune/01-enrolled-windows-vm.png)

**Endpoint protection**

![Defender PUA policy succeeded](../screenshots/05-intune/04-defender-policy-succeeded.png)

**Application deployment**

![Company Portal installed report](../screenshots/05-intune/07-company-portal-installed-report.png)

## Notes

Testing was performed on **one virtual machine**. Windows Autopilot, multi-device rollout, and production application packaging were not included.
