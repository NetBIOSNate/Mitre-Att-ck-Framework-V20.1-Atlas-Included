# T1195 - Supply Chain Compromise

[Enterprise](../../../README.md) / [Initial Access](../README.md)

Adversaries may manipulate products or product delivery mechanisms prior to receipt by a final consumer for the purpose of data or system compromise.

Supply chain compromise can take place at any stage of the supply chain including:

* Manipulation of development tools
* Manipulation of a development environment
* Manipulation of source code repositories (public or private)
* Manipulation of source code in open-source dependencies
* Manipulation of software update/distribution mechanisms
* Compromised/infected system images (removable media infected at the factory)(Citation: IBM Storwize)(Citation: Schneider Electric USB Malware) 
* Replacement of legitimate software with modified versions
* Sales of modified/counterfeit products to legitimate distributors
* Shipment interdiction

While supply chain compromise can impact any component of hardware or software, adversaries looking to gain execution have often focused on malicious additions to legitimate software in software distribution or update channels.(Citation: Avast CCleaner3 2018)(Citation: Microsoft Dofoil 2018)(Citation: Command Five SK 2011) Adversaries may limit targeting to a desired victim set or distribute malicious software to a broad set of consumers but only follow up with specific victims.(Citation: Symantec Elderwood Sept 2012)(Citation: Avast CCleaner3 2018)(Citation: Command Five SK 2011) Popular open-source projects that are used as dependencies in many applications may also be targeted as a means to add malicious code to users of the dependency.(Citation: Trendmicro NPM Compromise)

In some cases, adversaries may conduct “second-order” supply chain compromises by leveraging the access gained from an initial supply chain compromise to further compromise a software component.(Citation: Krebs 3cx overview 2023) This may allow the threat actor to spread to even more victims.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1195)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), [SaaS](../../../Platforms/SaaS.md)

## Sub-techniques

- [T1195.003 - Compromise Hardware Supply Chain](T1195.003%20-%20Compromise%20Hardware%20Supply%20Chain/README.md)
- [T1195.001 - Compromise Software Dependencies and Development Tools](T1195.001%20-%20Compromise%20Software%20Dependencies%20and%20Development%20Tools/README.md)
- [T1195.002 - Compromise Software Supply Chain](T1195.002%20-%20Compromise%20Software%20Supply%20Chain/README.md)

## Procedure examples

- [G1003 - Ember Bear](../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) has compromised information technology providers and software developers providing services to targets of interest, building initial access to ultimate victims at least in part through compromise of service providers that work with the victim organizations.(Citation: Cadet Blizzard emerges as novel threat actor) [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/)
- [S1213 - Lumma Stealer](../../../Threat%20Intelligence/Software/Malware/S1213%20-%20Lumma%20Stealer.md) — [Lumma Stealer](https://attack.mitre.org/software/S1213) has been delivered through cracked software downloads.(Citation: Cybereason LumaStealer Undated)(Citation: Fortinet LummaStealer 2024)(Citation: TrendMicro LummaStealer 2025) [TrendMicro LummaStealer 2025](https://www.trendmicro.com/en_us/research/25/a/lumma-stealers-github-based-delivery-via-mdr.html) · [Fortinet LummaStealer 2024](https://www.fortinet.com/blog/threat-research/lumma-variant-on-youtube) · [Cybereason LumaStealer Undated](https://www.cybereason.com/blog/threat-analysis-rise-of-lummastealer)
- [G0049 - OilRig](../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has leveraged compromised organizations to conduct supply chain attacks on government entities.(Citation: Trend Micro Earth Simnavaz October 2024) [Trend Micro Earth Simnavaz October 2024](https://www.trendmicro.com/en_us/research/24/j/earth-simnavaz-cyberattacks.html)
- [S1148 - Raccoon Stealer](../../../Threat%20Intelligence/Software/Malware/S1148%20-%20Raccoon%20Stealer.md) — [Raccoon Stealer](https://attack.mitre.org/software/S1148) has been distributed through cracked software downloads.(Citation: S2W Racoon 2022) [S2W Racoon 2022](https://medium.com/s2wblog/raccoon-stealer-is-back-with-a-new-version-5f436e04b20d)
- [G0034 - Sandworm Team](../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) staged compromised versions of legitimate software installers on forums to achieve initial, untargetetd access in victim environments.(Citation: mandiant_apt44_unearthing_sandworm) [mandiant_apt44_unearthing_sandworm](https://services.google.com/fh/files/misc/apt44-unearthing-sandworm.pdf)

## Mitigations

- [M1013 - Application Developer Guidance](../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Application developers should be cautious when selecting third-party libraries to integrate into their application. Additionally, where possible, developers should lock software dependencies to specific versions rather than pulling the latest version on build.(Citation: Cider Security Top 10 CICD Security Risks) [Cider Security Top 10 CICD Security Risks](https://web.archive.org/web/20220316130828/https://www.cidersecurity.io/top-10-cicd-security-risks/)
- [M1046 - Boot Integrity](../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Use secure methods to boot a system and verify the integrity of the operating system and loading mechanisms.
- [M1033 - Limit Software Installation](../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Where possible, consider requiring developers to pull from internal repositories containing verified and approved packages rather than from external ones.(Citation: Cider Security Top 10 CICD Security Risks) [Cider Security Top 10 CICD Security Risks](https://web.archive.org/web/20220316130828/https://www.cidersecurity.io/top-10-cicd-security-risks/)
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — A patch management process should be implemented to check unused dependencies, unmaintained and/or previously vulnerable dependencies, unnecessary features, components, files, and documentation.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Implement robust user account management practices to limit permissions associated with software execution. Ensure that software runs with the lowest necessary privileges, avoiding the use of root or administrator accounts when possible. By restricting permissions, you can minimize the risk of propagation and unauthorized actions in the event of a supply chain compromise, reducing the attack surface for adversaries to exploit within compromised systems.
- [M1016 - Vulnerability Scanning](../../../Defenses/Mitigations/M1016%20-%20Vulnerability%20Scanning.md) — Continuous monitoring of vulnerability sources and the use of automatic and manual code review tools should also be implemented as well.(Citation: OWASP Top 10) [OWASP Top 10](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project)

## Detection strategies

- [DET0537 - Behavioral detection for Supply Chain Compromise (package/update tamper → install → first-run)](../../../Defenses/Detection%20Strategies/DET0537%20-%20Behavioral%20detection%20for%20Supply%20Chain%20Compromise%20%28package%20-%20update%20tamper%20%E2%86%92%20install%20%E2%86%92.md)

## Sources

- [Avast CCleaner3 2018](https://blog.avast.com/new-investigations-in-ccleaner-incident-point-to-a-possible-third-stage-that-had-keylogger-capacities)
- [Krebs 3cx overview 2023](https://krebsonsecurity.com/2023/04/3cx-breach-was-a-double-supply-chain-compromise/)
- [Command Five SK 2011](https://web.archive.org/web/20160309235002/https://www.commandfive.com/papers/C5_APT_SKHack.pdf)
- [IBM Storwize](https://www-01.ibm.com/support/docview.wss?uid=ssg1S1010146&myns=s028&mynp=OCSTHGUJ&mynp=OCSTLM5A&mynp=OCSTLM6B&mynp=OCHW206&mync=E&cm_sp=s028-_-OCSTHGUJ-OCSTLM5A-OCSTLM6B-OCHW206-_-E)
- [Symantec Elderwood Sept 2012](https://web.archive.org/web/20190717233006/http:/www.symantec.com/content/en/us/enterprise/media/security_response/whitepapers/the-elderwood-project.pdf)
- [Schneider Electric USB Malware](https://www.se.com/us/en/download/document/SESN-2018-236-01/)
- [Trendmicro NPM Compromise](https://www.trendmicro.com/vinfo/dk/security/news/cybercrime-and-digital-threats/hacker-infects-node-js-package-to-steal-from-bitcoin-wallets)
- [Microsoft Dofoil 2018](https://cloudblogs.microsoft.com/microsoftsecure/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign/)
