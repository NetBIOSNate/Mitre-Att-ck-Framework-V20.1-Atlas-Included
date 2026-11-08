# T1591 - Gather Victim Org Information

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may gather information about the victim's organization that can be used during targeting. Information about an organization may include a variety of details, including the names of divisions/departments, specifics of business operations, as well as the roles and responsibilities of key employees.

Adversaries may gather this information in various ways, such as direct elicitation via [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about an organization may also be exposed to adversaries via online or other accessible data sets (ex: [Social Media](https://attack.mitre.org/techniques/T1593/001) or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)).(Citation: ThreatPost Broadvoice Leak)(Citation: SEC EDGAR Search) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [Phishing](https://attack.mitre.org/techniques/T1566) or [Trusted Relationship](https://attack.mitre.org/techniques/T1199)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1591)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1591.002 - Business Relationships](T1591.002%20-%20Business%20Relationships/README.md)
- [T1591.001 - Determine Physical Locations](T1591.001%20-%20Determine%20Physical%20Locations/README.md)
- [T1591.003 - Identify Business Tempo](T1591.003%20-%20Identify%20Business%20Tempo/README.md)
- [T1591.004 - Identify Roles](T1591.004%20-%20Identify%20Roles/README.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Procedure examples

- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has used large language models (LLMs) to gather information about satellite capabilities.(Citation: MSFT-AI)(Citation: OpenAI-CTI) [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/) · [OpenAI-CTI](https://openai.com/index/disrupting-malicious-uses-of-ai-by-state-affiliated-threat-actors/)
- [G0046 - FIN7](../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — [FIN7](https://attack.mitre.org/groups/G0046) has compiled a list of victims by filtering companies by revenue using Zoominfo, which is a service that provides business information.(Citation: BiZone Lizar May 2021) [BiZone Lizar May 2021](https://bi-zone.medium.com/from-pentest-to-apt-attack-cybercriminal-group-fin7-disguises-its-malware-as-an-ethical-hackers-c23c9a75e319)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has collected victim organization information including but not limited to organization hierarchy, functions, press releases, and others.(Citation: KISA Operation Muzabi) [Kimsuky](https://attack.mitre.org/groups/G0094) has also used large language models (LLMs) to gather information about potential targets of interest.(Citation: MSFT-AI) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf) · [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)
- [G0032 - Lazarus Group](../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) has studied publicly available information about a targeted organization to tailor spearphishing efforts against specific departments and/or individuals.(Citation: Kaspersky ThreatNeedle Feb 2021) [Kaspersky ThreatNeedle Feb 2021](https://securelist.com/lazarus-threatneedle/100803/)
- [G1054 - MirrorFace](../../../Threat%20Intelligence/Groups/G1054%20-%20MirrorFace.md) — [MirrorFace](https://attack.mitre.org/groups/G1054) has placed specific content in phishing emails to target members of particular political parties.(Citation: ESET MirrorFace DEC 2022) [ESET MirrorFace DEC 2022](https://www.welivesecurity.com/2022/12/14/unmasking-mirrorface-operation-liberalface-targeting-japanese-political-entities/)
- [G1036 - Moonstone Sleet](../../../Threat%20Intelligence/Groups/G1036%20-%20Moonstone%20Sleet.md) — [Moonstone Sleet](https://attack.mitre.org/groups/G1036) has gathered information on victim organizations through email and social media interaction.(Citation: Microsoft Moonstone Sleet 2024) [Microsoft Moonstone Sleet 2024](https://www.microsoft.com/en-us/security/blog/2024/05/28/moonstone-sleet-emerges-as-new-north-korean-threat-actor-with-new-bag-of-tricks/)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has gathered details on victims to ensure they target members of organizations within software or aviation.(Citation: CheckPoint_NimbusManticore_May2026) [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/)
- [C0061 - Operation Digital Eye](../../../Threat%20Intelligence/Campaigns/C0061%20-%20Operation%20Digital%20Eye.md) — During [Operation Digital Eye](https://attack.mitre.org/campaigns/C0061), threat actors concealed malicious activity by using terms that aligned with the technological context of the targeted organization.(Citation: sentinelone operationDigitalEye Dec 2024) [sentinelone operationDigitalEye Dec 2024](https://www.sentinelone.com/labs/operation-digital-eye-chinese-apt-compromises-critical-digital-infrastructure-via-visual-studio-code-tunnels/)
- [C0022 - Operation Dream Job](../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — For [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) gathered victim organization information to identify specific targets.(Citation: ClearSky Lazarus Aug 2020) [ClearSky Lazarus Aug 2020](https://www.clearskysec.com/wp-content/uploads/2020/08/Dream-Job-Campaign.pdf)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has conducted extensive reconnaissance pre-compromise to gain information about the targeted organization.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0890 - Detection of Gather Victim Org Information](../../../Defenses/Detection%20Strategies/DET0890%20-%20Detection%20of%20Gather%20Victim%20Org%20Information.md)

## Sources

- [ThreatPost Broadvoice Leak](https://threatpost.com/broadvoice-leaks-350m-records-voicemail-transcripts/160158/)
- [SEC EDGAR Search](https://www.sec.gov/edgar/search/)
