# T1136.003 - Cloud Account

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1136 - Create Account](../README.md)

Adversaries may create a cloud account to maintain access to victim systems. With a sufficient level of access, such accounts may be used to establish secondary credentialed access that does not require persistent remote access tools to be deployed on the system.(Citation: Microsoft O365 Admin Roles)(Citation: Microsoft Support O365 Add Another Admin, October 2019)(Citation: AWS Create IAM User)(Citation: GCP Create Cloud Identity Users)(Citation: Microsoft Azure AD Users)

In addition to user accounts, cloud accounts may be associated with services. Cloud providers handle the concept of service accounts in different ways. In Azure, service accounts include service principals and managed identities, which can be linked to various resources such as OAuth applications, serverless functions, and virtual machines in order to grant those resources permissions to perform various activities in the environment.(Citation: Microsoft Entra ID Service Principals) In GCP, service accounts can also be linked to specific resources, as well as be impersonated by other accounts for [Temporary Elevated Cloud Access](https://attack.mitre.org/techniques/T1548/005).(Citation: GCP Service Accounts) While AWS has no specific concept of service accounts, resources can be directly granted permission to assume roles.(Citation: AWS Instance Profiles)(Citation: AWS Lambda Execution Role)

Adversaries may create accounts that only have access to specific cloud services, which can reduce the chance of detection.

Once an adversary has created a cloud account, they can then manipulate that account to ensure persistence and allow access to additional resources - for example, by adding [Additional Cloud Credentials](https://attack.mitre.org/techniques/T1098/001) or assigning [Additional Cloud Roles](https://attack.mitre.org/techniques/T1098/003).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1136/003)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [SaaS](../../../../Platforms/SaaS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can create new Azure AD users.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) can create new users through Azure AD.(Citation: MSTIC Nobelium Oct 2021) [MSTIC Nobelium Oct 2021](https://www.microsoft.com/security/blog/2021/10/25/nobelium-targeting-delegated-administrative-privileges-to-facilitate-broader-attacks/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has created global admin accounts in the targeted organization's cloud instances to gain persistence.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts.
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Configure access controls and firewalls to limit access to critical systems and domain controllers. Most cloud environments support separate virtual private cloud (VPC) instances that enable further segmentation of cloud systems.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit the number of accounts with permissions to create other accounts. Do not allow privileged accounts to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.

## Detection strategies

- [DET0319 - Detection Strategy for T1136.003 - Cloud Account Creation across IaaS, IdP, SaaS, Office](../../../../Defenses/Detection%20Strategies/DET0319%20-%20Detection%20Strategy%20for%20T1136.003%20-%20Cloud%20Account%20Creation%20across%20IaaS%2C%20IdP%2C%20SaaS%2C%20Off.md)

## Sources

- [Microsoft O365 Admin Roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles?view=o365-worldwide)
- [AWS Create IAM User](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html)
- [AWS Lambda Execution Role](https://docs.aws.amazon.com/lambda/latest/dg/lambda-intro-execution-role.html)
- [AWS Instance Profiles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2_instance-profiles.html)
- [GCP Create Cloud Identity Users](https://support.google.com/cloudidentity/answer/7332836?hl=en&ref_topic=7558554)
- [GCP Service Accounts](https://cloud.google.com/iam/docs/service-account-overview)
- [Microsoft Azure AD Users](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Microsoft Entra ID Service Principals](https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals?tabs=browser)
- [Microsoft Support O365 Add Another Admin, October 2019](https://support.office.com/en-us/article/add-another-admin-f693489f-9f55-4bd0-a637-a81ce93de22d)
