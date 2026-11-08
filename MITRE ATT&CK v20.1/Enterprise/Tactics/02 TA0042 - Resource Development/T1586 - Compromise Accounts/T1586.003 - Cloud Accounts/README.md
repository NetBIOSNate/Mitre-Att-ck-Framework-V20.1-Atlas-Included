# T1586.003 - Cloud Accounts

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1586 - Compromise Accounts](../README.md)

Adversaries may compromise cloud accounts that can be used during targeting. Adversaries can use compromised cloud accounts to further their operations, including leveraging cloud storage services such as Dropbox, Microsoft OneDrive, or AWS S3 buckets for [Exfiltration to Cloud Storage](https://attack.mitre.org/techniques/T1567/002) or to [Upload Tool](https://attack.mitre.org/techniques/T1608/002)s. Cloud accounts can also be used in the acquisition of infrastructure, such as [Virtual Private Server](https://attack.mitre.org/techniques/T1583/003)s or [Serverless](https://attack.mitre.org/techniques/T1583/007) infrastructure. Additionally, cloud-based messaging services such as Twilio, SendGrid, AWS End User Messaging, AWS SNS (Simple Notification Service), or AWS SES (Simple Email Service) may be leveraged for spam or [Phishing](https://attack.mitre.org/techniques/T1566).(Citation: Palo Alto Unit 42 Compromised Cloud Compute Credentials 2022)(Citation: Netcraft SendGrid 2024) Compromising cloud accounts may allow adversaries to develop sophisticated capabilities without managing their own servers.(Citation: Awake Security C2 Cloud)

A variety of methods exist for compromising cloud accounts, such as gathering credentials via [Phishing for Information](https://attack.mitre.org/techniques/T1598), purchasing credentials from third-party sites, conducting [Password Spraying](https://attack.mitre.org/techniques/T1110/003) attacks, or attempting to [Steal Application Access Token](https://attack.mitre.org/techniques/T1528)s.(Citation: MSTIC Nobelium Oct 2021) Prior to compromising cloud accounts, adversaries may conduct Reconnaissance to inform decisions about which accounts to compromise to further their operation. In some cases, adversaries may target privileged service provider accounts with the intent of leveraging a [Trusted Relationship](https://attack.mitre.org/techniques/T1199) between service providers and their customers.(Citation: MSTIC Nobelium Oct 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1586/003)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0879 - Detection of Cloud Accounts](../../../../Defenses/Detection%20Strategies/DET0879%20-%20Detection%20of%20Cloud%20Accounts.md)

## Procedure examples

- [G0099 - APT-C-36](../../../../Threat%20Intelligence/Groups/G0099%20-%20APT-C-36.md) — [APT-C-36](https://attack.mitre.org/groups/G0099) has used compromised Google Drive accounts including one associated with a Colombian government organization.(Citation: Recorded Future TAG-144 AUG 2025) [Recorded Future TAG-144 AUG 2025](https://assets.recordedfuture.com/insikt-report-pdfs/2025/cta-2025-0826.pdf)
- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has used residential proxies, including Azure Virtual Machines, to obfuscate their access to victim environments.(Citation: Mandiant APT29 Microsoft 365 2022) [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used virtual private server (VPS) providers to host C2 infrastructure including Hostwinds.(Citation: Microsoft Axios Compromise APR 2026)(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [Microsoft Axios Compromise APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/01/mitigating-the-axios-npm-supply-chain-compromise/) · [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [C0040 - APT41 DUST](../../../../Threat%20Intelligence/Campaigns/C0040%20-%20APT41%20DUST.md) — [APT41 DUST](https://attack.mitre.org/campaigns/C0040) used compromised Google Workspace accounts for command and control.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Palo Alto Unit 42 Compromised Cloud Compute Credentials 2022](https://unit42.paloaltonetworks.com/compromised-cloud-compute-credentials/)
- [Awake Security C2 Cloud](https://awakesecurity.com/blog/threat-hunting-series-detecting-command-control-in-the-cloud/)
- [Netcraft SendGrid 2024](https://www.netcraft.com/blog/popular-email-platform-used-to-impersonate-itself/)
- [MSTIC Nobelium Oct 2021](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)
