# T1074.002 - Remote Data Staging

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1074 - Data Staged](../README.md)

Adversaries may stage data collected from multiple systems in a central location or directory on one system prior to Exfiltration. Data may be kept in separate files or combined into one file through techniques such as [Archive Collected Data](https://attack.mitre.org/techniques/T1560). Interactive command shells may be used, and common functionality within [cmd](https://attack.mitre.org/software/S0106) and bash may be used to copy data into a staging location.

In cloud environments, adversaries may stage data within a particular instance or virtual machine before exfiltration. An adversary may [Create Cloud Instance](https://attack.mitre.org/techniques/T1578/002) and stage data in that instance.(Citation: Mandiant M-Trends 2020)

By staging data on one system prior to Exfiltration, adversaries can minimize the number of connections made to their C2 server and better evade detection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1074/002)

**Tactics**  [Collection](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has staged archives of collected data on a target's Outlook Web Access (OWA) server.(Citation: Cybersecurity Advisory GRU Brute Force Campaign July 2021) [Cybersecurity Advisory GRU Brute Force Campaign July 2021](https://media.defense.gov/2021/Jul/01/2002753896/-1/-1/1/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21.PDF)
- [S1043 - ccf32](../../../../Threat%20Intelligence/Software/Malware/S1043%20-%20ccf32.md) — [ccf32](https://attack.mitre.org/software/S1043) has copied files to a remote machine infected with [Chinoxy](https://attack.mitre.org/software/S1041) or another backdoor.(Citation: Bitdefender FunnyDream Campaign November 2020) [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
- [G0114 - Chimera](../../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has staged stolen data on designated servers in the target environment.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [G0037 - FIN6](../../../../Threat%20Intelligence/Groups/G0037%20-%20FIN6.md) — [FIN6](https://attack.mitre.org/groups/G0037) actors have compressed data from remote systems and moved it to another staging system before exfiltration.(Citation: FireEye FIN6 April 2016) [FireEye FIN6 April 2016](https://web.archive.org/web/20190807112824/https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf)
- [G0061 - FIN8](../../../../Threat%20Intelligence/Groups/G0061%20-%20FIN8.md) — [FIN8](https://attack.mitre.org/groups/G0061) aggregates staged data from a network into a single location.(Citation: FireEye Know Your Enemy FIN8 Aug 2016) [FireEye Know Your Enemy FIN8 Aug 2016](https://www2.fireeye.com/WBNR-Know-Your-Enemy-UNC622-Spear-Phishing.html)
- [G0065 - Leviathan](../../../../Threat%20Intelligence/Groups/G0065%20-%20Leviathan.md) — [Leviathan](https://attack.mitre.org/groups/G0065) has staged data remotely prior to exfiltration.(Citation: CISA AA21-200A APT40 July 2021) [CISA AA21-200A APT40 July 2021](https://us-cert.cisa.gov/ncas/alerts/aa21-200a)
- [G0045 - menuPass](../../../../Threat%20Intelligence/Groups/G0045%20-%20menuPass.md) — [menuPass](https://attack.mitre.org/groups/G0045) has staged data on remote MSP systems or other victim networks prior to exfiltration.(Citation: PWC Cloud Hopper April 2017)(Citation: Symantec Cicada November 2020) [PWC Cloud Hopper April 2017](https://web.archive.org/web/20220224041316/https:/www.pwc.co.uk/cyber-security/pdf/cloud-hopper-report-final-v4.pdf) · [Symantec Cicada November 2020](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/cicada-apt10-japan-espionage)
- [G1054 - MirrorFace](../../../../Threat%20Intelligence/Groups/G1054%20-%20MirrorFace.md) — [MirrorFace](https://attack.mitre.org/groups/G1054) has gathered data and files of interest on a single victim machine.(Citation: Trend Micro Earth Kasha NOV 2024) [Trend Micro Earth Kasha NOV 2024](https://www.trendmicro.com/en_us/research/24/k/lodeinfo-campaign-of-earth-kasha.html)
- [G1019 - MoustachedBouncer](../../../../Threat%20Intelligence/Groups/G1019%20-%20MoustachedBouncer.md) — [MoustachedBouncer](https://attack.mitre.org/groups/G1019) has used plugins to save captured screenshots to `.\AActdata\` on an SMB share.(Citation: MoustachedBouncer ESET August 2023) [MoustachedBouncer ESET August 2023](https://www.welivesecurity.com/en/eset-research/moustachedbouncer-espionage-against-foreign-diplomats-in-belarus/)
- [C0002 - Night Dragon](../../../../Threat%20Intelligence/Campaigns/C0002%20-%20Night%20Dragon.md) — During [Night Dragon](https://attack.mitre.org/campaigns/C0002), threat actors copied files to company web servers and subsequently downloaded them.(Citation: McAfee Night Dragon) [McAfee Night Dragon](https://scadahacker.com/library/Documents/Cyber_Events/McAfee%20-%20Night%20Dragon%20-%20Global%20Energy%20Cyberattacks.pdf)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) staged collected email archives in the public web directory of a website that was accessible from the internet.(Citation: Hunt Sea Turtle 2024) [Hunt Sea Turtle 2024](https://www.huntandhackett.com/blog/turkish-espionage-campaigns)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) staged data and files in password-protected archives on a victim's OWA server.(Citation: Volexity SolarWinds) [Volexity SolarWinds](https://www.volexity.com/blog/2020/12/14/dark-halo-leverages-solarwinds-compromise-to-breach-organizations/)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has moved staged encrypted archives to Internet-facing servers that had previously been compromised with [China Chopper](https://attack.mitre.org/software/S0020) prior to exfiltration.(Citation: SecureWorks BRONZE UNION June 2017) [SecureWorks BRONZE UNION June 2017](https://www.secureworks.com/research/bronze-union)
- [G1022 - ToddyCat](../../../../Threat%20Intelligence/Groups/G1022%20-%20ToddyCat.md) — [ToddyCat](https://attack.mitre.org/groups/G1022) manually transferred collected files to an exfiltration host using xcopy.(Citation: Kaspersky ToddyCat Check Logs October 2023) [Kaspersky ToddyCat Check Logs October 2023](https://securelist.com/toddycat-keep-calm-and-check-logs/110696/)

## Detection strategies

- [DET0071 - Detection of Remote Data Staging Prior to Exfiltration](../../../../Defenses/Detection%20Strategies/DET0071%20-%20Detection%20of%20Remote%20Data%20Staging%20Prior%20to%20Exfiltration.md)

## Sources

- [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)
