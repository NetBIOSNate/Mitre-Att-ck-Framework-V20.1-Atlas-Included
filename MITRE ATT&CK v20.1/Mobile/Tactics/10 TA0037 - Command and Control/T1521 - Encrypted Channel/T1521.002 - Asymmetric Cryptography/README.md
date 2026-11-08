# T1521.002 - Asymmetric Cryptography

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1521 - Encrypted Channel](../README.md)

Adversaries may employ a known asymmetric encryption algorithm to conceal command and control traffic, rather than relying on any inherent protections provided by a communication protocol. Asymmetric cryptography, also known as public key cryptography, uses a keypair per party: one public that can be freely distributed, and one private that should not be distributed. Due to how asymmetric algorithms work, the sender encrypts data with the receiver’s public key and the receiver decrypts the data with their private key. This ensures that only the intended recipient can read the encrypted data. Common public key encryption algorithms include RSA, ElGamal, and ECDSA.

For efficiency, many protocols (including SSL/TLS) use symmetric cryptography once a connection is established, but use asymmetric cryptography to establish or transmit a key. As such, these protocols are classified as [Asymmetric Cryptography](https://attack.mitre.org/techniques/T1521/002).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1521/002)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0529 - CarbonSteal](../../../../Threat%20Intelligence/Software/Malware/S0529%20-%20CarbonSteal.md) — [CarbonSteal](https://attack.mitre.org/software/S0529) has performed rudimentary SSL certificate validation to verify C2 server authenticity before establishing a SSL connection.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S0555 - CHEMISTGAMES](../../../../Threat%20Intelligence/Software/Malware/S0555%20-%20CHEMISTGAMES.md) — [CHEMISTGAMES](https://attack.mitre.org/software/S0555) has used HTTPS for C2 communication.(Citation: CYBERWARCON CHEMISTGAMES) [CYBERWARCON CHEMISTGAMES](https://www.youtube.com/watch?v=xoNSbm1aX_w)
- [S0507 - eSurv](../../../../Threat%20Intelligence/Software/Malware/S0507%20-%20eSurv.md) — [eSurv](https://attack.mitre.org/software/S0507)’s Android version has used public key encryption for C2 communication.(Citation: Lookout eSurv) [Lookout eSurv](https://blog.lookout.com/esurv-research)
- [S1067 - FluBot](../../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) has encrypted C2 message bodies with RSA and encoded them in base64.(Citation: proofpoint_flubot_0421) [proofpoint_flubot_0421](https://www.proofpoint.com/us/blog/threat-insight/flubot-android-malware-spreading-rapidly-through-europe-may-hit-us-soon)
- [C0054 - Operation Triangulation](../../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors used RSA to encrypt C2 communication.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)
- [S1055 - SharkBot](../../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) has used RSA to encrypt the symmetric encryption key used for C2 messages.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)
- [S0549 - SilkBean](../../../../Threat%20Intelligence/Software/Malware/S0549%20-%20SilkBean.md) — [SilkBean](https://attack.mitre.org/software/S0549) has used HTTPS for C2 communication.(Citation: Lookout Uyghur Campaign) [Lookout Uyghur Campaign](https://www.lookout.com/documents/threat-reports/us/lookout-uyghur-malware-tr-us.pdf)
- [S1216 - TriangleDB](../../../../Threat%20Intelligence/Software/Malware/S1216%20-%20TriangleDB.md) — [TriangleDB](https://attack.mitre.org/software/S1216) has encrypted data using RSA.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)

## Detection strategies

- [DET0667 - Detection of Asymmetric Cryptography](../../../../Defenses/Detection%20Strategies/DET0667%20-%20Detection%20of%20Asymmetric%20Cryptography.md)
