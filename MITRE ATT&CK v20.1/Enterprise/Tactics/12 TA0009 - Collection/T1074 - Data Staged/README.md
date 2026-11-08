# T1074 - Data Staged

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may stage collected data in a central location or directory prior to Exfiltration. Data may be kept in separate files or combined into one file through techniques such as [Archive Collected Data](https://attack.mitre.org/techniques/T1560). Interactive command shells may be used, and common functionality within [cmd](https://attack.mitre.org/software/S0106) and bash may be used to copy data into a staging location.(Citation: PWC Cloud Hopper April 2017)

In cloud environments, adversaries may stage data within a particular instance or virtual machine before exfiltration. An adversary may [Create Cloud Instance](https://attack.mitre.org/techniques/T1578/002) and stage data in that instance.(Citation: Mandiant M-Trends 2020)

Adversaries may choose to stage data from a victim network in a centralized location prior to Exfiltration to minimize the number of connections made to their C2 server and better evade detection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1074)

**Tactics**  [Collection](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1074.001 - Local Data Staging](T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1074.002 - Remote Data Staging](T1074.002%20-%20Remote%20Data%20Staging/README.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary had Claude Code document select findings in the skills Markdown (MD) file for future recollection.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G1032 - INC Ransom](../../../Threat%20Intelligence/Groups/G1032%20-%20INC%20Ransom.md) — [INC Ransom](https://attack.mitre.org/groups/G1032) has staged data on compromised hosts prior to exfiltration.(Citation: Huntress INC Ransom Group August 2023)(Citation: SOCRadar INC Ransom January 2024) [SOCRadar INC Ransom January 2024](https://socradar.io/dark-web-profile-inc-ransom/) · [Huntress INC Ransom Group August 2023](https://www.huntress.com/blog/investigating-new-inc-ransom-group-activity)
- [S1020 - Kevin](../../../Threat%20Intelligence/Software/Malware/S1020%20-%20Kevin.md) — [Kevin](https://attack.mitre.org/software/S1020) can create directories to store logs and other collected data.(Citation: Kaspersky Lyceum October 2021) [Kaspersky Lyceum October 2021](https://vblocalhost.com/uploads/VB2021-Kayal-etal.pdf)
- [S0641 - Kobalos](../../../Threat%20Intelligence/Software/Malware/S0641%20-%20Kobalos.md) — [Kobalos](https://attack.mitre.org/software/S0641) can write captured SSH connection credentials to a file under the <code>/var/run</code> directory with a <code>.pid</code> extension for exfiltration.(Citation: ESET Kobalos Jan 2021) [ESET Kobalos Jan 2021](https://www.welivesecurity.com/wp-content/uploads/2021/01/ESET_Kobalos.pdf)
- [S1076 - QUIETCANARY](../../../Threat%20Intelligence/Software/Malware/S1076%20-%20QUIETCANARY.md) — [QUIETCANARY](https://attack.mitre.org/software/S1076) has the ability to stage data prior to exfiltration.(Citation: Mandiant Suspected Turla Campaign February 2023) [Mandiant Suspected Turla Campaign February 2023](https://www.mandiant.com/resources/blog/turla-galaxy-opportunity)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) stages data in a centralized database prior to exfiltration.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [S1019 - Shark](../../../Threat%20Intelligence/Software/Malware/S1019%20-%20Shark.md) — [Shark](https://attack.mitre.org/software/S1019) has stored information in folders named `U1` and `U2` prior to exfiltration.(Citation: ClearSky Siamesekitten August 2021) [ClearSky Siamesekitten August 2021](https://www.clearskysec.com/siamesekitten/)
- [G1055 - VOID MANTICORE](../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has staged compressed files in specified locations prior to exfiltration over C2.(Citation: FBI IC3 Flash VOID MANTICORE Handala Hack March 2026) [FBI IC3 Flash VOID MANTICORE Handala Hack March 2026](https://www.ic3.gov/CSA/2026/260320.pdf)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has staged collected data in password-protected archives.(Citation: Microsoft Volt Typhoon May 2023) [Microsoft Volt Typhoon May 2023](https://www.microsoft.com/en-us/security/blog/2023/05/24/volt-typhoon-targets-us-critical-infrastructure-with-living-off-the-land-techniques/)
- [G0102 - Wizard Spider](../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has collected and staged credentials and network enumeration information, using the networkdll and psfin [TrickBot](https://attack.mitre.org/software/S0266) modules.(Citation: CrowdStrike Grim Spider May 2019) [CrowdStrike Grim Spider May 2019](https://www.crowdstrike.com/blog/timelining-grim-spiders-big-game-hunting-tactics/)

## Detection strategies

- [DET0014 - Detection of Data Staging Prior to Exfiltration](../../../Defenses/Detection%20Strategies/DET0014%20-%20Detection%20of%20Data%20Staging%20Prior%20to%20Exfiltration.md)

## Sources

- [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)
- [PWC Cloud Hopper April 2017](https://web.archive.org/web/20220224041316/https:/www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf)
