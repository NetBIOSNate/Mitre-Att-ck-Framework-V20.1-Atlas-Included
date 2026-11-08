# T1587 - Develop Capabilities

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may build capabilities that can be used during targeting. Rather than purchasing, freely downloading, or stealing capabilities, adversaries may develop their own capabilities in-house. This is the process of identifying development requirements and building solutions such as malware, exploits, and self-signed certificates. Adversaries may develop capabilities to support their operations throughout numerous phases of the adversary lifecycle.(Citation: Mandiant APT1)(Citation: Kaspersky Sofacy)(Citation: Bitdefender StrongPity June 2020)(Citation: Talos Promethium June 2020)

As with legitimate development efforts, different skill sets may be required for developing capabilities. The skills needed may be located in-house, or may need to be contracted out. Use of a contractor may be considered an extension of that adversary's development capabilities, provided the adversary plays a role in shaping requirements and maintains a degree of exclusivity to the capability. Adversaries may also employ the use of [Artificial Intelligence](https://attack.mitre.org/techniques/T1588/007) for development.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1587)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1587.002 - Code Signing Certificates](T1587.002%20-%20Code%20Signing%20Certificates/README.md)
- [T1587.003 - Digital Certificates](T1587.003%20-%20Digital%20Certificates/README.md)
- [T1587.004 - Exploits](T1587.004%20-%20Exploits/README.md)
- [T1587.001 - Malware](T1587.001%20-%20Malware/README.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary utilized and ingested into the LLM a pre-written document that consisted of techniques and procedures to utilize when set variables and conditions were encountered.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G1052 - Contagious Interview](../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) developed malicious NPM packages for delivery to or retrieval by victims.(Citation: Sentinel One Contagious Interview ClickFix September 2025)(Citation: Validin Contagious Interview North Korea ClickFix January 2025)(Citation: Esentire ContagiousInterview BeaverTail InvisibleFerret November 2024)(Citation: Socket Contagious Interview NPM April 2025)(Citation: Socket BeaverTail XORIndex HexEval Contagious Interview July 2025)(Citation: Socket HexEval BeaverTail Contagious Interview June 2025)(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/) · [Validin Contagious Interview North Korea ClickFix January 2025](https://www.validin.com/blog/inoculating_contagious_interview_with_validin/) · [Esentire ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.esentire.com/blog/bored-beavertail-invisibleferret-yacht-club-a-lazarus-lure-pt-2) · [Socket Contagious Interview NPM April 2025](https://socket.dev/blog/lazarus-expands-malicious-npm-campaign-11-new-packages-add-malware-loaders-and-bitbucket) · [Socket BeaverTail XORIndex HexEval Contagious Interview July 2025](https://socket.dev/blog/contagious-interview-campaign-escalates-67-malicious-npm-packages) · [Socket HexEval BeaverTail Contagious Interview June 2025](https://socket.dev/blog/north-korean-contagious-interview-campaign-drops-35-new-malicious-npm-packages) · [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) created and used a mailing toolkit to use in spearphishing attacks.(Citation: VirusBulletin Kimsuky October 2019) [VirusBulletin Kimsuky October 2019](https://www.virusbulletin.com/virusbulletin/2020/03/vb2019-paper-kimsuky-group-tracking-king-spearphishing/)
- [G1036 - Moonstone Sleet](../../../Threat%20Intelligence/Groups/G1036%20-%20Moonstone%20Sleet.md) — [Moonstone Sleet](https://attack.mitre.org/groups/G1036) developed malicious npm packages for delivery to or retrieval by victims.(Citation: Microsoft Moonstone Sleet 2024) [Microsoft Moonstone Sleet 2024](https://www.microsoft.com/en-us/security/blog/2024/05/28/moonstone-sleet-emerges-as-new-north-korean-threat-actor-with-new-bag-of-tricks/)
- [G1045 - Salt Typhoon](../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has hosted and attended formal training programs for foreign-made IT products to include Cisco Network Academy.(Citation: CarySentinelLabs_CiscoSaltTyphoon_Dec2025) [CarySentinelLabs_CiscoSaltTyphoon_Dec2025](https://www.sentinelone.com/labs/malicious-apprentice-how-two-hackers-went-from-cisco-academy-to-cisco-cves/)

## Detection strategies

- [DET0853 - Detection of Develop Capabilities](../../../Defenses/Detection%20Strategies/DET0853%20-%20Detection%20of%20Develop%20Capabilities.md)

## Sources

- [Kaspersky Sofacy](https://securelist.com/sofacy-apt-hits-high-profile-targets-with-updated-toolset/72924/)
- [Mandiant APT1](https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf)
- [Talos Promethium June 2020](https://blog.talosintelligence.com/2020/06/promethium-extends-with-strongpity3.html)
- [Bitdefender StrongPity June 2020](https://www.bitdefender.com/files/News/CaseStudies/study/353/Bitdefender-Whitepaper-StrongPity-APT.pdf)
