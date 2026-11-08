# T1481.002 - Bidirectional Communication

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1481 - Web Service](../README.md)

Adversaries may use an existing, legitimate external Web service channel as a means for sending commands to and receiving output from a compromised system. Compromised systems may leverage popular websites and social media to host command and control (C2) instructions. Those infected systems can then send the output from those commands back over that Web service channel. The return traffic may occur in a variety of ways, depending on the Web service being utilized. For example, the return traffic may take the form of the compromised system posting a comment on a forum, issuing a pull request to development project, updating a document hosted on a Web service, or by sending a Tweet. 

 

Popular websites and social media, acting as a mechanism for C2, may give a significant amount of cover. This is due to the likelihood that hosts within a network are already communicating with them prior to a compromise. Using common services, such as those offered by Google or Twitter, makes it easier for adversaries to hide in expected noise. Web service providers commonly use SSL/TLS encryption, giving adversaries an added level of protection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1481/002)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0655 - BusyGasper](../../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can be controlled via IRC using freenode.net servers.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S9048 - KoSpy](../../../../Threat%20Intelligence/Software/Malware/S9048%20-%20KoSpy.md) — [KoSpy](https://attack.mitre.org/software/S9048) has used Firebase Firestore to receive configuration data: an “on”/”off” switch and the C2 server address.(Citation: Lookout_KoSpy_March2025) [Lookout_KoSpy_March2025](https://security.lookout.com/threat-intelligence/article/lookout-discovers-new-spyware-by-north-korean-apt37)
- [S0485 - Mandrake](../../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) has used Firebase for C2.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0545 - TERRACOTTA](../../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) has used Firebase for C2 communication.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)
- [S9006 - VajraSpy](../../../../Threat%20Intelligence/Software/Malware/S9006%20-%20VajraSpy.md) — [VajraSpy](https://attack.mitre.org/software/S9006) has used Firebase and Google Cloud Storage to send and receive C2 communications and to send collected data.(Citation: ESET_VajraSpy_Feb2024)(Citation: K7Dhanalakshmi_VajraSpy_April2022) [K7Dhanalakshmi_VajraSpy_April2022](https://labs.k7computing.com/index.php/vajraspy-an-android-rat/) · [ESET_VajraSpy_Feb2024](https://www.welivesecurity.com/en/eset-research/vajraspy-patchwork-espionage-apps/)

## Detection strategies

- [DET0700 - Detection of Bidirectional Communication](../../../../Defenses/Detection%20Strategies/DET0700%20-%20Detection%20of%20Bidirectional%20Communication.md)
