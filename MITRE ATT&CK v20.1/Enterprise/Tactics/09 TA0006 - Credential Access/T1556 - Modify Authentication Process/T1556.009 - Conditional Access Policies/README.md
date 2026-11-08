# T1556.009 - Conditional Access Policies

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may disable or modify conditional access policies to enable persistent access to compromised accounts. Conditional access policies are additional verifications used by identity providers and identity and access management systems to determine whether a user should be granted access to a resource.

For example, in Entra ID, Okta, and JumpCloud, users can be denied access to applications based on their IP address, device enrollment status, and use of multi-factor authentication.(Citation: Microsoft Conditional Access)(Citation: JumpCloud Conditional Access Policies)(Citation: Okta Conditional Access Policies) In some cases, identity providers may also support the use of risk-based metrics to deny sign-ins based on a variety of indicators. In AWS and GCP, IAM policies can contain `condition` attributes that verify arbitrary constraints such as the source IP, the date the request was made, and the nature of the resources or regions being requested.(Citation: AWS IAM Conditions)(Citation: GCP IAM Conditions) These measures help to prevent compromised credentials from resulting in unauthorized access to data or resources, as well as limit user permissions to only those required. 

By modifying conditional access policies, such as adding additional trusted IP ranges, removing [Multi-Factor Authentication](https://attack.mitre.org/techniques/T1556/006) requirements, or allowing additional [Unused/Unsupported Cloud Regions](https://attack.mitre.org/techniques/T1535), adversaries may be able to ensure persistent access to accounts and circumvent defensive measures.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/009)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md), [Credential Access](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md)

## Procedure examples

- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has added additional trusted locations to Azure AD conditional access policies. (Citation: MSTIC Octo Tempest Operations October 2023) [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has registered their own MFA method, and leveraged a victim hybrid joined server to circumvent Conditional Access Policies.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Mitigations

- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit permissions to modify conditional access policies to only those required.

## Detection strategies

- [DET0030 - Detect Conditional Access Policy Modification in Identity and Cloud Platforms](../../../../Defenses/Detection%20Strategies/DET0030%20-%20Detect%20Conditional%20Access%20Policy%20Modification%20in%20Identity%20and%20Cloud%20Platforms.md)

## Sources

- [AWS IAM Conditions](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition.html)
- [GCP IAM Conditions](https://cloud.google.com/iam/docs/conditions-overview)
- [JumpCloud Conditional Access Policies](https://jumpcloud.com/support/get-started-conditional-access-policies)
- [Microsoft Conditional Access](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview)
- [Okta Conditional Access Policies](https://support.okta.com/help/s/article/Conditional-access-based-on-device-security-posture?language=en_US)
