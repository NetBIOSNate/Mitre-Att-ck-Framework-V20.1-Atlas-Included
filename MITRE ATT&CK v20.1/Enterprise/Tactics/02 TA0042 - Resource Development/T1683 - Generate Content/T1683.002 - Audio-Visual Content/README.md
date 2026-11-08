# T1683.002 - Audio-Visual Content

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1683 - Generate Content](../README.md)

Adversaries may create or manipulate audio, image, and video content to support targeting and malicious operations. Adversaries may also use synthetic voice recordings, real-time altered audio or video during live interactions, fabricated profile photos and identity documents, or video content depicting fabricated or impersonated individuals.(Citation: Nov AI Threat Tracker)

Content may be produced manually through editing tools, generated using AI-assisted tools, or produced using third-party synthetic services.(Citation: FBI 2025 AI Generate Content)(Citation: Europol Deepfakes) AI-assisted tools have enabled adversaries to produce synthetic media at scale and generate content that is more difficult to identify as inauthentic. 

Audio-visual content produced through these methods may be used in support of other techniques, such as [Phishing](https://attack.mitre.org/techniques/T1660), [Spearphishing via Service](https://attack.mitre.org/techniques/T1566/003), [Phishing for Information](https://attack.mitre.org/techniques/T1598), [Internal Spearphishing](https://attack.mitre.org/techniques/T1534), [Social Engineering](https://attack.mitre.org/techniques/T1684), [Financial Theft](https://attack.mitre.org/techniques/T1657), or [Establish Accounts](https://attack.mitre.org/techniques/T1585).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1683/002)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on designing defenses that are not reliant on atomic indicators.

## Procedure examples

- [G0099 - APT-C-36](../../../../Threat%20Intelligence/Groups/G0099%20-%20APT-C-36.md) — [APT-C-36](https://attack.mitre.org/groups/G0099) has used phishing pages appearing like legitimate banking login portals to compromise credentials.(Citation: LevelBlue Blind Eagle Proton66 JUN 2025) [LevelBlue Blind Eagle Proton66 JUN 2025](https://www.levelblue.com/blogs/spiderlabs-blog/tracing-blind-eagle-to-proton66/)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has created fictitious profiles on social media utilizing fake photos and personas to entice users to engage in the schemes.(Citation: Microsoft CYBERWARCON NOV 2024) [Microsoft CYBERWARCON NOV 2024](https://www.microsoft.com/en-us/security/blog/2024/11/22/microsoft-shares-latest-intelligence-on-north-korean-and-chinese-threat-actors-at-cyberwarcon/)
- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has used AI to clone video-conferencing applications to distribute their [BeaverTail](https://attack.mitre.org/software/S1246) malware. They have also used AI to create deepfake videos. (Citation: PaloAlto Unit42 ContagiousInterview BeaverTail InvisibileFerret October 2024) [PaloAlto Unit42 ContagiousInterview BeaverTail InvisibileFerret October 2024](https://unit42.paloaltonetworks.com/north-korean-threat-actors-lure-tech-job-seekers-as-fake-recruiters/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has generated fictitious job-related themed websites that entice users to interact and launch malicious actions.(Citation: CheckPoint_NimbusManticoreEurope_Sept2025)(Citation: Mandiant_UNC1549_Feb2024) [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has also utilized decoy documents and files to provide a sense of legitimacy to the user.(Citation: Mandiant_UNC1549_Feb2024) [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has leveraged fake Microsoft Outlook login windows prompts to entice victims to enter their credentials.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [CheckPoint_NimbusManticoreEurope_Sept2025](https://research.checkpoint.com/2025/nimbus-manticore-deploys-new-malware-targeting-europe/) · [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense) · [Mandiant_UNC1549_Feb2024](https://cloud.google.com/blog/topics/threat-intelligence/suspected-iranian-unc1549-targets-israel-middle-east)
- [G1058 - The Gentlemen](../../../../Threat%20Intelligence/Groups/G1058%20-%20The%20Gentlemen.md) — [The Gentlemen](https://attack.mitre.org/groups/G1058) has leveraged a branded graphic that is placed on the systems desktop wallpaper that symbolizes the association of malicious activity to the group.(Citation: MSTI_GentelmenRansomware_May2026)(Citation: CheckPointResearch_TheGentlemen_April2026)(Citation: BradyUnit42_TheGentlemen_July2026) [BradyUnit42_TheGentlemen_July2026](https://unit42.paloaltonetworks.com/the-gentlemen-ransomware/) · [CheckPointResearch_TheGentlemen_April2026](https://research.checkpoint.com/2026/dfir-report-the-gentlemen/) · [MSTI_GentelmenRansomware_May2026](https://www.microsoft.com/en-us/security/blog/2026/05/28/the-gentlemen-ransomware-dissecting-a-self-propagating-go-encryptor/)

## Detection strategies

- [DET0918 - Detection of Audio-Visual Content](../../../../Defenses/Detection%20Strategies/DET0918%20-%20Detection%20of%20Audio-Visual%20Content.md)

## Sources

- [Europol Deepfakes](https://www.europol.europa.eu/cms/sites/default/files/documents/Europol_Innovation_Lab_Facing_Reality_Law_Enforcement_And_The_Challenge_Of_Deepfakes.pdf)
- [Nov AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools)
- [FBI 2025 AI Generate Content](https://www.ic3.gov/AnnualReport/Reports/2025_IC3Report.pdf)
