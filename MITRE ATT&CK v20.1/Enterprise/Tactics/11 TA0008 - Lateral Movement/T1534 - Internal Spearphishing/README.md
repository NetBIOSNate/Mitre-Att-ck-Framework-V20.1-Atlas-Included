# T1534 - Internal Spearphishing

[Enterprise](../../../README.md) / [Lateral Movement](../README.md)

After they already have access to accounts or systems within the environment, adversaries may use internal spearphishing to gain access to additional information or compromise other users within the same organization. Internal spearphishing is multi-staged campaign where a legitimate account is initially compromised either by controlling the user's device or by compromising the account credentials of the user. Adversaries may then attempt to take advantage of the trusted internal account to increase the likelihood of tricking more victims into falling for phish attempts, often incorporating [Impersonation](https://attack.mitre.org/techniques/T1684/001).(Citation: Trend Micro - Int SP)

For example, adversaries may leverage [Spearphishing Attachment](https://attack.mitre.org/techniques/T1566/001) or [Spearphishing Link](https://attack.mitre.org/techniques/T1566/002) as part of internal spearphishing to deliver a payload or redirect to an external site to capture credentials through [Input Capture](https://attack.mitre.org/techniques/T1056) on sites that mimic login interfaces.

Adversaries may also leverage internal chat apps, such as Microsoft Teams, to spread malicious content or engage users in attempts to capture sensitive information and/or credentials.(Citation: Int SP - chat apps)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1534)

**Tactics**  [Lateral Movement](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [G0099 - APT-C-36](../../../Threat%20Intelligence/Groups/G0099%20-%20APT-C-36.md) — [APT-C-36](https://attack.mitre.org/groups/G0099) has used a compromised account to send a phishing email to an address likely used and monitored by the IT team within the same targeted organization.(Citation: Zscaler BlindEagle DEC 2025) [Zscaler BlindEagle DEC 2025](https://www.zscaler.com/blogs/security-research/blindeagle-targets-colombian-government-agency-caminho-and-dcrat)
- [G0047 - Gamaredon Group](../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used an Outlook VBA module on infected systems to send phishing emails with malicious attachments to other employees within the organization.(Citation: ESET Gamaredon June 2020) [ESET Gamaredon June 2020](https://www.welivesecurity.com/2020/06/11/gamaredon-group-grows-its-game/)
- [G1001 - HEXANE](../../../Threat%20Intelligence/Groups/G1001%20-%20HEXANE.md) — [HEXANE](https://attack.mitre.org/groups/G1001) has conducted internal spearphishing attacks against executives, HR, and IT personnel to gain information and access.(Citation: SecureWorks August 2019) [SecureWorks August 2019](https://www.secureworks.com/blog/lyceum-takes-center-stage-in-middle-east-campaign)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has sent internal spearphishing emails for lateral movement after stealing victim information.(Citation: KISA Operation Muzabi) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf)
- [G0065 - Leviathan](../../../Threat%20Intelligence/Groups/G0065%20-%20Leviathan.md) — [Leviathan](https://attack.mitre.org/groups/G0065) has conducted internal spearphishing within the victim's environment for lateral movement.(Citation: CISA AA21-200A APT40 July 2021) [CISA AA21-200A APT40 July 2021](https://us-cert.cisa.gov/ncas/alerts/aa21-200a)
- [G0069 - MuddyWater](../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has used compromised mailboxes within target organizations to send spearphishing emails.(Citation: FalconFeeds_Iran_Mar2026) [FalconFeeds_Iran_Mar2026](https://falconfeeds.io/blogs/the-digital-redoubt-irans-national-information-network-cyber-conflict)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has conducted internal spearphishing attacks against IT staff and administrators.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [C0022 - Operation Dream Job](../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — During [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) conducted internal spearphishing from within a compromised organization.(Citation: ClearSky Lazarus Aug 2020) [ClearSky Lazarus Aug 2020](https://www.clearskysec.com/wp-content/uploads/2020/08/Dream-Job-Campaign.pdf)
- [S9030 - SameCoin](../../../Threat%20Intelligence/Software/Malware/S9030%20-%20SameCoin.md) — [SameCoin](https://attack.mitre.org/software/S9030) can send its Setup.exe file as an attachment to other addresses in the same compromised organization.(Citation: Check Point Wirte NOV 2024) [Check Point Wirte NOV 2024](https://research.checkpoint.com/2024/hamas-affiliated-threat-actor-expands-to-disruptive-activity/)

## Detection strategies

- [DET0054 - Internal Spearphishing via Trusted Accounts](../../../Defenses/Detection%20Strategies/DET0054%20-%20Internal%20Spearphishing%20via%20Trusted%20Accounts.md)

## Sources

- [Int SP - chat apps](https://www.microsoft.com/en-us/security/blog/2023/08/02/midnight-blizzard-conducts-targeted-social-engineering-over-microsoft-teams/)
- [Trend Micro - Int SP](https://www.trendmicro.com/en_us/research.html)
