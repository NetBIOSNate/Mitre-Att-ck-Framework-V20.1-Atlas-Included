# T1039 - Data from Network Shared Drive

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may search network shares on computers they have compromised to find files of interest. Sensitive data can be collected from remote systems via shared network drives (host shared directory, network file server, etc.) that are accessible from the current system prior to Exfiltration. Interactive command shells may be in use, and common functionality within [cmd](https://attack.mitre.org/software/S0106) may be used to gather information.(Citation: Net Use)(Citation: Cybersecurity Advisory GRU Brute Force Campaign July 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1039)

**Tactics**  [Collection](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has collected files from network shared drives.(Citation: Cybersecurity Advisory GRU Brute Force Campaign July 2021) [Cybersecurity Advisory GRU Brute Force Campaign July 2021](https://media.defense.gov/2021/Jul/01/2002753896/-1/-1/1/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21.PDF)
- [S0128 - BADNEWS](../../../Threat%20Intelligence/Software/Malware/S0128%20-%20BADNEWS.md) — When it first starts, [BADNEWS](https://attack.mitre.org/software/S0128) crawls the victim's mapped drives and collects documents with the following extensions: .doc, .docx, .pdf, .ppt, .pptx, and .txt.(Citation: Forcepoint Monsoon) [Forcepoint Monsoon](https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf)
- [G0060 - BRONZE BUTLER](../../../Threat%20Intelligence/Groups/G0060%20-%20BRONZE%20BUTLER.md) — [BRONZE BUTLER](https://attack.mitre.org/groups/G0060) has exfiltrated files stolen from file shares.(Citation: Secureworks BRONZE BUTLER Oct 2017) [Secureworks BRONZE BUTLER Oct 2017](https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses)
- [C0015 - C0015](../../../Threat%20Intelligence/Campaigns/C0015%20-%20C0015.md) — During [C0015](https://attack.mitre.org/campaigns/C0015), the threat actors collected files from network shared drives prior to network encryption.(Citation: DFIR Conti Bazar Nov 2021) [DFIR Conti Bazar Nov 2021](https://thedfirreport.com/2021/11/29/continuing-the-bazar-ransomware-story/)
- [G0114 - Chimera](../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has collected data of interest from network shares.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [S0050 - CosmicDuke](../../../Threat%20Intelligence/Software/Malware/S0050%20-%20CosmicDuke.md) — [CosmicDuke](https://attack.mitre.org/software/S0050) steals user files from network shared drives with file extensions and keywords that match a predefined list.(Citation: F-Secure Cosmicduke) [F-Secure Cosmicduke](https://blog.f-secure.com/wp-content/uploads/2019/10/CosmicDuke.pdf)
- [S0554 - Egregor](../../../Threat%20Intelligence/Software/Malware/S0554%20-%20Egregor.md) — [Egregor](https://attack.mitre.org/software/S0554) can collect any files found in the enumerated drivers before sending it to its C2 channel.(Citation: NHS Digital Egregor Nov 2020) [NHS Digital Egregor Nov 2020](https://digital.nhs.uk/cyber-alerts/2020/cc-3681#summary)
- [G0117 - Fox Kitten](../../../Threat%20Intelligence/Groups/G0117%20-%20Fox%20Kitten.md) — [Fox Kitten](https://attack.mitre.org/groups/G0117) has searched network shares to access sensitive documents.(Citation: CISA AA20-259A Iran-Based Actor September 2020) [CISA AA20-259A Iran-Based Actor September 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-259a)
- [G0047 - Gamaredon Group](../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) malware has collected Microsoft Office documents from mapped network drives.(Citation: ESET Gamaredon June 2020)(Citation: ESET Gamaredon Sept2024) [ESET Gamaredon June 2020](https://www.welivesecurity.com/2020/06/11/gamaredon-group-grows-its-game/) · [ESET Gamaredon Sept2024](https://web-assets.esetstatic.com/wls/en/papers/white-papers/cyberespionage-gamaredon-way.pdf)
- [G0045 - menuPass](../../../Threat%20Intelligence/Groups/G0045%20-%20menuPass.md) — [menuPass](https://attack.mitre.org/groups/G0045) has collected data from remote systems by mounting network shares with <code>net use</code> and using Robocopy to transfer data.(Citation: PWC Cloud Hopper April 2017) [PWC Cloud Hopper April 2017](https://web.archive.org/web/20220224041316/https:/www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has collected data from SMB shares within the victim network.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [S0458 - Ramsay](../../../Threat%20Intelligence/Software/Malware/S0458%20-%20Ramsay.md) — [Ramsay](https://attack.mitre.org/software/S0458) can collect data from network drives and stage it for exfiltration.(Citation: Eset Ramsay May 2020) [Eset Ramsay May 2020](https://www.welivesecurity.com/2020/05/13/ramsay-cyberespionage-toolkit-airgapped-networks/)
- [G1039 - RedCurl](../../../Threat%20Intelligence/Groups/G1039%20-%20RedCurl.md) — [RedCurl](https://attack.mitre.org/groups/G1039) has collected data about network drives.(Citation: group-ib_redcurl1)(Citation: group-ib_redcurl2) [group-ib_redcurl1](https://www.group-ib.com/resources/research-hub/red-curl/) · [group-ib_redcurl2](https://www.group-ib.com/resources/research-hub/red-curl-2/)
- [G0054 - Sowbug](../../../Threat%20Intelligence/Groups/G0054%20-%20Sowbug.md) — [Sowbug](https://attack.mitre.org/groups/G0054) extracted Word documents from a file server on a victim network.(Citation: Symantec Sowbug Nov 2017) [Symantec Sowbug Nov 2017](https://www.symantec.com/connect/blogs/sowbug-cyber-espionage-group-targets-south-american-and-southeast-asian-governments)

## Detection strategies

- [DET0410 - Detection Strategy for Data from Network Shared Drive](../../../Defenses/Detection%20Strategies/DET0410%20-%20Detection%20Strategy%20for%20Data%20from%20Network%20Shared%20Drive.md)

## Sources

- [Net Use](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/gg651155%28v=ws.11%29)
- [Cybersecurity Advisory GRU Brute Force Campaign July 2021](https://media.defense.gov/2021/Jul/01/2002753896/-1/-1/1/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21.PDF)
