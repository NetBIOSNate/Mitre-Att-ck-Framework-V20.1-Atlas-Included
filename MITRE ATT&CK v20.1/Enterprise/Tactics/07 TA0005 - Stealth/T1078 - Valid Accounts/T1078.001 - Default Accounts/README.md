# T1078.001 - Default Accounts

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1078 - Valid Accounts](../README.md)

Adversaries may obtain and abuse credentials of a default account as a means of gaining Initial Access, Persistence, Privilege Escalation, or Defense Evasion. Default accounts are those that are built-into an OS, such as the Guest or Administrator accounts on Windows systems. Default accounts also include default factory/provider set accounts on other types of systems, software, or devices, including the root user account in AWS, the root user account in ESXi, and the default service account in Kubernetes.(Citation: Microsoft Local Accounts Feb 2019)(Citation: AWS Root User)(Citation: Threat Matrix for Kubernetes)

Default accounts are not limited to client machines; rather, they also include accounts that are preset for equipment such as network devices and computer applications, whether they are internal, open source, or commercial. Appliances that come preset with a username and password combination pose a serious threat to organizations that do not change it post installation, as they are easy targets for an adversary. Similarly, adversaries may also utilize publicly disclosed or stolen [Private Keys](https://attack.mitre.org/techniques/T1552/004) or credential materials to legitimately connect to remote environments via [Remote Services](https://attack.mitre.org/techniques/T1021).(Citation: Metasploit SSH Module)

Default accounts may be created on a system after initial setup by connecting or integrating it with another application. For example, when an ESXi server is connected to a vCenter server, a default privileged account called `vpxuser` is created on the ESXi server. If a threat actor is able to compromise this account’s credentials (for example, via [Exploitation for Credential Access](https://attack.mitre.org/techniques/T1212) on the vCenter host), they will then have access to the ESXi server.(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023)(Citation: Pentera vCenter Information Disclosure)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1078/001)

**Tactics**  [Initial Access](../../../03%20TA0001%20-%20Initial%20Access/README.md), [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md), [ESXi](../../../../Platforms/ESXi.md), [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1003 - Ember Bear](../../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) has abused default user names and passwords in externally-accessible IP cameras for initial access.(Citation: CISA GRU29155 2024) [CISA GRU29155 2024](https://www.cisa.gov/sites/default/files/2024-09/aa24-249a-russian-military-cyber-actors-target-us-and-global-critical-infrastructure.pdf)
- [G1016 - FIN13](../../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has leveraged default credentials for authenticating myWebMethods (WMS) and QLogic web management interface to gain initial access.(Citation: Sygnia Elephant Beetle Jan 2022) [Sygnia Elephant Beetle Jan 2022](https://web.archive.org/web/20220105132433/https://f.hubspotusercontent30.net/hubfs/8776530/Sygnia-%20Elephant%20Beetle_Jan2022.pdf)
- [C0038 - HomeLand Justice](../../../../Threat%20Intelligence/Campaigns/C0038%20-%20HomeLand%20Justice.md) — During [HomeLand Justice](https://attack.mitre.org/campaigns/C0038), threat actors used the built-in administrator account to move laterally using RDP and [Impacket](https://attack.mitre.org/software/S0357).(Citation: Microsoft Albanian Government Attacks September 2022) [Microsoft Albanian Government Attacks September 2022](https://www.microsoft.com/en-us/security/blog/2022/09/08/microsoft-investigates-iranian-attacks-against-the-albanian-government/)
- [S0537 - HyperStack](../../../../Threat%20Intelligence/Software/Malware/S0537%20-%20HyperStack.md) — [HyperStack](https://attack.mitre.org/software/S0537) can use default credentials to connect to IPC$ shares on remote machines.(Citation: Accenture HyperStack October 2020) [Accenture HyperStack October 2020](https://web.archive.org/web/20201101015247/https://www.accenture.com/us-en/blogs/cyber-defense/turla-belugasturgeon-compromises-government-entity)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) enabled and used the default system managed account, DefaultAccount, via `"powershell.exe" /c net user DefaultAccount /active:yes` to connect to a targeted Exchange server over RDP.(Citation: DFIR Phosphorus November 2021) [DFIR Phosphorus November 2021](https://thedfirreport.com/2021/11/15/exchange-exploit-leads-to-domain-wide-ransomware/)
- [S0603 - Stuxnet](../../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) infected WinCC machines via a hardcoded database server password.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has harvested and used vCenter Server service accounts.(Citation: Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023) [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/)

## Detection strategies

- [DET0465 - Detection of Default Account Abuse Across Platforms](../../../../Defenses/Detection%20Strategies/DET0465%20-%20Detection%20of%20Default%20Account%20Abuse%20Across%20Platforms.md)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Implement multi-factor authentication (MFA) for default accounts whenever possible to prevent unauthorized access, even if credentials for these accounts are compromised. MFA adds an additional layer of security that requires more than just a username and password, making it significantly harder for adversaries to exploit these accounts for initial access or lateral movement.
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Applications and appliances that utilize default username and password should be changed immediately after the installation, and before deployment to a production environment. (Citation: US-CERT Alert TA13-175A Risks of Default Passwords on the Internet) [US-CERT Alert TA13-175A Risks of Default Passwords on the Internet](https://www.us-cert.gov/ncas/alerts/TA13-175A)

## Sources

- [Google Cloud Threat Intelligence VMWare ESXi Zero-Day 2023](https://cloud.google.com/blog/topics/threat-intelligence/vmware-esxi-zero-day-bypass/)
- [AWS Root User](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html)
- [Microsoft Local Accounts Feb 2019](https://docs.microsoft.com/en-us/windows/security/identity-protection/access-control/local-accounts)
- [Metasploit SSH Module](https://github.com/rapid7/metasploit-framework/tree/master/modules/exploits/linux/ssh)
- [Threat Matrix for Kubernetes](https://www.microsoft.com/security/blog/2020/04/02/attack-matrix-kubernetes/)
- [Pentera vCenter Information Disclosure](https://pentera.io/blog/information-disclosure-in-vmware-vcenter/)
