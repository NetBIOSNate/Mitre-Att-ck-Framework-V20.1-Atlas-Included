# T1538 - Cloud Service Dashboard

[Enterprise](../../../README.md) / [Discovery](../README.md)

An adversary may use a cloud service dashboard GUI with stolen credentials to gain useful information from an operational cloud environment, such as specific services, resources, and features. For example, the GCP Command Center can be used to view all assets, review findings of potential security risks, and run additional queries, such as finding public IP addresses and open ports.(Citation: Google Command Center Dashboard)

Depending on the configuration of the environment, an adversary may be able to enumerate more information via the graphical dashboard than an API. This also allows the adversary to gain information without manually making any API requests.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1538)

**Tactics**  [Discovery](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md), [SaaS](../../../Platforms/SaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md)

## Detection strategies

- [DET0291 - Detection of Cloud Service Dashboard Usage via GUI-Based Cloud Access](../../../Defenses/Detection%20Strategies/DET0291%20-%20Detection%20of%20Cloud%20Service%20Dashboard%20Usage%20via%20GUI-Based%20Cloud%20Access.md)

## Procedure examples

- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) abused AWS Systems Manager Inventory to identify targets on the compromised network prior to lateral movement.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)

## Mitigations

- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least-privilege by limiting dashboard visibility to only the resources required. This may limit the discovery value of the dashboard in the event of a compromised account.

## Sources

- [AWS Console Sign-in Events](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-aws-console-sign-in-events.html)
- [Google Command Center Dashboard](https://cloud.google.com/security-command-center/docs/quickstart-scc-dashboard)
