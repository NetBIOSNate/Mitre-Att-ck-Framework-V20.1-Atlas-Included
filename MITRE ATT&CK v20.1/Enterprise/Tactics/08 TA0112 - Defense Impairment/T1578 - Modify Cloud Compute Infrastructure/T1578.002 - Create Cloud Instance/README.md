# T1578.002 - Create Cloud Instance

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1578 - Modify Cloud Compute Infrastructure](../README.md)

An adversary may create a new instance or virtual machine (VM) within the compute service of a cloud account to evade defenses. Creating a new instance may allow an adversary to bypass firewall rules and permissions that exist on instances currently residing within an account. An adversary may [Create Snapshot](https://attack.mitre.org/techniques/T1578/001) of one or more volumes in an account, create a new instance, mount the snapshots, and then apply a less restrictive security policy to collect [Data from Local System](https://attack.mitre.org/techniques/T1005) or for [Remote Data Staging](https://attack.mitre.org/techniques/T1074/002).(Citation: Mandiant M-Trends 2020)

Creating a new instance may also allow an adversary to carry out malicious activity within an environment without affecting the execution of current running instances.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1578/002)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Procedure examples

- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) used access to the victim's Azure tenant to create Azure VMs.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has created new virtual machines within the target's cloud environment after leveraging credential access to cloud assets.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has created Amazon EC2 instances within the victim's environment.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)

## Detection strategies

- [DET0449 - Detection Strategy for Modify Cloud Compute Infrastructure: Create Cloud Instance](../../../../Defenses/Detection%20Strategies/DET0449%20-%20Detection%20Strategy%20for%20Modify%20Cloud%20Compute%20Infrastructure%20-%20Create%20Cloud%20Instance.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely check user permissions to ensure only the expected users have the capability to create new instances.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit permissions for creating new instances in accordance with least privilege. Organizations should limit the number of users within the organization with an IAM role that has administrative privileges, strive to reduce all permanent privileged role assignments, and conduct periodic entitlement reviews on IAM users, roles and policies.(Citation: Mandiant M-Trends 2020) [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)

## Sources

- [Mandiant M-Trends 2020](https://www.mandiant.com/sites/default/files/2021-09/mtrends-2020.pdf)
