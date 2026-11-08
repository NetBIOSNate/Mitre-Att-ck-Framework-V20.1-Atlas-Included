# T1136 - Create Account

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may create an account to maintain access to victim systems.(Citation: Symantec WastedLocker June 2020) With a sufficient level of access, creating such accounts may be used to establish secondary credentialed access that does not require persistent remote access tools to be deployed on the system.

Accounts may be created on the local system or within a domain or cloud tenant. In cloud environments, adversaries may create accounts that only have access to specific services, which can reduce the chance of detection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1136)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Containers](../../../Platforms/Containers.md), [SaaS](../../../Platforms/SaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [ESXi](../../../Platforms/ESXi.md)

## Sub-techniques

- [T1136.003 - Cloud Account](T1136.003%20-%20Cloud%20Account/README.md)
- [T1136.002 - Domain Account](T1136.002%20-%20Domain%20Account/README.md)
- [T1136.001 - Local Account](T1136.001%20-%20Local%20Account/README.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) added a login to a SQL Server with `sp_addlinkedsrvlogin`.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [G0119 - Indrik Spider](../../../Threat%20Intelligence/Groups/G0119%20-%20Indrik%20Spider.md) — [Indrik Spider](https://attack.mitre.org/groups/G0119) used <code>wmic.exe</code> to add a new user to the system.(Citation: Symantec WastedLocker June 2020) [Symantec WastedLocker June 2020](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/wastedlocker-ransomware-us)
- [S1199 - LockBit 2.0](../../../Threat%20Intelligence/Software/Malware/S1199%20-%20LockBit%202.0.md) — [LockBit 2.0](https://attack.mitre.org/software/S1199) has been observed creating accounts for persistence using simple names like "a".(Citation: Palo Alto Lockbit 2.0 JUN 2022) [Palo Alto Lockbit 2.0 JUN 2022](https://unit42.paloaltonetworks.com/lockbit-2-ransomware/)
- [G1045 - Salt Typhoon](../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has created Linux-level users on compromised network devices through modification of `/etc/shadow` and `/etc/passwd`.(Citation: Cisco Salt Typhoon FEB 2025) [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) creates new user identities within the compromised organization.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Configure access controls and firewalls to limit access to domain controllers and systems used to create and manage accounts.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Protect domain controllers by ensuring proper security configuration for critical servers.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit the number of accounts with permissions to create other accounts. Do not allow domain administrator accounts to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.

## Detection strategies

- [DET0583 - Detection Strategy for T1136 - Create Account across platforms](../../../Defenses/Detection%20Strategies/DET0583%20-%20Detection%20Strategy%20for%20T1136%20-%20Create%20Account%20across%20platforms.md)

## Sources

- [Symantec WastedLocker June 2020](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/wastedlocker-ransomware-us)
