# T1521.001 - Symmetric Cryptography

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1521 - Encrypted Channel](../README.md)

Adversaries may employ a known symmetric encryption algorithm to conceal command and control traffic, rather than relying on any inherent protections provided by a communication protocol. Symmetric encryption algorithms use the same key for plaintext encryption and ciphertext decryption. Common symmetric encryption algorithms include AES, Blowfish, and RC4.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1521/001)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [C0033 - C0033](../../../../Threat%20Intelligence/Campaigns/C0033%20-%20C0033.md) — During [C0033](https://attack.mitre.org/campaigns/C0033), [PROMETHIUM](https://attack.mitre.org/groups/G0056) used [StrongPity](https://attack.mitre.org/software/S0491) to encrypt C2 communication using AES.(Citation: welivesec_strongpity) [welivesec_strongpity](https://www.welivesecurity.com/2023/01/10/strongpity-espionage-campaign-targeting-android-users/)
- [S0478 - EventBot](../../../../Threat%20Intelligence/Software/Malware/S0478%20-%20EventBot.md) — [EventBot](https://attack.mitre.org/software/S0478) has encrypted base64-encoded payload data using RC4 and Curve25519.(Citation: Cybereason EventBot) [Cybereason EventBot](https://www.cybereason.com/blog/eventbot-a-new-mobile-banking-trojan-is-born)
- [C0054 - Operation Triangulation](../../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors used 3DES and AES to encrypt C2 communication and data.(Citation: SecureList OpTriangulation 21Jun2023)(Citation: SecureList OpTriangulation 23Oct2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/) · [SecureList OpTriangulation 23Oct2023](https://securelist.com/triangulation-validators-modules/110847/)
- [S0411 - Rotexy](../../../../Threat%20Intelligence/Software/Malware/S0411%20-%20Rotexy.md) — [Rotexy](https://attack.mitre.org/software/S0411) encrypts JSON HTTP payloads with AES.(Citation: securelist rotexy 2018) [securelist rotexy 2018](https://securelist.com/the-rotexy-mobile-trojan-banker-and-ransomware/88893/)
- [S1055 - SharkBot](../../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) can use RC4 to encrypt C2 payloads.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)
- [S1216 - TriangleDB](../../../../Threat%20Intelligence/Software/Malware/S1216%20-%20TriangleDB.md) — [TriangleDB](https://attack.mitre.org/software/S1216) has encrypted data using 3DES.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [G0112 - Windshift](../../../../Threat%20Intelligence/Groups/G0112%20-%20Windshift.md) — [Windshift](https://attack.mitre.org/groups/G0112) has encrypted C2 communications using AES in CBC mode during Operation BULL and Operation ROCK.(Citation: BlackBerry Bahamut) [BlackBerry Bahamut](https://www.blackberry.com/us/en/pdfviewer?file=/content/dam/blackberry-com/asset/enterprise/pdf/direct/report-spark-bahamut.pdf)

## Detection strategies

- [DET0650 - Detection of Symmetric Cryptography](../../../../Defenses/Detection%20Strategies/DET0650%20-%20Detection%20of%20Symmetric%20Cryptography.md)
