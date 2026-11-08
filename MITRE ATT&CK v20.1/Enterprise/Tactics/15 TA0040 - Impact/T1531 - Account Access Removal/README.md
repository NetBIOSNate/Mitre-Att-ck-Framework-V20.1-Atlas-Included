# T1531 - Account Access Removal

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may interrupt availability of system and network resources by inhibiting access to accounts utilized by legitimate users. Accounts may be deleted, locked, or manipulated (ex: changed credentials, revoked permissions for SaaS platforms such as Sharepoint) to remove access to accounts.(Citation: Obsidian Security SaaS Ransomware June 2023) Adversaries may also subsequently log off and/or perform a [System Shutdown/Reboot](https://attack.mitre.org/techniques/T1529) to set malicious changes into place.(Citation: CarbonBlack LockerGoga 2019)(Citation: Unit42 LockerGoga 2019)

In Windows, [Net](https://attack.mitre.org/software/S0039) utility, <code>Set-LocalUser</code> and <code>Set-ADAccountPassword</code> [PowerShell](https://attack.mitre.org/techniques/T1059/001) cmdlets may be used by adversaries to modify user accounts. Accounts could also be disabled by Group Policy. In Linux, the <code>passwd</code> utility may be used to change passwords. On ESXi servers, accounts can be removed or modified via esxcli (`system account set`, `system account remove`).

Adversaries who use ransomware or similar attacks may first perform this and other Impact behaviors, such as [Data Destruction](https://attack.mitre.org/techniques/T1485) and [Defacement](https://attack.mitre.org/techniques/T1491), in order to impede incident response/recovery before completing the [Data Encrypted for Impact](https://attack.mitre.org/techniques/T1486) objective.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1531)

**Tactics**  [Impact](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [SaaS](../../../Platforms/SaaS.md), [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [ESXi](../../../Platforms/ESXi.md)

## Procedure examples

- [G1024 - Akira](../../../Threat%20Intelligence/Groups/G1024%20-%20Akira.md) — [Akira](https://attack.mitre.org/groups/G1024) deletes administrator accounts in victim networks prior to encryption.(Citation: Secureworks GOLD SAHARA) [Secureworks GOLD SAHARA](https://www.secureworks.com/research/threat-profiles/gold-sahara)
- [S1134 - DEADWOOD](../../../Threat%20Intelligence/Software/Malware/S1134%20-%20DEADWOOD.md) — [DEADWOOD](https://attack.mitre.org/software/S1134) changes the password for local and domain users via <code>net.exe</code> to a random 32 character string to prevent these accounts from logging on. Additionally, [DEADWOOD](https://attack.mitre.org/software/S1134) will terminate the <code>winlogon.exe</code> process to prevent attempts to log on to the infected system.(Citation: SentinelOne Agrius 2021) [SentinelOne Agrius 2021](https://assets.sentinelone.com/sentinellabs/evol-agrius)
- [G1004 - LAPSUS$](../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has removed a targeted organization's global admin accounts to lock the organization out of all access.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [S0372 - LockerGoga](../../../Threat%20Intelligence/Software/Malware/S0372%20-%20LockerGoga.md) — [LockerGoga](https://attack.mitre.org/software/S0372) has been observed changing account passwords and logging off current users.(Citation: CarbonBlack LockerGoga 2019)(Citation: Unit42 LockerGoga 2019) [CarbonBlack LockerGoga 2019](https://www.carbonblack.com/2019/03/22/tau-threat-intelligence-notification-lockergoga-ransomware/) · [Unit42 LockerGoga 2019](https://unit42.paloaltonetworks.com/born-this-way-origins-of-lockergoga/)
- [S0576 - MegaCortex](../../../Threat%20Intelligence/Software/Malware/S0576%20-%20MegaCortex.md) — [MegaCortex](https://attack.mitre.org/software/S0576) has changed user account passwords and logged users off the system.(Citation: IBM MegaCortex) [IBM MegaCortex](https://securityintelligence.com/posts/from-mega-to-giga-cross-version-comparison-of-top-megacortex-modifications/)
- [S0688 - Meteor](../../../Threat%20Intelligence/Software/Malware/S0688%20-%20Meteor.md) — [Meteor](https://attack.mitre.org/software/S0688) has the ability to change the password of local users on compromised hosts and can log off users.(Citation: Check Point Meteor Aug 2021) [Check Point Meteor Aug 2021](https://research.checkpoint.com/2021/indra-hackers-behind-recent-attacks-on-iran/)

## Detection strategies

- [DET0120 - Account Access Removal via Multi-Platform Audit Correlation](../../../Defenses/Detection%20Strategies/DET0120%20-%20Account%20Access%20Removal%20via%20Multi-Platform%20Audit%20Correlation.md)

## Sources

- [CarbonBlack LockerGoga 2019](https://www.carbonblack.com/2019/03/22/tau-threat-intelligence-notification-lockergoga-ransomware/)
- [Unit42 LockerGoga 2019](https://unit42.paloaltonetworks.com/born-this-way-origins-of-lockergoga/)
- [Obsidian Security SaaS Ransomware June 2023](https://web.archive.org/web/20230608061141/https://www.obsidiansecurity.com/blog/saas-ransomware-observed-sharepoint-microsoft-365/)
