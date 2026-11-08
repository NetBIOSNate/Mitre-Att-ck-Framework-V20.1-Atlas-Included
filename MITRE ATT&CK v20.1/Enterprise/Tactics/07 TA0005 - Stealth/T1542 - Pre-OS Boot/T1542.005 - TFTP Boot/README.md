# T1542.005 - TFTP Boot

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1542 - Pre-OS Boot](../README.md)

Adversaries may abuse netbooting to load an unauthorized network device operating system from a Trivial File Transfer Protocol (TFTP) server. TFTP boot (netbooting) is commonly used by network administrators to load configuration-controlled network device images from a centralized management server. Netbooting is one option in the boot sequence and can be used to centralize, manage, and control device images.

Adversaries may manipulate the configuration on the network device specifying use of a malicious TFTP server, which may be used in conjunction with [Modify System Image](https://attack.mitre.org/techniques/T1601) to load a modified image on device startup or reset. The unauthorized image allows adversaries to modify device configuration, add malicious capabilities to the device, and introduce backdoors to maintain control of the network device while minimizing detection through use of a standard functionality. This technique is similar to [ROMMONkit](https://attack.mitre.org/techniques/T1542/004) and may result in the network device running a modified image.(Citation: Cisco Blog Legacy Device Attacks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1542/005)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Stealth](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically check the integrity of the running configuration and system image to ensure they have not been modified. (Citation: Cisco IOS Software Integrity Assurance - Image File Verification) (Citation: Cisco IOS Software Integrity Assurance - Image File Integrity) (Citation: Cisco IOS Software Integrity Assurance - Change Control) [Cisco IOS Software Integrity Assurance - Image File Verification](https://tools.cisco.com/security/center/resources/integrity_assurance.html#7) · [Cisco IOS Software Integrity Assurance - Image File Integrity](https://tools.cisco.com/security/center/resources/integrity_assurance.html#30) · [Cisco IOS Software Integrity Assurance - Change Control](https://tools.cisco.com/security/center/resources/integrity_assurance.html#31)
- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Enable secure boot features to validate the digital signature of the boot environment and system image using a special purpose hardware device. If the validation check fails, the device will fail to boot preventing loading of unauthorized software. (Citation: Cisco IOS Software Integrity Assurance - Secure Boot) [Cisco IOS Software Integrity Assurance - Secure Boot](https://tools.cisco.com/security/center/resources/integrity_assurance.html#35)
- [M1035 - Limit Access to Resource Over Network](../../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Restrict use of protocols without encryption or authentication mechanisms. Limit access to administrative and management interfaces from untrusted network sources.
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific protocols, such as TFTP, can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific technique used by a particular adversary or tool, and will likely be different across various network configurations.
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Follow vendor device hardening best practices to disable unnecessary and unused features and services, avoid using default configurations and passwords, and introduce logging and auditing for detection.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Use of Authentication, Authorization, and Accounting (AAA) systems will limit actions administrators can perform and provide a history of user actions to detect unauthorized use and abuse. TACACS+ can keep control over which commands administrators are permitted to use through the configuration of authentication and command authorization. (Citation: Cisco IOS Software Integrity Assurance - AAA) (Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - AAA](https://tools.cisco.com/security/center/resources/integrity_assurance.html#38) · [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)

## Detection strategies

- [DET0582 - Detection Strategy for T1542.005 Pre-OS Boot: TFTP Boot](../../../../Defenses/Detection%20Strategies/DET0582%20-%20Detection%20Strategy%20for%20T1542.005%20Pre-OS%20Boot%20-%20TFTP%20Boot.md)

## Sources

- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
