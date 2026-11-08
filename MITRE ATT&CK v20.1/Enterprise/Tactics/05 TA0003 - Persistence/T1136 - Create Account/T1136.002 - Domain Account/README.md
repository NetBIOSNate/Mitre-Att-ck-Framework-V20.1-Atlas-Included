# T1136.002 - Domain Account

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1136 - Create Account](../README.md)

Adversaries may create a domain account to maintain access to victim systems. Domain accounts are those managed by Active Directory Domain Services where access and permissions are configured across systems and services that are part of that domain. Domain accounts can cover user, administrator, and service accounts. With a sufficient level of access, the <code>net user /add /domain</code> command can be used to create a domain account.(Citation: Savill 1999)

Such accounts may be used to establish secondary credentialed access that does not require persistent remote access tools to be deployed on the system.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1136/002)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0003 - T1136.002 Detection Strategy - Domain Account Creation Across Platforms](../../../../Defenses/Detection%20Strategies/DET0003%20-%20T1136.002%20Detection%20Strategy%20-%20Domain%20Account%20Creation%20Across%20Platforms.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) created privileged domain accounts to be used for further exploitation and lateral movement. (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf)
- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) created two new accounts, “admin” and “система” (System). The accounts were then assigned to a domain matching local operation and were delegated new privileges.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [G1043 - BlackByte](../../../../Threat%20Intelligence/Groups/G1043%20-%20BlackByte.md) — [BlackByte](https://attack.mitre.org/groups/G1043) created privileged domain accounts during intrusions.(Citation: Cisco BlackByte 2024) [Cisco BlackByte 2024](https://blog.talosintelligence.com/blackbyte-blends-tried-and-true-tradecraft-with-newly-disclosed-vulnerabilities-to-support-ongoing-attacks/)
- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) has a module for creating a new domain user if permissions allow.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [G0093 - GALLIUM](../../../../Threat%20Intelligence/Groups/G0093%20-%20GALLIUM.md) — [GALLIUM](https://attack.mitre.org/groups/G0093) created high-privileged domain user accounts to maintain access to victim networks.(Citation: Cybereason Soft Cell June 2019)(Citation: Microsoft GALLIUM December 2019) [Cybereason Soft Cell June 2019](https://www.cybereason.com/blog/operation-soft-cell-a-worldwide-campaign-against-telecommunications-providers) · [Microsoft GALLIUM December 2019](https://www.microsoft.com/security/blog/2019/12/12/gallium-targeting-global-telecom/)
- [G0125 - HAFNIUM](../../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has created domain accounts.(Citation: Volexity Exchange Marauder March 2021)(Citation: Microsoft Silk Typhoon MAR 2025) [Volexity Exchange Marauder March 2021](https://www.volexity.com/blog/2021/03/02/active-exploitation-of-microsoft-exchange-zero-day-vulnerabilities/) · [Microsoft Silk Typhoon MAR 2025](https://www.microsoft.com/en-us/security/blog/2025/03/05/silk-typhoon-targeting-it-supply-chain/)
- [G1051 - Medusa Group](../../../../Threat%20Intelligence/Groups/G1051%20-%20Medusa%20Group.md) — [Medusa Group](https://attack.mitre.org/groups/G1051) has created a domain account within the victim environment.(Citation: CISA Medusa Group Medusa Ransomware March 2025) [CISA Medusa Group Medusa Ransomware March 2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a)
- [S0039 - Net](../../../../Threat%20Intelligence/Software/Tools/S0039%20-%20Net.md) — The <code>net user username \password \domain</code> commands in [Net](https://attack.mitre.org/software/S0039) can be used to create a domain account.(Citation: Savill 1999) [Savill 1999](https://web.archive.org/web/20150511162820/http://windowsitpro.com/windows/netexe-reference)
- [S0029 - PsExec](../../../../Threat%20Intelligence/Software/Tools/S0029%20-%20PsExec.md) — [PsExec](https://attack.mitre.org/software/S0029) has the ability to remotely create accounts on target systems.(Citation: NCC Group Fivehands June 2021) [NCC Group Fivehands June 2021](https://research.nccgroup.com/2021/06/15/handy-guide-to-a-new-fivehands-ransomware-variant/)
- [S0192 - Pupy](../../../../Threat%20Intelligence/Software/Tools/S0192%20-%20Pupy.md) — [Pupy](https://attack.mitre.org/software/S0192) can user PowerView to execute “net user” commands and create domain accounts.(Citation: GitHub Pupy) [GitHub Pupy](https://github.com/n1nj4sec/pupy)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has created and used new accounts within a victim's Active Directory environment to maintain persistence.(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts.
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Configure access controls and firewalls to limit access to domain controllers and systems used to create and manage accounts.
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Protect domain controllers by ensuring proper security configuration for critical servers.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit the number of accounts with permissions to create other accounts. Do not allow domain administrator accounts to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.

## Sources

- [Savill 1999](https://web.archive.org/web/20150511162820/http://windowsitpro.com/windows/netexe-reference)
