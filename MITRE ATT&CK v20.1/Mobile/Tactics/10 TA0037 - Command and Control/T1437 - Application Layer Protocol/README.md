# T1437 - Application Layer Protocol

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may communicate using application layer protocols to avoid detection/network filtering by blending in with existing traffic. Commands to the mobile device, and often the results of those commands, will be embedded within the protocol traffic between the mobile device and server. 

Adversaries may utilize many different protocols, including those used for web browsing, transferring files, electronic mail, or DNS.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1437)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1437.001 - Web Protocols](T1437.001%20-%20Web%20Protocols/README.md)

## Procedure examples

- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has used a SOCKS proxy.(Citation: ThreatFabric_Chameleon_Dec2023) [ThreatFabric_Chameleon_Dec2023](https://www.threatfabric.com/blogs/android-banking-trojan-chameleon-is-back-in-action)
- [S1243 - DCHSpy](../../../Threat%20Intelligence/Software/Malware/S1243%20-%20DCHSpy.md) — [DCHSpy](https://attack.mitre.org/software/S1243) has uploaded collected data to a Secure File Transfer Protocol (SFTP) server.(Citation: Lookout_DCHSpy_July2025) [Lookout_DCHSpy_July2025](https://www.lookout.com/threat-intelligence/article/lookout-discovers-iranian-dchsy-surveillanceware)
- [S0550 - DoubleAgent](../../../Threat%20Intelligence/Software/Malware/S0550%20-%20DoubleAgent.md) — [DoubleAgent](https://attack.mitre.org/software/S0550) has used both FTP and TCP sockets for data exfiltration.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1054 - Drinik](../../../Threat%20Intelligence/Software/Malware/S1054%20-%20Drinik.md) — [Drinik](https://attack.mitre.org/software/S1054) has code to use Firebase Cloud Messaging for receiving C2 instructions.(Citation: cyble_drinik_1022) [cyble_drinik_1022](https://web.archive.org/web/20221114031945/https://blog.cyble.com/2022/10/27/drinik-malware-returns-with-advanced-capabilities-targeting-indian-taxpayers/)
- [S9040 - NGate](../../../Threat%20Intelligence/Software/Malware/S9040%20-%20NGate.md) — [NGate](https://attack.mitre.org/software/S9040) has used TCP sockets to communicate with the C2 server.(Citation: CERTPL_NGate_Nov2025) [CERTPL_NGate_Nov2025](https://cert.pl/en/posts/2025/11/analiza-ngate/)
- [C0054 - Operation Triangulation](../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors used HTTPS POST requests for C2 communication.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)

## Detection strategies

- [DET0685 - Detection of Application Layer Protocol](../../../Defenses/Detection%20Strategies/DET0685%20-%20Detection%20of%20Application%20Layer%20Protocol.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-29.html)
