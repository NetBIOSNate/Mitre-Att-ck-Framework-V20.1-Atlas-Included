# T1553 - Subvert Trust Controls

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may undermine security controls that will either warn users of untrusted activity or prevent execution of untrusted programs. Operating systems and security products may contain mechanisms to identify programs or websites as possessing some level of trust. Examples of such features would include a program being allowed to run because it is signed by a valid code signing certificate, a program prompting the user with a warning because it has an attribute set from being downloaded from the Internet, or getting an indication that you are about to connect to an untrusted site.

Adversaries may attempt to subvert these trust mechanisms. The method adversaries use will depend on the specific mechanism they seek to subvert. Adversaries may conduct [File and Directory Permissions Modification](https://attack.mitre.org/techniques/T1222) or [Modify Registry](https://attack.mitre.org/techniques/T1112) in support of subverting these controls.(Citation: SpectorOps Subverting Trust Sept 2017) Adversaries may also create or steal code signing certificates to acquire trust on target systems.(Citation: Securelist Digital Certificates)(Citation: Symantec Digital Certificates)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1553)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1553.002 - Code Signing](T1553.002%20-%20Code%20Signing/README.md)
- [T1553.006 - Code Signing Policy Modification](T1553.006%20-%20Code%20Signing%20Policy%20Modification/README.md)
- [T1553.001 - Gatekeeper Bypass](T1553.001%20-%20Gatekeeper%20Bypass/README.md)
- [T1553.004 - Install Root Certificate](T1553.004%20-%20Install%20Root%20Certificate/README.md)
- [T1553.005 - Mark-of-the-Web Bypass](T1553.005%20-%20Mark-of-the-Web%20Bypass/README.md)
- [T1553.003 - SIP and Trust Provider Hijacking](T1553.003%20-%20SIP%20and%20Trust%20Provider%20Hijacking/README.md)

## Mitigations

- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — System settings can prevent applications from running that haven't been downloaded through the Apple Store (or other legitimate repositories) which can help mitigate some of these issues. Also enable application control solutions such as AppLocker and/or Device Guard to block the loading of malicious content.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Windows Group Policy can be used to manage root certificates and the <code>Flags</code> value of <code>HKLM\\SOFTWARE\\Policies\\Microsoft\\SystemCertificates\\Root\\ProtectedRoots</code> can be set to 1 to prevent non-administrator users from making further root installations into their own HKCU certificate store. (Citation: SpectorOps Code Signing Dec 2017) [SpectorOps Code Signing Dec 2017](https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Manage the creation, modification, use, and permissions associated to privileged accounts, including SYSTEM and root.
- [M1024 - Restrict Registry Permissions](../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper permissions are set for Registry hives to prevent users from modifying keys related to SIP and trust provider components. Components may still be able to be hijacked to suitable functions already present on disk if malicious modifications to Registry keys are not prevented.
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — HTTP Public Key Pinning (HPKP) is one method to mitigate potential [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) situations where and adversary uses a mis-issued or fraudulent certificate to intercept encrypted communications by enforcing use of an expected certificate. (Citation: Wikipedia HPKP) [Wikipedia HPKP](https://en.wikipedia.org/wiki/HTTP_Public_Key_Pinning)

## Procedure examples

- [G0001 - Axiom](../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) has used digital certificates to deliver malware.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [S9008 - Shai-Hulud](../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has suppressed victim NPM warnings using `process[“exit’](0x0);` which results in having all errors exit with code 0.(Citation: Socket Shai-Hulud November 2025) [Socket Shai-Hulud November 2025](https://socket.dev/blog/shai-hulud-strikes-again-v2)

## Detection strategies

- [DET0452 - Detect Subversion of Trust Controls via Certificate, Registry, and Attribute Manipulation](../../../Defenses/Detection%20Strategies/DET0452%20-%20Detect%20Subversion%20of%20Trust%20Controls%20via%20Certificate%2C%20Registry%2C%20and%20Attribute%20Manipula.md)

## Sources

- [SpectorOps Subverting Trust Sept 2017](https://specterops.io/assets/resources/SpecterOps_Subverting_Trust_in_Windows.pdf)
- [Securelist Digital Certificates](https://securelist.com/why-you-shouldnt-completely-trust-files-signed-with-digital-certificates/68593/)
- [Symantec Digital Certificates](http://www.symantec.com/connect/blogs/how-attackers-steal-private-keys-digital-certificates)
