# T1001 - Data Obfuscation

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries may obfuscate command and control traffic to make it more difficult to detect.(Citation: Bitdefender FunnyDream Campaign November 2020) Command and control (C2) communications are hidden (but not necessarily encrypted) in an attempt to make the content more difficult to discover or decipher and to make the communication less conspicuous and hide commands from being seen. This encompasses many methods, such as adding junk data to protocol traffic, using steganography, or impersonating legitimate protocols.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1001)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1001.001 - Junk Data](T1001.001%20-%20Junk%20Data/README.md)
- [T1001.003 - Protocol or Service Impersonation](T1001.003%20-%20Protocol%20or%20Service%20Impersonation/README.md)
- [T1001.002 - Steganography](T1001.002%20-%20Steganography/README.md)

## Procedure examples

- [S1111 - DarkGate](../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) will retrieved encrypted commands from its command and control server for follow-on actions such as cryptocurrency mining.(Citation: Ensilo Darkgate 2018) [Ensilo Darkgate 2018](https://www.fortinet.com/blog/threat-research/enter-the-darkgate-new-cryptocurrency-mining-and-ransomware-campaign)
- [S9003 - evilginx2](../../../Threat%20Intelligence/Software/Tools/S9003%20-%20evilginx2.md) — [evilginx2](https://attack.mitre.org/software/S9003) can modify the Origin and Referrer fields in HTTPS headers it relays between intended victims and legitimate websites to comply with cross-origin resource sharing (CORS) restrictions.(Citation: Evilginx 2 July 2018) [Evilginx 2 July 2018](https://breakdev.org/evilginx-2-next-generation-of-phishing-2fa-tokens/)
- [S0381 - FlawedAmmyy](../../../Threat%20Intelligence/Software/Malware/S0381%20-%20FlawedAmmyy.md) — [FlawedAmmyy](https://attack.mitre.org/software/S0381) may obfuscate portions of the initial C2 handshake.(Citation: Proofpoint TA505 Mar 2018) [Proofpoint TA505 Mar 2018](https://www.proofpoint.com/us/threat-insight/post/leaked-ammyy-admin-source-code-turned-malware)
- [S1120 - FRAMESTING](../../../Threat%20Intelligence/Software/Malware/S1120%20-%20FRAMESTING.md) — [FRAMESTING](https://attack.mitre.org/software/S1120) can send and receive zlib compressed data within `POST` requests.(Citation: Mandiant Cutting Edge Part 2 January 2024) [Mandiant Cutting Edge Part 2 January 2024](https://www.mandiant.com/resources/blog/investigating-ivanti-zero-day-exploitation)
- [S1044 - FunnyDream](../../../Threat%20Intelligence/Software/Malware/S1044%20-%20FunnyDream.md) — [FunnyDream](https://attack.mitre.org/software/S1044) can send compressed and obfuscated packets to C2.(Citation: Bitdefender FunnyDream Campaign November 2020) [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
- [G0047 - Gamaredon Group](../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used obfuscated VBScripts with randomly generated variable names and concatenated strings.(Citation: unit42_gamaredon_dec2022) [unit42_gamaredon_dec2022](https://unit42.paloaltonetworks.com/trident-ursa/)
- [S1100 - Ninja](../../../Threat%20Intelligence/Software/Malware/S1100%20-%20Ninja.md) — [Ninja](https://attack.mitre.org/software/S1100) has the ability to modify headers and URL paths to hide malicious traffic in HTTP requests.(Citation: Kaspersky ToddyCat June 2022) [Kaspersky ToddyCat June 2022](https://securelist.com/toddycat/106799/)
- [S0439 - Okrum](../../../Threat%20Intelligence/Software/Malware/S0439%20-%20Okrum.md) — Okrum leverages the HTTP protocol for C2 communication, while hiding the actual messages in the Cookie and Set-Cookie headers of the HTTP requests.(Citation: ESET Okrum July 2019) [ESET Okrum July 2019](https://www.welivesecurity.com/wp-content/uploads/2019/07/ESET_Okrum_and_Ketrican.pdf)
- [C0014 - Operation Wocao](../../../Threat%20Intelligence/Campaigns/C0014%20-%20Operation%20Wocao.md) — During [Operation Wocao](https://attack.mitre.org/campaigns/C0014), threat actors encrypted IP addresses used for "Agent" proxy hops with RC4.(Citation: FoxIT Wocao December 2019) [FoxIT Wocao December 2019](https://www.fox-it.com/media/kadlze5c/201912_report_operation_wocao.pdf)
- [S0495 - RDAT](../../../Threat%20Intelligence/Software/Malware/S0495%20-%20RDAT.md) — [RDAT](https://attack.mitre.org/software/S0495) has used encoded data within subdomains as AES ciphertext to communicate from the host to the C2.(Citation: Unit42 RDAT July 2020) [Unit42 RDAT July 2020](https://unit42.paloaltonetworks.com/oilrig-novel-c2-channel-steganography/)
- [S0610 - SideTwist](../../../Threat%20Intelligence/Software/Malware/S0610%20-%20SideTwist.md) — [SideTwist](https://attack.mitre.org/software/S0610) can embed C2 responses in the source code of a fake Flickr webpage.(Citation: Check Point APT34 April 2021) [Check Point APT34 April 2021](https://research.checkpoint.com/2021/irans-apt34-returns-with-an-updated-arsenal/)
- [S0533 - SLOTHFULMEDIA](../../../Threat%20Intelligence/Software/Malware/S0533%20-%20SLOTHFULMEDIA.md) — [SLOTHFULMEDIA](https://attack.mitre.org/software/S0533) has hashed a string containing system information prior to exfiltration via POST requests.(Citation: CISA MAR SLOTHFULMEDIA October 2020) [CISA MAR SLOTHFULMEDIA October 2020](https://us-cert.cisa.gov/ncas/analysis-reports/ar20-275a)
- [S1183 - StrelaStealer](../../../Threat%20Intelligence/Software/Malware/S1183%20-%20StrelaStealer.md) — [StrelaStealer](https://attack.mitre.org/software/S1183) encrypts the payload of HTTP POST communications using the same XOR key used for the malware's DLL payload.(Citation: DCSO StrelaStealer 2022) [DCSO StrelaStealer 2022](https://medium.com/@DCSO_CyTec/shortandmalicious-strelastealer-aims-for-mail-credentials-a4c3e78c8abc)
- [S9001 - SystemBC](../../../Threat%20Intelligence/Software/Malware/S9001%20-%20SystemBC.md) — [SystemBC](https://attack.mitre.org/software/S9001) has encoded with XOR and encrypted with RC4 its beacon.(Citation: Lumen_SystemBC_Sept2025) [Lumen_SystemBC_Sept2025](https://blog.lumen.com/systembc-bringing-the-noise/)
- [S0682 - TrailBlazer](../../../Threat%20Intelligence/Software/Malware/S0682%20-%20TrailBlazer.md) — [TrailBlazer](https://attack.mitre.org/software/S0682) can masquerade its C2 traffic as legitimate Google Notifications HTTP requests.(Citation: CrowdStrike StellarParticle January 2022) [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/)

## Detection strategies

- [DET0053 - Detect Obfuscated C2 via Network Traffic Analysis](../../../Defenses/Detection%20Strategies/DET0053%20-%20Detect%20Obfuscated%20C2%20via%20Network%20Traffic%20Analysis.md)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate some obfuscation activity at the network level.

## Sources

- [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)
- [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
