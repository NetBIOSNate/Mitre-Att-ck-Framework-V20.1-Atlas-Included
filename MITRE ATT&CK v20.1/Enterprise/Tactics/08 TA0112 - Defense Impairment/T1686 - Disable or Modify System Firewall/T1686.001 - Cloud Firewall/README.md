# T1686.001 - Cloud Firewall

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1686 - Disable or Modify System Firewall](../README.md)

Adversaries may disable or modify a firewall within a cloud environment to bypass controls that limit access to cloud resources.

Cloud environments typically utilize restrictive security groups and firewall rules that only allow network activity from trusted IP addresses via expected ports and protocols. An adversary with appropriate permissions may introduce new firewall rules or policies to allow access into a victim cloud environment and/or move laterally from the cloud control plane to the data plane.

For example, an adversary may use a script or utility that creates new ingress rules in existing security groups (or creates new security groups entirely) to allow any TCP/IP connectivity to a cloud-hosted instance. They may also remove networking limitations to support traffic associated with malicious activity (such as cryptomining).(Citation: Palo Alto Unit 42 Compromised Cloud Compute Credentials 2022)(Citation: Expel AWS)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1686/001)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely check account role permissions to ensure only expected users and roles have permission to modify cloud firewalls.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure least privilege principles are applied to Identity and Access Management (IAM) security policies.(Citation: Expel IO Evil in AWS) [Expel IO Evil in AWS](https://expel.io/blog/finding-evil-in-aws/)

## Procedure examples

- [S1091 - Pacu](../../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can allowlist IP addresses in AWS GuardDuty.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)

## Detection strategies

- [DET0424 - Detection Strategy for Disable or Modify Cloud Firewall](../../../../Defenses/Detection%20Strategies/DET0424%20-%20Detection%20Strategy%20for%20Disable%20or%20Modify%20Cloud%20Firewall.md)

## Sources

- [Expel AWS](https://expel.com/blog/finding-evil-in-aws/)
- [Palo Alto Unit 42 Compromised Cloud Compute Credentials 2022](https://unit42.paloaltonetworks.com/compromised-cloud-compute-credentials/)
