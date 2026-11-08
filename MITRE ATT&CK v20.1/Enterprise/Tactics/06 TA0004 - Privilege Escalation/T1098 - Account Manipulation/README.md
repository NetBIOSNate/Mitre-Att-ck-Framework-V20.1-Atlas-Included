# T1098 - Account Manipulation

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may manipulate accounts to maintain and/or elevate access to victim systems. Account manipulation may consist of any action that preserves or modifies adversary access to a compromised account, such as modifying credentials or permission groups.(Citation: FireEye SMOKEDHAM June 2021) These actions could also include account activity designed to subvert security policies, such as performing iterative password updates to bypass password duration policies and preserve the life of compromised credentials. 

In order to create or manipulate accounts, the adversary must already have sufficient permissions on systems or the domain. However, account manipulation may also lead to privilege escalation where modifications grant access to additional roles, permissions, or higher-privileged [Valid Accounts](https://attack.mitre.org/techniques/T1078).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098)

**Tactics**  [Persistence](../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md), [ESXi](../../../Platforms/ESXi.md), [IaaS](../../../Platforms/IaaS.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1098.001 - Additional Cloud Credentials](T1098.001%20-%20Additional%20Cloud%20Credentials/README.md)
- [T1098.003 - Additional Cloud Roles](T1098.003%20-%20Additional%20Cloud%20Roles/README.md)
- [T1098.006 - Additional Container Cluster Roles](T1098.006%20-%20Additional%20Container%20Cluster%20Roles/README.md)
- [T1098.002 - Additional Email Delegate Permissions](T1098.002%20-%20Additional%20Email%20Delegate%20Permissions/README.md)
- [T1098.007 - Additional Local or Domain Groups](T1098.007%20-%20Additional%20Local%20or%20Domain%20Groups/README.md)
- [T1098.005 - Device Registration](T1098.005%20-%20Device%20Registration/README.md)
- [T1098.004 - SSH Authorized Keys](T1098.004%20-%20SSH%20Authorized%20Keys/README.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Remove unnecessary and potentially abusable authentication and authorization mechanisms where possible.
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Configure access controls and firewalls to limit access to critical systems and domain controllers. Most cloud environments support separate virtual private cloud (VPC) instances that enable further segmentation of cloud systems.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Protect domain controllers by ensuring proper security configuration for critical servers to limit access by potentially unnecessary protocols and services, such as SMB file sharing.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow domain administrator accounts to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict access to potentially sensitive files that deal with authentication and/or authorization.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that low-privileged user accounts do not have permissions to modify accounts or account-related policies.

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) used the `sp_addlinkedsrvlogin` command in MS-SQL to create a link between a created account and other servers in the network.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [S0274 - Calisto](../../../Threat%20Intelligence/Software/Malware/S0274%20-%20Calisto.md) — [Calisto](https://attack.mitre.org/software/S0274) adds permissions and remote logins to all users.(Citation: Symantec Calisto July 2018) [Symantec Calisto July 2018](https://web.archive.org/web/20190111082249/https://www.symantec.com/security-center/writeup/2018-073014-2512-99?om_rssid=sr-latestthreats30days)
- [G0125 - HAFNIUM](../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has granted privileges to domain accounts and reset the password for default admin accounts.(Citation: Volexity Exchange Marauder March 2021)(Citation: Microsoft Silk Typhoon MAR 2025) [Volexity Exchange Marauder March 2021](https://www.volexity.com/blog/2021/03/02/active-exploitation-of-microsoft-exchange-zero-day-vulnerabilities/) · [Microsoft Silk Typhoon MAR 2025](https://www.microsoft.com/en-us/security/blog/2025/03/05/silk-typhoon-targeting-it-supply-chain/)
- [G0032 - Lazarus Group](../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) malware WhiskeyDelta-Two contains a function that attempts to rename the administrator’s account.(Citation: Novetta Blockbuster)(Citation: Novetta Blockbuster Destructive Malware) [Novetta Blockbuster Destructive Malware](https://web.archive.org/web/20160303200515/https:/operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf) · [Novetta Blockbuster](https://web.archive.org/web/20160226161828/https://www.operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Report.pdf)
- [S0002 - Mimikatz](../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — The [Mimikatz](https://attack.mitre.org/software/S0002) credential dumper has been extended to include Skeleton Key domain controller authentication bypass functionality. The <code>LSADUMP::ChangeNTLM</code> and <code>LSADUMP::SetNTLM</code> modules can also manipulate the password hash of an account without knowing the clear text value.(Citation: Adsecurity Mimikatz Guide)(Citation: Metcalf 2015) [Adsecurity Mimikatz Guide](https://adsecurity.org/?page_id=1821) · [Metcalf 2015](http://adsecurity.org/?p=1275)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has reset passwords of valid accounts to include domain accounts in order to obtain persistence and escalate privileges.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has reset passwords for domain controller accounts using `net.exe` through the command `net user DC-01$ P@ssw0rd`.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has also abused Resource-Based Constrained Delegation (RBCD) assignments to impersonate high-privileged users and gain unauthorized access to services and resources.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has added accounts to the ESX Admins group to grant them full admin rights in vSphere.(Citation: Mandiant VMware vSphere JUL 2025) [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [S9008 - Shai-Hulud](../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has modified GitHub account settings for private repositories and changed them to public.(Citation: Aikido Shai-Hulud September 2025)(Citation: Netskope Shai-Hulud November 2025)(Citation: Wiz Shai-Hulud September 2025)(Citation: Microsoft Shai-Hulud December 2025) [Aikido Shai-Hulud September 2025](https://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again) · [Netskope Shai-Hulud November 2025](https://www.netskope.com/blog/shai-hulud-2-0-aggressive-automated-one-of-fastest-spreading-npm-supply-chain-attacks-ever-observed) · [Wiz Shai-Hulud September 2025](https://www.wiz.io/blog/shai-hulud-npm-supply-chain-attack) · [Microsoft Shai-Hulud December 2025](https://www.microsoft.com/en-us/security/blog/2025/12/09/shai-hulud-2-0-guidance-for-detecting-investigating-and-defending-against-the-supply-chain-attack/)
- [G1056 - TeamPCP](../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has modified settings to publish private Aqua Security repositories to GitHub as public.(Citation: Aqua Security Blog Trivy Compromise APR 2026) [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know)
- [G1055 - VOID MANTICORE](../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has leveraged access to administrative control systems to achieve disruptive effects, consistent with administrative account abuse or privilege escalation within existing access.(Citation: Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026)(Citation: SEC 8K Palo Alto Statement Stryker Corp Handala March 2026) [Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026](https://dti.domaintools.com/research/handala-mois-linked-cyber-influence-ecosystem-threat-intelligence-assessment) · [SEC 8K Palo Alto Statement Stryker Corp Handala March 2026](https://www.sec.gov/Archives/edgar/data/310764/000119312526118634/d94012dex991.htm)

## Detection strategies

- [DET0096 - Account Manipulation Behavior Chain Detection](../../../Defenses/Detection%20Strategies/DET0096%20-%20Account%20Manipulation%20Behavior%20Chain%20Detection.md)

## Sources

- [FireEye SMOKEDHAM June 2021](https://www.fireeye.com/blog/threat-research/2021/06/darkside-affiliate-supply-chain-software-compromise.html)
- [Microsoft Security Event 4670](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventID=4670)
- [Microsoft User Modified Event](https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/event-4738)
- [InsiderThreat ChangeNTLM July 2017](https://blog.stealthbits.com/manipulating-user-passwords-with-mimikatz-SetNTLM-ChangeNTLM)
- [GitHub Mimikatz Issue 92 June 2017](https://github.com/gentilkiwi/mimikatz/issues/92)
