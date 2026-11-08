# T1555.002 - Securityd Memory

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1555 - Credentials from Password Stores](../README.md)

An adversary with root access may gather credentials by reading `securityd`’s memory. `securityd` is a service/daemon responsible for implementing security protocols such as encryption and authorization.(Citation: Apple Dev SecurityD) A privileged adversary may be able to scan through `securityd`'s memory to find the correct sequence of keys to decrypt the user’s logon keychain. This may provide the adversary with various plaintext passwords, such as those for users, WiFi, mail, browsers, certificates, secure notes, etc.(Citation: OS X Keychain)(Citation: OSX Keydnap malware)

In OS X prior to El Capitan, users with root access can read plaintext keychain passwords of logged-in users because Apple’s keychain implementation allows these credentials to be cached so that users are not repeatedly prompted for passwords.(Citation: OS X Keychain)(Citation: External to DA, the OS X Way) Apple’s `securityd` utility takes the user’s logon password, encrypts it with PBKDF2, and stores this master key in memory. Apple also uses a set of keys and algorithms to encrypt the user’s password, but once the master key is found, an adversary need only iterate over the other values to unlock the final password.(Citation: OS X Keychain)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1555/002)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0276 - Keydnap](../../../../Threat%20Intelligence/Software/Malware/S0276%20-%20Keydnap.md) — [Keydnap](https://attack.mitre.org/software/S0276) uses the keychaindump project to read securityd memory.(Citation: synack 2016 review) [synack 2016 review](https://objective-see.org/blog/blog_0x16.html)

## Detection strategies

- [DET0057 - Detect Suspicious Access to securityd Memory for Credential Extraction](../../../../Defenses/Detection%20Strategies/DET0057%20-%20Detect%20Suspicious%20Access%20to%20securityd%20Memory%20for%20Credential%20Extraction.md)

## Sources

- [External to DA, the OS X Way](https://www.slideshare.net/slideshow/external-to-da-the-os-x-way/62021418)
- [Apple Dev SecurityD](https://developer.apple.com/library/archive/documentation/Security/Conceptual/Security_Overview/Architecture/Architecture.html)
- [OS X Keychain](https://web.archive.org/web/20130106164109/https://juusosalonen.com/post/30923743427/breaking-into-the-os-x-keychain)
- [OSX Keydnap malware](https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/)
