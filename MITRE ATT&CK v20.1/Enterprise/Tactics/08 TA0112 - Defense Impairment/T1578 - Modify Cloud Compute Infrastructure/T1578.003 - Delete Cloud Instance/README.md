# T1578.003 - Delete Cloud Instance

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1578 - Modify Cloud Compute Infrastructure](../README.md)

An adversary may delete a cloud instance after they have performed malicious activities in an attempt to evade detection and remove evidence of their presence.  Deleting an instance or virtual machine can remove valuable forensic artifacts and other evidence of suspicious behavior if the instance is not recoverable.

An adversary may also [Create Cloud Instance](https://attack.mitre.org/techniques/T1578/002) and later terminate the instance after achieving their objectives.(Citation: Mandiant M-Trends 2020)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1578/003)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Detection strategies

- [DET0084 - Detection Strategy for Modify Cloud Compute Infrastructure: Delete Cloud Instance](../../../../Defenses/Detection%20Strategies/DET0084%20-%20Detection%20Strategy%20for%20Modify%20Cloud%20Compute%20Infrastructure%20-%20Delete%20Cloud%20Instance.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely check user permissions to ensure only the expected users have the capability to delete new instances.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit permissions for deleting new instances in accordance with least privilege. Organizations should limit the number of users within the organization with an IAM role that has administrative privileges, strive to reduce all permanent privileged role assignments, and conduct periodic entitlement reviews on IAM users, roles and policies.(Citation: Mandiant M-Trends 2020) [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)

## Procedure examples

- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has deleted the target's systems and resources in the cloud to trigger the organization's incident and crisis response process.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has conducted mass deletion of cloud data stores and resources from Azure subscriptions.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Sources

- [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)
