# T1593 - Search Open Websites/Domains

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may search freely available websites and/or domains for information about victims that can be used during targeting. Information about victims may be available in various online sites, such as social media, news sites, or those hosting information about business operations such as hiring or requested/rewarded contracts.(Citation: Cyware Social Media)(Citation: SecurityTrails Google Hacking)(Citation: ExploitDB GoogleHacking)

Adversaries may search in different online sites depending on what information they seek to gather. Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133) or [Phishing](https://attack.mitre.org/techniques/T1566)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1593)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1593.003 - Code Repositories](T1593.003%20-%20Code%20Repositories/README.md)
- [T1593.002 - Search Engines](T1593.002%20-%20Search%20Engines/README.md)
- [T1593.001 - Social Media](T1593.001%20-%20Social%20Media/README.md)

## Detection strategies

- [DET0856 - Detection of Search Open Websites/Domains](../../../Defenses/Detection%20Strategies/DET0856%20-%20Detection%20of%20Search%20Open%20Websites%20-%20Domains.md)

## Procedure examples

- [G0099 - APT-C-36](../../../Threat%20Intelligence/Groups/G0099%20-%20APT-C-36.md) — [APT-C-36](https://attack.mitre.org/groups/G0099) has gathered information on Colombian financial institutions, including Bancolombia, BBVA, Banco Caja Social, and Davivienda to craft phishing pages.(Citation: LevelBlue Blind Eagle Proton66 JUN 2025) [LevelBlue Blind Eagle Proton66 JUN 2025](https://www.levelblue.com/blogs/spiderlabs-blog/tracing-blind-eagle-to-proton66/)
- [G1052 - Contagious Interview](../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has utilized open-source indicator of compromise repositories to determine their exposure to include VirusTotal, and MalTrail.(Citation: Sentinel One Contagious Interview ClickFix September 2025) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/)
- [G0129 - Mustang Panda](../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used open-source research to identify information about victims to use in targeting to include creating weaponized phishing lures and attachments.(Citation: IBM MUSTANG PANDA PUBLOAD CLAIMLOADER JUNE 2025)(Citation: 2025_IBM_PUBLOAD_TONESHELL_HIUPAN_CLAIMLOADER_MUSTANG PANDA) [IBM MUSTANG PANDA PUBLOAD CLAIMLOADER JUNE 2025](https://www.ibm.com/think/x-force/hive0154-mustang-panda-shifts-focus-tibetan-community-deploy-pubload-backdoor) · [2025_IBM_PUBLOAD_TONESHELL_HIUPAN_CLAIMLOADER_MUSTANG PANDA](https://www.ibm.com/think/x-force/hive0154-targeting-us-philippines-pakistan-taiwan)
- [G0034 - Sandworm Team](../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) researched Ukraine's unique legal entity identifier (called an "EDRPOU" number), including running queries on the EDRPOU website, in preparation for the [NotPetya](https://attack.mitre.org/software/S0368) attack. [Sandworm Team](https://attack.mitre.org/groups/G0034) has also researched third-party websites to help it craft credible spearphishing emails.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)
- [G1033 - Star Blizzard](../../../Threat%20Intelligence/Groups/G1033%20-%20Star%20Blizzard.md) — [Star Blizzard](https://attack.mitre.org/groups/G1033) has used open-source research to identify information about victims to use in targeting.(Citation: Microsoft Star Blizzard August 2022)(Citation: CISA Star Blizzard Advisory December 2023) [CISA Star Blizzard Advisory December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-341a) · [Microsoft Star Blizzard August 2022](https://www.microsoft.com/en-us/security/blog/2022/08/15/disrupting-seaborgiums-ongoing-phishing-operations/)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has conducted pre-compromise web searches for victim information.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1013 - Application Developer Guidance](../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Application developers uploading to public code repositories should be careful to avoid publishing sensitive information such as credentials and API keys.
- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Scan public code repositories for exposed credentials or other sensitive information before making commits. Ensure that any leaked credentials are removed from the commit history, not just the current latest version of the code.

## Sources

- [SecurityTrails Google Hacking](https://www.recordedfuture.com/threat-intelligence-101/threat-analysis-techniques/google-dorks)
- [Cyware Social Media](https://cyware.com/news/how-hackers-exploit-social-media-to-break-into-your-company-88e8da8e)
- [ExploitDB GoogleHacking](https://www.exploit-db.com/google-hacking-database)
