# T1634.001 - Keychain

[Mobile](../../../../README.md) / [Credential Access](../../README.md) / [T1634 - Credentials from Password Store](../README.md)

Adversaries may collect keychain data from an iOS device to acquire credentials. Keychains are the built-in way for iOS to keep track of users' passwords and credentials for many services and features such as Wi-Fi passwords, websites, secure notes, certificates, private keys, and VPN credentials. 

On the device, the keychain database is stored outside of application sandboxes to prevent unauthorized access to the raw data. Standard iOS APIs allow applications access to their own keychain contained within the database. By utilizing a privilege escalation exploit or existing root access, adversaries can access the entire encrypted database.(Citation: Apple Keychain Services)(Citation: Elcomsoft Decrypt Keychain)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1634/001)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0463 - INSOMNIA](../../../../Threat%20Intelligence/Software/Malware/S0463%20-%20INSOMNIA.md) — [INSOMNIA](https://attack.mitre.org/software/S0463) can extract the device’s keychain.(Citation: Google Project Zero Insomnia) [Google Project Zero Insomnia](https://googleprojectzero.blogspot.com/2019/08/implant-teardown.html)
- [S1185 - LightSpy](../../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has accessed the device’s KeyChain data.(Citation: MelikovBlackBerry LightSpy 2024)(Citation: Threatfabric LightSpy 2024)(Citation: Shoshin_Kaspersky LightSpy 2020)(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [MelikovBlackBerry LightSpy 2024](https://blogs.blackberry.com/en/2024/04/lightspy-returns-renewed-espionage-campaign-targets-southern-asia-possibly-india) · [Shoshin_Kaspersky LightSpy 2020](https://usa.kaspersky.com/blog/lightspy-watering-hole-attack/21301/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [C0054 - Operation Triangulation](../../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors have dumped the device’s keychain.(Citation: SecureList OpTriangulation 21Jun2023)(Citation: SecureList OpTriangulation 23Oct2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/) · [SecureList OpTriangulation 23Oct2023](https://securelist.com/triangulation-validators-modules/110847/)
- [S1216 - TriangleDB](../../../../Threat%20Intelligence/Software/Malware/S1216%20-%20TriangleDB.md) — [TriangleDB](https://attack.mitre.org/software/S1216) has extracted the device’s keychain.(Citation: SecureList OpTriangulation 21Jun2023) [SecureList OpTriangulation 21Jun2023](https://securelist.com/triangledb-triangulation-implant/110050/)

## Detection strategies

- [DET0664 - Detection of Keychain](../../../../Defenses/Detection%20Strategies/DET0664%20-%20Detection%20of%20Keychain.md)

## Mitigations

- [M1002 - Attestation](../../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation can often detect jailbroken devices.
- [M1010 - Deploy Compromised Device Detection Method](../../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security products can take appropriate action when jailbroken devices are detected, potentially limiting the adversary’s access to password stores.
- [M1001 - Security Updates](../../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Apple regularly provides security updates for known OS vulnerabilities.

## Sources

- [Apple Keychain Services](https://developer.apple.com/documentation/security/keychain_services)
- [Elcomsoft Decrypt Keychain](https://blog.elcomsoft.com/2018/12/six-ways-to-decrypt-iphone-passwords-from-the-keychain/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/authentication-threats/AUT-11.html)
