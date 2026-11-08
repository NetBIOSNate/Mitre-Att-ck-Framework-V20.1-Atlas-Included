# T1578.005 - Modify Cloud Compute Configurations

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1578 - Modify Cloud Compute Infrastructure](../README.md)

Adversaries may modify settings that directly affect the size, locations, and resources available to cloud compute infrastructure in order to evade defenses. These settings may include service quotas, subscription associations, tenant-wide policies, or other configurations that impact available compute. Such modifications may allow adversaries to abuse the victim’s compute resources to achieve their goals, potentially without affecting the execution of running instances and/or revealing their activities to the victim.

For example, cloud providers often limit customer usage of compute resources via quotas. Customers may request adjustments to these quotas to support increased computing needs, though these adjustments may require approval from the cloud provider. Adversaries who compromise a cloud environment may similarly request quota adjustments in order to support their activities, such as enabling additional [Resource Hijacking](https://attack.mitre.org/techniques/T1496) without raising suspicion by using up a victim’s entire quota.(Citation: Microsoft Cryptojacking 2023) Adversaries may also increase allowed resource usage by modifying any tenant-wide policies that limit the sizes of deployed virtual machines.(Citation: Microsoft Azure Policy)

Adversaries may also modify settings that affect where cloud resources can be deployed, such as enabling [Unused/Unsupported Cloud Regions](https://attack.mitre.org/techniques/T1535).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1578/005)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely monitor user permissions to ensure only the expected users have the capability to request quota adjustments or modify tenant-level compute settings.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit permissions to request quotas adjustments or modify tenant-level compute setting to only those required.

## Detection strategies

- [DET0492 - Detection Strategy for Modify Cloud Compute Infrastructure: Modify Cloud Compute Configurations](../../../../Defenses/Detection%20Strategies/DET0492%20-%20Detection%20Strategy%20for%20Modify%20Cloud%20Compute%20Infrastructure%20-%20Modify%20Cloud%20Compute%20Con.md)

## Sources

- [Microsoft Cryptojacking 2023](https://www.microsoft.com/en-us/security/blog/2023/07/25/cryptojacking-understanding-and-defending-against-cloud-compute-resource-abuse/)
- [Microsoft Azure Policy](https://learn.microsoft.com/en-us/azure/governance/policy/samples/built-in-policies#compute)
