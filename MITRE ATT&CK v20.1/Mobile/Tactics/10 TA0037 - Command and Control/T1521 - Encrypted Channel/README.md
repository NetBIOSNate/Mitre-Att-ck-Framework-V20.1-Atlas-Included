# T1521 - Encrypted Channel

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may explicitly employ a known encryption algorithm to conceal command and control traffic rather than relying on any inherent protections provided by a communication protocol. Despite the use of a secure algorithm, these implementations may be vulnerable to reverse engineering if necessary secret keys are encoded and/or generated within malware samples/configuration files.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1521)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1521.002 - Asymmetric Cryptography](T1521.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1521.003 - SSL Pinning](T1521.003%20-%20SSL%20Pinning/README.md)
- [T1521.001 - Symmetric Cryptography](T1521.001%20-%20Symmetric%20Cryptography/README.md)

## Procedure examples

- [S1095 - AhRat](../../../Threat%20Intelligence/Software/Malware/S1095%20-%20AhRat.md) — [AhRat](https://attack.mitre.org/software/S1095) can communicate with the C2 using HTTPS requests.(Citation: welivesecurity_ahrat_0523) [welivesecurity_ahrat_0523](https://www.welivesecurity.com/2023/05/23/android-app-breaking-bad-legitimate-screen-recording-file-exfiltration/)
- [S0302 - Twitoor](../../../Threat%20Intelligence/Software/Malware/S0302%20-%20Twitoor.md) — [Twitoor](https://attack.mitre.org/software/S0302) encrypts its C2 communication.(Citation: ESET-Twitoor) [ESET-Twitoor](http://www.welivesecurity.com/2016/08/24/first-twitter-controlled-android-botnet-discovered/)

## Detection strategies

- [DET0641 - Detection of Encrypted Channel](../../../Defenses/Detection%20Strategies/DET0641%20-%20Detection%20of%20Encrypted%20Channel.md)
