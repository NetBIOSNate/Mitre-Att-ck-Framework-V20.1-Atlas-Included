# T1542.001 - System Firmware

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1542 - Pre-OS Boot](../README.md)

Adversaries may modify system firmware to persist on systems.The BIOS (Basic Input/Output System) and The Unified Extensible Firmware Interface (UEFI) or Extensible Firmware Interface (EFI) are examples of system firmware that operate as the software interface between the operating system and hardware of a computer.(Citation: Wikipedia BIOS)(Citation: Wikipedia UEFI)(Citation: About UEFI)

System firmware like BIOS and (U)EFI underly the functionality of a computer and may be modified by an adversary to perform or assist in malicious activity. Capabilities exist to overwrite the system firmware, which may give sophisticated adversaries a means to install malicious firmware updates as a means of persistence on a system that may be difficult to detect.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1542/001)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Stealth](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Check the integrity of the existing BIOS or EFI to determine if it is vulnerable to modification. Use Trusted Platform Module technology. (Citation: TCG Trusted Platform Module) Move system's root of trust to hardware to prevent tampering with the SPI flash memory.(Citation: ESET LoJax Sept 2018) Technologies such as Intel Boot Guard can assist with this. (Citation: Intel Hardware-based Security Technologies) [TCG Trusted Platform Module](http://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf) · [ESET LoJax Sept 2018](https://www.welivesecurity.com/wp-content/uploads/2018/09/ESET-LoJax.pdf) · [Intel Hardware-based Security Technologies](https://www.intel.com/content/dam/www/public/us/en/documents/white-papers/security-technologies-4th-gen-core-retail-paper.pdf)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Prevent adversary access to privileged accounts or access necessary to perform this technique.
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Patch the BIOS and EFI as necessary.

## Detection strategies

- [DET0099 - Detection Strategy for T1542.001 Pre-OS Boot: System Firmware](../../../../Defenses/Detection%20Strategies/DET0099%20-%20Detection%20Strategy%20for%20T1542.001%20Pre-OS%20Boot%20-%20System%20Firmware.md)

## Procedure examples

- [S0047 - Hacking Team UEFI Rootkit](../../../../Threat%20Intelligence/Software/Malware/S0047%20-%20Hacking%20Team%20UEFI%20Rootkit.md) — [Hacking Team UEFI Rootkit](https://attack.mitre.org/software/S0047) is a UEFI BIOS rootkit developed by the company Hacking Team to persist remote access software on some targeted systems.(Citation: TrendMicro Hacking Team UEFI) [TrendMicro Hacking Team UEFI](http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-uses-uefi-bios-rootkit-to-keep-rcs-9-agent-in-target-systems/)
- [S0397 - LoJax](../../../../Threat%20Intelligence/Software/Malware/S0397%20-%20LoJax.md) — [LoJax](https://attack.mitre.org/software/S0397) is a UEFI BIOS rootkit deployed to persist remote access software on some targeted systems.(Citation: ESET LoJax Sept 2018) [ESET LoJax Sept 2018](https://www.welivesecurity.com/wp-content/uploads/2018/09/ESET-LoJax.pdf)
- [S0001 - Trojan.Mebromi](../../../../Threat%20Intelligence/Software/Malware/S0001%20-%20Trojan.Mebromi.md) — [Trojan.Mebromi](https://attack.mitre.org/software/S0001) performs BIOS modification and can download and execute a file as well as protect itself from removal.(Citation: Ge 2011) [Ge 2011](http://www.symantec.com/connect/blogs/bios-threat-showing-again)

## Sources

- [About UEFI](http://www.uefi.org/about)
- [Wikipedia UEFI](https://en.wikipedia.org/wiki/Unified_Extensible_Firmware_Interface)
- [Wikipedia BIOS](https://en.wikipedia.org/wiki/BIOS)
