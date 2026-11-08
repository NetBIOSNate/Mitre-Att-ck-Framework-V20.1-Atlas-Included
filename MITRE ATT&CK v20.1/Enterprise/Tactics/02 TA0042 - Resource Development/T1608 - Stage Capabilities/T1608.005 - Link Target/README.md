# T1608.005 - Link Target

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1608 - Stage Capabilities](../README.md)

Adversaries may put in place resources that are referenced by a link that can be used during targeting. An adversary may rely upon a user clicking a malicious link in order to divulge information (including credentials) or to gain execution, as in [Malicious Link](https://attack.mitre.org/techniques/T1204/001). Links can be used for spearphishing, such as sending an email accompanied by social engineering text to coax the user to actively click or copy and paste a URL into a browser. Prior to a phish for information (as in [Spearphishing Link](https://attack.mitre.org/techniques/T1598/003)) or a phish to gain initial access to a system (as in [Spearphishing Link](https://attack.mitre.org/techniques/T1566/002)), an adversary must set up the resources for a link target for the spearphishing link. 

Typically, the resources for a link target will be an HTML page that may include some client-side script such as [JavaScript](https://attack.mitre.org/techniques/T1059/007) to decide what content to serve to the user. Adversaries may clone legitimate sites to serve as the link target, this can include cloning of login pages of legitimate web services or organization login pages in an effort to harvest credentials during [Spearphishing Link](https://attack.mitre.org/techniques/T1598/003).(Citation: Malwarebytes Silent Librarian October 2020)(Citation: Proofpoint TA407 September 2019) Adversaries may also [Upload Malware](https://attack.mitre.org/techniques/T1608/001) and have the link target point to malware for download/execution by the user.

Adversaries may purchase domains similar to legitimate domains (ex: homoglyphs, typosquatting, different top-level domain, etc.) during acquisition of infrastructure ([Domains](https://attack.mitre.org/techniques/T1583/001)) to help facilitate [Malicious Link](https://attack.mitre.org/techniques/T1204/001).

Links can be written by adversaries to mask the true destination in order to deceive victims by abusing the URL schema and increasing the effectiveness of phishing.(Citation: Kaspersky-masking)(Citation: mandiant-masking)

Adversaries may also use free or paid accounts on link shortening services and Platform-as-a-Service providers to host link targets while taking advantage of the widely trusted domains of those providers to avoid being blocked while redirecting victims to malicious pages.(Citation: Netskope GCP Redirection)(Citation: Netskope Cloud Phishing)(Citation: Intezer App Service Phishing)(Citation: Cofense-redirect) In addition, adversaries may serve a variety of malicious links through uniquely generated URIs/URLs (including one-time, single use links).(Citation: iOS URL Scheme)(Citation: URI)(Citation: URI Use)(Citation: URI Unique) Finally, adversaries may take advantage of the decentralized nature of the InterPlanetary File System (IPFS) to host link targets that are difficult to remove.(Citation: Talos IPFS 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1608/005)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0046 - FIN7](../../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — [FIN7](https://attack.mitre.org/groups/G0046) has created a fake link that redirected to an adversary-controlled Dropbox that downloaded the malicious executable.(Citation: BlackBerry_FIN7_April2024) [BlackBerry_FIN7_April2024](https://blogs.blackberry.com/en/2024/04/fin7-targets-the-united-states-automotive-industry)
- [G1014 - LuminousMoth](../../../../Threat%20Intelligence/Groups/G1014%20-%20LuminousMoth.md) — [LuminousMoth](https://attack.mitre.org/groups/G1014) has created a link to a Dropbox file that has been used in their spear-phishing operations.(Citation: Kaspersky LuminousMoth July 2021) [Kaspersky LuminousMoth July 2021](https://securelist.com/apt-luminousmoth/103332/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) had registered domains that would point to a typo-squatted domain used to deliver malicious payloads.(Citation: CheckPoint_NimbusManticore_May2026) [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has also pre-shared credentials with a link to spoofed phishing login pages that enable the download of malicious payloads when authorized credentials are used.(Citation: CheckPoint_NimbusManticoreEurope_Sept2025)(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [CheckPoint_NimbusManticoreEurope_Sept2025](https://research.checkpoint.com/2025/nimbus-manticore-deploys-new-malware-targeting-europe/) · [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/) · [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [C0060 - Operation AkaiRyū](../../../../Threat%20Intelligence/Campaigns/C0060%20-%20Operation%20AkaiRy%C5%AB.md) — During [Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060), [MirrorFace](https://attack.mitre.org/groups/G1054) used links to direct victims to malicious files hosted on OneDrive.(Citation: Trend Micro Earth Kasha Anel NOV 2024)(Citation: ESET MirrorFace 2025) [ESET MirrorFace 2025](https://www.welivesecurity.com/en/eset-research/operation-akairyu-mirrorface-invites-europe-expo-2025-revives-anel-backdoor/) · [Trend Micro Earth Kasha Anel NOV 2024](https://www.trendmicro.com/en_us/research/24/k/return-of-anel-in-the-recent-earth-kasha-spearphishing-campaign.html)
- [C0059 - Salesforce Data Exfiltration](../../../../Threat%20Intelligence/Campaigns/C0059%20-%20Salesforce%20Data%20Exfiltration.md) — During [Salesforce Data Exfiltration](https://attack.mitre.org/campaigns/C0059), threat actors established an Okta phishing panel which victims were tricked into accessing from mobile phones or work computers during social engineering calls.(Citation: FBI Salesforce Data Theft SEP 2025)(Citation: Google Salesforce JUN 2025) [FBI Salesforce Data Theft SEP 2025](https://www.ic3.gov/CSA/2025/250912.pdf) · [Google Salesforce JUN 2025](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion)
- [G0122 - Silent Librarian](../../../../Threat%20Intelligence/Groups/G0122%20-%20Silent%20Librarian.md) — [Silent Librarian](https://attack.mitre.org/groups/G0122) has cloned victim organization login pages and staged them for later use in credential harvesting campaigns. [Silent Librarian](https://attack.mitre.org/groups/G0122) has also made use of a variety of URL shorteners for these staged websites.(Citation: Secureworks COBALT DICKENS September 2019)(Citation: Malwarebytes Silent Librarian October 2020)(Citation: Proofpoint TA407 September 2019) [Secureworks COBALT DICKENS September 2019](https://www.secureworks.com/blog/cobalt-dickens-goes-back-to-school-again) · [Malwarebytes Silent Librarian October 2020](https://blog.malwarebytes.com/malwarebytes-news/2020/10/silent-librarian-apt-phishing-attack/) · [Proofpoint TA407 September 2019](https://www.proofpoint.com/us/threat-insight/post/threat-actor-profile-ta407-silent-librarian)

## Detection strategies

- [DET0893 - Detection of Link Target](../../../../Defenses/Detection%20Strategies/DET0893%20-%20Detection%20of%20Link%20Target.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Netskope GCP Redirection](https://www.netskope.com/blog/targeted-attacks-abusing-google-cloud-platform-open-redirection)
- [Netskope Cloud Phishing](https://www.netskope.com/blog/a-big-catch-cloud-phishing-from-google-app-engine-and-azure-app-service)
- [URI Unique](https://media.defense.gov/2020/Jun/09/2002313081/-1/-1/0/CSI-DETECT-AND-PREVENT-WEB-SHELL-MALWARE-20200422.PDF)
- [Kaspersky-masking](https://www.kaspersky.com/blog/malicious-redirect-methods/50045/)
- [Talos IPFS 2022](https://blog.talosintelligence.com/ipfs-abuse/)
- [Malwarebytes Silent Librarian October 2020](https://blog.malwarebytes.com/malwarebytes-news/2020/10/silent-librarian-apt-phishing-attack/)
- [URI](https://www.techtarget.com/searchsecurity/tip/Preparing-for-uniform-resource-identifier-URI-exploits)
- [URI Use](https://www.blackhat.com/presentations/bh-dc-08/McFeters-Rios-Carter/Presentation/bh-dc-08-mcfeters-rios-carter.pdf)
- [iOS URL Scheme](https://docs.ostorlab.co/kb/IPA_URL_SCHEME_HIJACKING/index.html)
- [Intezer App Service Phishing](https://www.intezer.com/blog/malware-analysis/kud-i-enter-your-server-new-vulnerabilities-in-microsoft-azure/)
- [Proofpoint TA407 September 2019](https://www.proofpoint.com/us/threat-insight/post/threat-actor-profile-ta407-silent-librarian)
- [Cofense-redirect](https://cofense.com/blog/major-energy-company-targeted-in-large-qr-code-campaign/)
- [mandiant-masking](https://www.mandiant.com/resources/blog/url-obfuscation-schema-abuse)
