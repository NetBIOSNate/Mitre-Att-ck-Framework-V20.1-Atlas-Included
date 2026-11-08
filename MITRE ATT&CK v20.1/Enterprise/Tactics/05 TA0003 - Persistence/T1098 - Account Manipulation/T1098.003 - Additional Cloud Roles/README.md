# T1098.003 - Additional Cloud Roles

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1098 - Account Manipulation](../README.md)

An adversary may add additional roles or permissions to an adversary-controlled cloud account to maintain persistent access to a tenant. For example, adversaries may update IAM policies in cloud-based environments or add a new global administrator in Office 365 environments.(Citation: AWS IAM Policies and Permissions)(Citation: Google Cloud IAM Policies)(Citation: Microsoft Support O365 Add Another Admin, October 2019)(Citation: Microsoft O365 Admin Roles) With sufficient permissions, a compromised account can gain almost unlimited access to data and settings (including the ability to reset the passwords of other admins).(Citation: Expel AWS Attacker)(Citation: Microsoft O365 Admin Roles) 

This account modification may immediately follow [Create Account](https://attack.mitre.org/techniques/T1136) or other malicious account activity. Adversaries may also modify existing [Valid Accounts](https://attack.mitre.org/techniques/T1078) that they have compromised. This could lead to privilege escalation, particularly if the roles added allow for lateral movement to additional accounts.

For example, in AWS environments, an adversary with appropriate permissions may be able to use the <code>CreatePolicyVersion</code> API to define a new version of an IAM policy or the <code>AttachUserPolicy</code> API to attach an IAM policy with additional or distinct permissions to a compromised user account.(Citation: Rhino Security Labs AWS Privilege Escalation)

In some cases, adversaries may add roles to adversary-controlled accounts outside the victim cloud tenant. This allows these external accounts to perform actions inside the victim tenant without requiring the adversary to [Create Account](https://attack.mitre.org/techniques/T1136) or modify a victim-owned account.(Citation: Invictus IR DangerDev 2024)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098/003)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure that all accounts use the least privileges they require. In Azure AD environments, consider using Privileged Identity Management (PIM) to define roles that require two or more approvals before assignment to users.(Citation: Microsoft Requests for Azure AD Roles in Privileged Identity Management) [Microsoft Requests for Azure AD Roles in Privileged Identity Management](https://learn.microsoft.com/en-us/azure/active-directory/privileged-identity-management/azure-ad-pim-approval-workflow)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that low-privileged user accounts do not have permissions to add permissions to accounts or update IAM policies.

## Procedure examples

- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) used IAM manipulation to gain persistence and to assume or elevate privileges.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has added the global admin role to accounts they have created in the targeted organization's cloud instances.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has assigned user access admin roles in order to gain Tenant Root Group management permissions in Azure.(Citation: MSTIC Octo Tempest Operations October 2023) [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) granted `company administrator` privileges to a newly created service principle.(Citation: CrowdStrike StellarParticle January 2022) [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has elevated their access to Azure resources using `Microsoft.Authorization/elevateAccess/action` and `Microsoft.Authorization/roleAssignments/write` operations to gain User Access Administrator and Owner Azure roles over the victims’ Azure subscriptions.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Detection strategies

- [DET0277 - Detection Strategy for Role Addition to Cloud Accounts](../../../../Defenses/Detection%20Strategies/DET0277%20-%20Detection%20Strategy%20for%20Role%20Addition%20to%20Cloud%20Accounts.md)

## Sources

- [Expel AWS Attacker](https://expel.com/blog/incident-report-from-cli-to-console-chasing-an-attacker-in-aws/)
- [Microsoft O365 Admin Roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles?view=o365-worldwide)
- [AWS IAM Policies and Permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
- [Google Cloud IAM Policies](https://cloud.google.com/iam/docs/policies)
- [Invictus IR DangerDev 2024](https://www.invictus-ir.com/news/the-curious-case-of-dangerdev-protonmail-me)
- [Microsoft Support O365 Add Another Admin, October 2019](https://support.office.com/en-us/article/add-another-admin-f693489f-9f55-4bd0-a637-a81ce93de22d)
- [Rhino Security Labs AWS Privilege Escalation](https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/)
