# T1634 - Credentials from Password Store

[Mobile](../../../README.md) / [Credential Access](../README.md)

Adversaries may search common password storage locations to obtain user credentials. Passwords can be stored in several places on a device, depending on the operating system or application holding the credentials. There are also specific applications that store passwords to make it easier for users to manage and maintain. Once credentials are obtained, they can be used to perform lateral movement and access restricted information.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1634)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1634.001 - Keychain](T1634.001%20-%20Keychain/README.md)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation can often detect jailbroken devices.
- [M1010 - Deploy Compromised Device Detection Method](../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security products can take appropriate action when jailbroken devices are detected, potentially limiting the adversary’s access to password stores.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Apple regularly provides security updates for known OS vulnerabilities.

## Detection strategies

- [DET0633 - Detection of Credentials from Password Store](../../../Defenses/Detection%20Strategies/DET0633%20-%20Detection%20of%20Credentials%20from%20Password%20Store.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/authentication-threats/AUT-11.html)
