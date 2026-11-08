# T1213.002 - Sharepoint

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1213 - Data from Information Repositories](../README.md)

Adversaries may leverage the SharePoint repository as a source to mine valuable information.(Citation: Information architecture guidance for SharePoint Online portals) SharePoint will often contain useful information for an adversary to learn about the structure and functionality of the internal network and systems. For example, the following is a list of example information that may hold potential value to an adversary and may also be found on SharePoint:

* Policies, procedures, and standards
* Physical / logical network diagrams
* System architecture diagrams
* Technical system documentation
* Testing / development credentials (i.e., [Unsecured Credentials](https://attack.mitre.org/techniques/T1552))
* Work / project schedules
* Source code snippets
* Links to network shares and other internal resources

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1213/002)

**Tactics**  [Collection](../../README.md)

**Platforms**  [Office Suite](../../../../Platforms/Office%20Suite.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1024 - Akira](../../../../Threat%20Intelligence/Groups/G1024%20-%20Akira.md) — [Akira](https://attack.mitre.org/groups/G1024) has accessed and downloaded information stored in SharePoint instances as part of data gathering and exfiltration activity.(Citation: Secureworks GOLD SAHARA) [Secureworks GOLD SAHARA](https://www.secureworks.com/research/threat-profiles/gold-sahara)
- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has collected information from Microsoft SharePoint services within target networks.(Citation: RSAC 2015 Abu Dhabi Stefano Maccaglia) [RSAC 2015 Abu Dhabi Stefano Maccaglia](https://paper.seebug.org/papers/APT/APT_CyberCriminal_Campagin/2015/2015.11.04_Evolving_Threats/cct-w08_evolving-threats-dissection-of-a-cyber-espionage-attack.pdf)
- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) accessed victim SharePoint environments to search for VPN and MFA enrollment information, help desk instructions, and new hire guides.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G0114 - Chimera](../../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has collected documents from the victim's SharePoint.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [G0125 - HAFNIUM](../../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has abused compromised credentials to exfiltrate data from SharePoint.(Citation: Microsoft Silk Typhoon MAR 2025) [Microsoft Silk Typhoon MAR 2025](https://www.microsoft.com/en-us/security/blog/2025/03/05/silk-typhoon-targeting-it-supply-chain/)
- [G0004 - Ke3chang](../../../../Threat%20Intelligence/Groups/G0004%20-%20Ke3chang.md) — [Ke3chang](https://attack.mitre.org/groups/G0004) used a SharePoint enumeration and data dumping tool known as spwebmember.(Citation: NCC Group APT15 Alive and Strong) [NCC Group APT15 Alive and Strong](https://research.nccgroup.com/2018/03/10/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has searched a victim's network for collaboration platforms like SharePoint to discover further high-privilege account credentials.(Citation: MSTIC DEV-0537 Mar 2022)(Citation: NCC Group LAPSUS Apr 2022) [NCC Group LAPSUS Apr 2022](https://www.nccgroup.com/research-blog/lapsus-recent-techniques-tactics-and-procedures/) · [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has downloaded files from SharePoint services.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [S0227 - spwebmember](../../../../Threat%20Intelligence/Software/Tools/S0227%20-%20spwebmember.md) — [spwebmember](https://attack.mitre.org/software/S0227) is used to enumerate and dump information from Microsoft SharePoint.(Citation: NCC Group APT15 Alive and Strong) [NCC Group APT15 Alive and Strong](https://research.nccgroup.com/2018/03/10/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/)
- [S9009 - TruffleHog](../../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) has searched SharePoint for data and credentials.(Citation: Github TruffleSecurity Trufflehog April 2025) [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)
- [G1055 - VOID MANTICORE](../../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has accessed victim’s public facing SharePoint servers and exfiltrated data.(Citation: DOJ FBI Handala Hack March 2026) [DOJ FBI Handala Hack March 2026](https://www.justice.gov/opa/media/1431956/dl?inline)

## Detection strategies

- [DET0500 - Detecting Abnormal SharePoint Data Mining by Privileged or Rare Users](../../../../Defenses/Detection%20Strategies/DET0500%20-%20Detecting%20Abnormal%20SharePoint%20Data%20Mining%20by%20Privileged%20or%20Rare%20Users.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Consider periodic review of accounts and privileges for critical and sensitive SharePoint repositories.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least-privilege. Consider implementing access control mechanisms that include both authentication and authorization.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored in SharePoint repositories.

## Sources

- [Information architecture guidance for SharePoint Online portals](https://learn.microsoft.com/en-us/sharepoint/dev/solution-guidance/portal-information-architecture)
