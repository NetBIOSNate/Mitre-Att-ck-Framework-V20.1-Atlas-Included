# T1578 - Modify Cloud Compute Infrastructure

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

An adversary may attempt to modify a cloud account's compute service infrastructure to evade defenses. A modification to the compute service infrastructure can include the creation, deletion, or modification of one or more components such as compute instances, virtual machines, and snapshots.

Permissions gained from the modification of infrastructure components may bypass restrictions that prevent access to existing infrastructure. Modifying infrastructure components may also allow an adversary to evade detection and remove evidence of their presence.(Citation: Mandiant M-Trends 2020)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1578)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md)

## Sub-techniques

- [T1578.002 - Create Cloud Instance](T1578.002%20-%20Create%20Cloud%20Instance/README.md)
- [T1578.001 - Create Snapshot](T1578.001%20-%20Create%20Snapshot/README.md)
- [T1578.003 - Delete Cloud Instance](T1578.003%20-%20Delete%20Cloud%20Instance/README.md)
- [T1578.005 - Modify Cloud Compute Configurations](T1578.005%20-%20Modify%20Cloud%20Compute%20Configurations/README.md)
- [T1578.004 - Revert Cloud Instance](T1578.004%20-%20Revert%20Cloud%20Instance/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely monitor user permissions to ensure only the expected users have the capability to modify cloud compute infrastructure components.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit permissions for creating, deleting, and otherwise altering compute components in accordance with least privilege. Organizations should limit the number of users within the organization with an IAM role that has administrative privileges, strive to reduce all permanent privileged role assignments, and conduct periodic entitlement reviews on IAM users, roles and policies.(Citation: Mandiant M-Trends 2020) [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)

## Detection strategies

- [DET0308 - Detection Strategy for Modify Cloud Compute Infrastructure](../../../Defenses/Detection%20Strategies/DET0308%20-%20Detection%20Strategy%20for%20Modify%20Cloud%20Compute%20Infrastructure.md)

## Sources

- [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)
