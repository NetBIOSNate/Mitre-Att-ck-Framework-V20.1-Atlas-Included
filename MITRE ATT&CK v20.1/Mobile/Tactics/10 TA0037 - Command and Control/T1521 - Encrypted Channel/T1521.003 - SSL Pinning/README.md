# T1521.003 - SSL Pinning

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1521 - Encrypted Channel](../README.md)

Adversaries may use [SSL Pinning](https://attack.mitre.org/techniques/T1521/003)  to protect the C2 traffic from being intercepted and analyzed.

[SSL Pinning](https://attack.mitre.org/techniques/T1521/003)  is a technique commonly utilized by legitimate websites to ensure that encrypted communications are only allowed with a pre-defined certificate. If another certificate is presented, it could indicate device compromise, traffic interception, or another upstream issue. While benign usages are common, it is also possible for adversaries to abuse this technology to protect malicious C2 traffic.

In normal, not pinned SSL validation, when a client connects to a server using HTTPS, it typically checks whether the server’s SSL/TLS certificate is signed by a trusted Certificate Authority (CA) in the device’s trust store. If the certificate is valid and signed by a trusted CA, the connection is established. However, with [SSL Pinning](https://attack.mitre.org/techniques/T1521/003) , the client is configured to trust a specific SSL/TLS certificate or public key, rather than relying on the device’s trust store. This means that even if the server’s certificate is signed by a trusted CA, the client will only establish the connection of the certificate or key is pinned.

There are two types of [SSL Pinning](https://attack.mitre.org/techniques/T1521/003) :

1.	Certificate Pinning: The client stores a copy of the server’s certificate and compares it with the certificate received during the SSL handshake. If the certificates match, then the client proceeds with the connection. This approach also works with self-signed certificates.

2.	Public Key Pinning: Instead of pinning the entire certificate, the client pins just the public key extracted from the certificate. This is often more flexible, as it allows the server to renew its certificate without having to update the pinned certificate or breaking the SSL connection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1521/003)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Mitigations

- [M1012 - Enterprise Policy](../../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — Certain enterprise policies can be applied to prevent users from adding certificates to the device and to prevent applications from being able to install their own certificates.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be advised to not trust or install self-signed certificates.

## Procedure examples

- [S0507 - eSurv](../../../../Threat%20Intelligence/Software/Malware/S0507%20-%20eSurv.md) — [eSurv](https://attack.mitre.org/software/S0507)’s Android version has used certificate pinning for C2 communication.(Citation: Lookout eSurv) [Lookout eSurv](https://blog.lookout.com/esurv-research)

## Detection strategies

- [DET0646 - Detection of SSL Pinning](../../../../Defenses/Detection%20Strategies/DET0646%20-%20Detection%20of%20SSL%20Pinning.md)
