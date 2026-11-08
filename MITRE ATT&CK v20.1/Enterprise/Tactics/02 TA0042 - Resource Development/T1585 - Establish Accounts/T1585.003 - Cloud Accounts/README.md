# T1585.003 - Cloud Accounts

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1585 - Establish Accounts](../README.md)

Adversaries may create accounts with cloud providers that can be used during targeting. Adversaries can use cloud accounts to further their operations, including leveraging cloud storage services such as Dropbox, MEGA, Microsoft OneDrive, or AWS S3 buckets for [Exfiltration to Cloud Storage](https://attack.mitre.org/techniques/T1567/002) or to [Upload Tool](https://attack.mitre.org/techniques/T1608/002)s. Cloud accounts can also be used in the acquisition of infrastructure, such as [Virtual Private Server](https://attack.mitre.org/techniques/T1583/003)s or [Serverless](https://attack.mitre.org/techniques/T1583/007) infrastructure. Establishing cloud accounts may allow adversaries to develop sophisticated capabilities without managing their own servers.(Citation: Awake Security C2 Cloud)

Creating [Cloud Accounts](https://attack.mitre.org/techniques/T1585/003) may also require adversaries to establish [Email Accounts](https://attack.mitre.org/techniques/T1585/002) to register with the cloud provider.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1585/003)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [C0060 - Operation AkaiRyū](../../../../Threat%20Intelligence/Campaigns/C0060%20-%20Operation%20AkaiRy%C5%AB.md) — During [Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060), [MirrorFace](https://attack.mitre.org/groups/G1054) established OneDrive accounts to host malicious payloads.(Citation: ESET MirrorFace 2025) [ESET MirrorFace 2025](https://www.welivesecurity.com/en/eset-research/operation-akairyu-mirrorface-invites-europe-expo-2025-revives-anel-backdoor/)
- [C0042 - Outer Space](../../../../Threat%20Intelligence/Campaigns/C0042%20-%20Outer%20Space.md) — During [Outer Space](https://attack.mitre.org/campaigns/C0042), [OilRig](https://attack.mitre.org/groups/G0049) created M365 email accounts to be used as part of C2.(Citation: ESET OilRig Campaigns Sep 2023) [ESET OilRig Campaigns Sep 2023](https://www.welivesecurity.com/en/eset-research/oilrigs-outer-space-juicy-mix-same-ol-rig-new-drill-pipes/)
- [G1046 - Storm-1811](../../../../Threat%20Intelligence/Groups/G1046%20-%20Storm-1811.md) — [Storm-1811](https://attack.mitre.org/groups/G1046) has created malicious accounts to enable activity via Microsoft Teams, typically spoofing various IT support and helpdesk themes.(Citation: Microsoft Storm-1811 2024) [Microsoft Storm-1811 2024](https://www.microsoft.com/en-us/security/blog/2024/05/15/threat-actors-misusing-quick-assist-in-social-engineering-attacks-leading-to-ransomware/)

## Detection strategies

- [DET0846 - Detection of Cloud Accounts](../../../../Defenses/Detection%20Strategies/DET0846%20-%20Detection%20of%20Cloud%20Accounts.md)

## Sources

- [Awake Security C2 Cloud](https://awakesecurity.com/blog/threat-hunting-series-detecting-command-control-in-the-cloud/)
