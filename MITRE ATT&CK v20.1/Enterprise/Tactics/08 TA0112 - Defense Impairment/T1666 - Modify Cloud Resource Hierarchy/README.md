# T1666 - Modify Cloud Resource Hierarchy

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may attempt to modify hierarchical structures in infrastructure-as-a-service (IaaS) environments in order to evade defenses.  

IaaS environments often group resources into a hierarchy, enabling improved resource management and application of policies to relevant groups. Hierarchical structures differ among cloud providers. For example, in AWS environments, multiple accounts can be grouped under a single organization, while in Azure environments, multiple subscriptions can be grouped under a single management group.(Citation: AWS Organizations)(Citation: Microsoft Azure Resources)

Adversaries may add, delete, or otherwise modify resource groups within an IaaS hierarchy. For example, in Azure environments, an adversary who has gained access to a Global Administrator account may create new subscriptions in which to deploy resources. They may also engage in subscription hijacking by transferring an existing pay-as-you-go subscription from a victim tenant to an adversary-controlled tenant. This will allow the adversary to use the victim’s compute resources without generating logs on the victim tenant.(Citation: Microsoft Peach Sandstorm 2023)(Citation: Microsoft Subscription Hijacking 2022)

In AWS environments, adversaries with appropriate permissions in a given account may call the `LeaveOrganization` API, causing the account to be severed from the AWS Organization to which it was tied and removing any Service Control Policies, guardrails, or restrictions imposed upon it by its former Organization. Alternatively, adversaries may call the `CreateAccount` API in order to create a new account within an AWS Organization. This account will use the same payment methods registered to the payment account but may not be subject to existing detections or Service Control Policies.(Citation: AWS re Inforce Trust Mod)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1666)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md)

## Detection strategies

- [DET0155 - Detection Strategy for Modify Cloud Resource Hierarchy](../../../Defenses/Detection%20Strategies/DET0155%20-%20Detection%20Strategy%20for%20Modify%20Cloud%20Resource%20Hierarchy.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically audit resource groups in the cloud management console to ensure that only expected items exist, especially close to the top of the hierarchy (e.g., AWS accounts and Azure subscriptions). Typically, top-level accounts (such as the AWS management account) should not contain any workloads or resources.(Citation: AWS Management Account Best Practices) [AWS Management Account Best Practices](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_best-practices_mgmt-acct.html)
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — In Azure environments, consider setting a policy to block subscription transfers.(Citation: Azure Subscription Policies) In AWS environments, consider using Service Control Policies to prevent the use of the `LeaveOrganization` API call.(Citation: AWS RE:Inforce Threat Detection 2024) [AWS RE:Inforce Threat Detection 2024](https://reinforce.awsevents.com/content/dam/reinforce/2024/slides/TDR432_New-tactics-and-techniques-for-proactive-threat-detection.pdf) · [Azure Subscription Policies](https://learn.microsoft.com/en-us/azure/cost-management-billing/manage/manage-azure-subscription-policy)
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit permissions to add, delete, or modify resource groups to only those required.

## Sources

- [AWS re Inforce Trust Mod](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/events/approved/reinforce-2025/reinforce/2024/slides/TDR432_New-tactics-and-techniques-for-proactive-threat-detection.pdf)
- [AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started_concepts.html)
- [Microsoft Subscription Hijacking 2022](https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/hunt-for-compromised-azure-subscriptions-using-microsoft/ba-p/3607121)
- [Microsoft Azure Resources](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-setup-guide/organize-resources)
- [Microsoft Peach Sandstorm 2023](https://www.microsoft.com/en-us/security/blog/2023/09/14/peach-sandstorm-password-spray-campaigns-enable-intelligence-collection-at-high-value-targets/)
