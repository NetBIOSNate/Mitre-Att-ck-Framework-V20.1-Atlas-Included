# T1588.004 - Digital Certificates

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1588 - Obtain Capabilities](../README.md)

Adversaries may buy and/or steal SSL/TLS certificates that can be used during targeting. SSL/TLS certificates are designed to instill trust. They include information about the key, information about its owner's identity, and the digital signature of an entity that has verified the certificate's contents are correct. If the signature is valid, and the person examining the certificate trusts the signer, then they know they can use that key to communicate with its owner.

Adversaries may purchase or steal SSL/TLS certificates to further their operations, such as encrypting C2 traffic (ex: [Asymmetric Cryptography](https://attack.mitre.org/techniques/T1573/002) with [Web Protocols](https://attack.mitre.org/techniques/T1071/001)) or even enabling [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) if the certificate is trusted or otherwise added to the root of trust (i.e. [Install Root Certificate](https://attack.mitre.org/techniques/T1553/004)). The purchase of digital certificates may be done using a front organization or using information stolen from a previously compromised entity that allows the adversary to validate to a certificate provider as that entity. Adversaries may also steal certificate materials directly from a compromised third-party, including from certificate authorities.(Citation: DiginotarCompromise) Adversaries may register or hijack domains that they will later purchase an SSL/TLS certificate for.

Certificate authorities exist that allow adversaries to acquire SSL/TLS certificates, such as domain validation certificates, for free.(Citation: Let's Encrypt FAQ)

After obtaining a digital certificate, an adversary may then install that certificate (see [Install Digital Certificate](https://attack.mitre.org/techniques/T1608/003)) on infrastructure under their control.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1588/004)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [G0098 - BlackTech](../../../../Threat%20Intelligence/Groups/G0098%20-%20BlackTech.md) — [BlackTech](https://attack.mitre.org/groups/G0098) has used valid, stolen digital certificates for some of their malware and tools.(Citation: ESET PLEAD Malware July 2018) [ESET PLEAD Malware July 2018](https://www.welivesecurity.com/2018/07/09/certificates-stolen-taiwanese-tech-companies-plead-malware-campaign/)
- [C0043 - Indian Critical Infrastructure Intrusions](../../../../Threat%20Intelligence/Campaigns/C0043%20-%20Indian%20Critical%20Infrastructure%20Intrusions.md) — [Indian Critical Infrastructure Intrusions](https://attack.mitre.org/campaigns/C0043) included the use of digital certificates spoofing Microsoft.(Citation: RecordedFuture RedEcho 2022) [RecordedFuture RedEcho 2022](https://go.recordedfuture.com/hubfs/reports/ta-2022-0406.pdf)
- [G0032 - Lazarus Group](../../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) has obtained SSL certificates for their C2 domains.(Citation: CISA AppleJeus Feb 2021) [CISA AppleJeus Feb 2021](https://us-cert.cisa.gov/ncas/alerts/aa21-048a)
- [G1014 - LuminousMoth](../../../../Threat%20Intelligence/Groups/G1014%20-%20LuminousMoth.md) — [LuminousMoth](https://attack.mitre.org/groups/G1014) has used a valid digital certificate for some of their malware.(Citation: Kaspersky LuminousMoth July 2021) [Kaspersky LuminousMoth July 2021](https://securelist.com/apt-luminousmoth/103332/)
- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has obtained SSL certificates for their C2 domains.(Citation: EclecticIQ Mustang Panda PlugX)(Citation: Google Threat Intelligence Group MUSTANG PANDA PLUGX August 2025) [EclecticIQ Mustang Panda PlugX](https://blog.eclecticiq.com/mustang-panda-apt-group-uses-european-commission-themed-lure-to-deliver-plugx-malware) · [Google Threat Intelligence Group MUSTANG PANDA PLUGX August 2025](https://cloud.google.com/blog/topics/threat-intelligence/prc-nexus-espionage-targets-diplomats)
- [C0006 - Operation Honeybee](../../../../Threat%20Intelligence/Campaigns/C0006%20-%20Operation%20Honeybee.md) — For [Operation Honeybee](https://attack.mitre.org/campaigns/C0006), the threat actors stole a digital signature from Adobe Systems to use with their MaoCheng dropper.(Citation: McAfee Honeybee) [McAfee Honeybee](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/)
- [C0047 - RedDelta Modified PlugX Infection Chain Operations](../../../../Threat%20Intelligence/Campaigns/C0047%20-%20RedDelta%20Modified%20PlugX%20Infection%20Chain%20Operations.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) acquired Cloudflare Origin CA TLS certificates during [RedDelta Modified PlugX Infection Chain Operations](https://attack.mitre.org/campaigns/C0047).(Citation: Recorded Future RedDelta 2025) [Recorded Future RedDelta 2025](https://go.recordedfuture.com/hubfs/reports/cta-cn-2025-0109.pdf)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) created new certificates using a technique called the actors performed "certificate impersonation," a technique in which [Sea Turtle](https://attack.mitre.org/groups/G1041) obtained a certificate authority-signed X.509 certificate from another provider for the same domain imitating the one already used by the targeted organization.(Citation: Talos Sea Turtle 2019)(Citation: Talos Sea Turtle 2019_2) [Talos Sea Turtle 2019](https://blog.talosintelligence.com/seaturtle/) · [Talos Sea Turtle 2019_2](https://blog.talosintelligence.com/sea-turtle-keeps-on-swimming/)
- [G0122 - Silent Librarian](../../../../Threat%20Intelligence/Groups/G0122%20-%20Silent%20Librarian.md) — [Silent Librarian](https://attack.mitre.org/groups/G0122) has obtained free Let's Encrypt SSL certificates for use on their phishing pages.(Citation: Phish Labs Silent Librarian)(Citation: Secureworks COBALT DICKENS September 2019) [Phish Labs Silent Librarian](https://info.phishlabs.com/blog/silent-librarian-more-to-the-story-of-the-iranian-mabna-institute-indictment) · [Secureworks COBALT DICKENS September 2019](https://www.secureworks.com/blog/cobalt-dickens-goes-back-to-school-again)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has deployed malware using the victim's legitimate TLS certificate obtained from a compromised FortiGate device.(Citation: Google Cloud Mandiant UNC3886 2024) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations)

## Detection strategies

- [DET0848 - Detection of Digital Certificates](../../../../Defenses/Detection%20Strategies/DET0848%20-%20Detection%20of%20Digital%20Certificates.md)

## Sources

- [DiginotarCompromise](https://threatpost.com/final-report-diginotar-hack-shows-total-compromise-ca-servers-103112/77170/)
- [Recorded Future Beacon Certificates](https://www.recordedfuture.com/research/cobalt-strike-servers)
- [Splunk Kovar Certificates 2017](https://www.splunk.com/en_us/blog/security/tall-tales-of-hunting-with-tls-ssl-certificates.html)
- [Let's Encrypt FAQ](https://letsencrypt.org/docs/faq/)
