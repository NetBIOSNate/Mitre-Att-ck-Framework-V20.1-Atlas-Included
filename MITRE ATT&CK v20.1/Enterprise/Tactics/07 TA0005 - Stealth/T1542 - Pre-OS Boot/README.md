# T1542 - Pre-OS Boot

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may abuse Pre-OS Boot mechanisms as a way to establish persistence on a system. During the booting process of a computer, firmware and various startup services are loaded before the operating system. These programs control flow of execution before the operating system takes control.(Citation: Wikipedia Booting)

Adversaries may overwrite data in boot drivers or firmware such as BIOS (Basic Input/Output System) and The Unified Extensible Firmware Interface (UEFI) to persist on systems at a layer below the operating system. This can be particularly difficult to detect as malware at this level will not be detected by host software-based defenses.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1542)

**Tactics**  [Persistence](../../05%20TA0003%20-%20Persistence/README.md), [Stealth](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1542.003 - Bootkit](T1542.003%20-%20Bootkit/README.md)
- [T1542.002 - Component Firmware](T1542.002%20-%20Component%20Firmware/README.md)
- [T1542.004 - ROMMONkit](T1542.004%20-%20ROMMONkit/README.md)
- [T1542.001 - System Firmware](T1542.001%20-%20System%20Firmware/README.md)
- [T1542.005 - TFTP Boot](T1542.005%20-%20TFTP%20Boot/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Perform audits or scans of systems, permissions, insecure software, insecure configurations, etc. to identify potential weaknesses.
- [M1046 - Boot Integrity](../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Use Trusted Platform Module technology and a secure or trusted boot process to prevent system integrity from being compromised. Check the integrity of the existing BIOS or EFI to determine if it is vulnerable to modification. (Citation: TCG Trusted Platform Module) (Citation: TechNet Secure Boot Process) [TCG Trusted Platform Module](http://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf) · [TechNet Secure Boot Process](https://docs.microsoft.com/en-us/windows/security/information-protection/secure-the-windows-10-boot-process)
- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Prevent access to file shares, remote access to systems, unnecessary services. Mechanisms to limit access may include use of network concentrators, RDP gateways, etc.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure proper permissions are in place to help prevent adversary access to privileged accounts necessary to perform these actions
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Patch the BIOS and EFI as necessary.

## Detection strategies

- [DET0278 - Detection Strategy for T1542 Pre-OS Boot](../../../Defenses/Detection%20Strategies/DET0278%20-%20Detection%20Strategy%20for%20T1542%20Pre-OS%20Boot.md)

## Sources

- [Wikipedia Booting](https://en.wikipedia.org/wiki/Booting)
