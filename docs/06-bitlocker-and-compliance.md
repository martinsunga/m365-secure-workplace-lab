# 06. BitLocker and Compliance

[← Project overview](../README.md) | [Screenshot catalog](../screenshots/README.md)

## Overview

Configured disk encryption and checked the security compliance of the Intune-managed Windows 11 VM.

## Implementation

- Applied the `WIN-003-BitLocker-Encryption` configuration policy to `SG-ManagedWindows`.
- Enabled BitLocker for the operating system drive using the VM's virtual TPM.
- Verified that a BitLocker recovery-key record was backed up to Intune.
- Created **one** device compliance policy, `WIN-002-Device-Compliance`, with three requirements: BitLocker, Windows Firewall, and Secure Boot.

## Results

| Validation | Result |
| --- | --- |
| BitLocker encryption | 100% encrypted (Used Space Only; XTS-AES 128) |
| BitLocker protection | **Protection On** |
| Recovery-key backup | Recovery record visible in Intune |
| Compliance requirements | BitLocker, Firewall, and Secure Boot passed for the VM |

## Evidence

**BitLocker status**

![BitLocker protection enabled](../screenshots/05-intune/12-bitlocker-protection-on.png)

**Compliance results**

![Device compliance settings passed](../screenshots/05-intune/13-compliance-settings-passed.png)

## Notes

An attached Windows installation ISO initially prevented encryption; removing it from the virtual DVD drive resolved the issue. An actual BitLocker recovery test was **not** performed. The recovery password is not published.
