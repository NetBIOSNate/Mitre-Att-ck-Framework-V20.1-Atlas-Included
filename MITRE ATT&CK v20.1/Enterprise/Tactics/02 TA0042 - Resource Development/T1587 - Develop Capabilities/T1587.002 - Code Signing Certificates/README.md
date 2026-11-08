# T1587.002 - Code Signing Certificates

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1587 - Develop Capabilities](../README.md)

Adversaries may create self-signed code signing certificates that can be used during targeting. Code signing is the process of digitally signing executables and scripts to confirm the software author and guarantee that the code has not been altered or corrupted. Code signing provides a level of authenticity for a program from the developer and a guarantee that the program has not been tampered with.(Citation: Wikipedia Code Signing) Users and/or security tools may trust a signed piece of code more than an unsigned piece of code even if they don't know who issued the certificate or who the author is.

Prior to [Code Signing](https://attack.mitre.org/techniques/T1553/002), adversaries may develop self-signed code signing certificates for use in operations.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1587/002)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [G1034 - Daggerfly](../../../../Threat%20Intelligence/Groups/G1034%20-%20Daggerfly.md) — [Daggerfly](https://attack.mitre.org/groups/G1034) created code signing certificates to sign malicious macOS files.(Citation: ESET EvasivePanda 2024) [ESET EvasivePanda 2024](https://www.welivesecurity.com/en/eset-research/evasive-panda-leverages-monlam-festival-target-tibetans/)
- [C0022 - Operation Dream Job](../../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — During [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) digitally signed their malware and the dbxcli utility.(Citation: ESET Lazarus Jun 2020) [ESET Lazarus Jun 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_Operation_Interception.pdf)
- [G0040 - Patchwork](../../../../Threat%20Intelligence/Groups/G0040%20-%20Patchwork.md) — [Patchwork](https://attack.mitre.org/groups/G0040) has created self-signed certificates from fictitious and spoofed legitimate software companies that were later used to sign malware.(Citation: Unit 42 BackConfig May 2020) [Unit 42 BackConfig May 2020](https://unit42.paloaltonetworks.com/updated-backconfig-malware-targeting-government-and-military-organizations/)
- [G0056 - PROMETHIUM](../../../../Threat%20Intelligence/Groups/G0056%20-%20PROMETHIUM.md) — [PROMETHIUM](https://attack.mitre.org/groups/G0056) has created self-signed certificates to sign malicious installers.(Citation: Bitdefender StrongPity June 2020) [Bitdefender StrongPity June 2020](https://www.bitdefender.com/files/News/CaseStudies/study/353/Bitdefender-Whitepaper-StrongPity-APT.pdf)

## Detection strategies

- [DET0833 - Detection of Code Signing Certificates](../../../../Defenses/Detection%20Strategies/DET0833%20-%20Detection%20of%20Code%20Signing%20Certificates.md)

## Sources

- [Wikipedia Code Signing](https://en.wikipedia.org/wiki/Code_signing)
