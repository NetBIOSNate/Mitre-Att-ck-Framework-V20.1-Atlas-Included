# T1484.002 - Trust Modification

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1484 - Domain or Tenant Policy Modification](../README.md)

Adversaries may add new domain trusts, modify the properties of existing domain trusts, or otherwise change the configuration of trust relationships between domains and tenants to evade defenses and/or elevate privileges.Trust details, such as whether or not user identities are federated, allow authentication and authorization properties to apply between domains or tenants for the purpose of accessing shared resources.(Citation: Microsoft - Azure AD Federation) These trust objects may include accounts, credentials, and other authentication material applied to servers, tokens, and domains.

Manipulating these trusts may allow an adversary to escalate privileges and/or evade defenses by modifying settings to add objects which they control. For example, in Microsoft Active Directory (AD) environments, this may be used to forge [SAML Tokens](https://attack.mitre.org/techniques/T1606/002) without the need to compromise the signing certificate to forge new credentials. Instead, an adversary can manipulate domain trusts to add their own signing certificate. An adversary may also convert an AD domain to a federated domain using Active Directory Federation Services (AD FS), which may enable malicious trust modifications such as altering the claim issuance rules to log in any valid set of credentials as a specified user.(Citation: AADInternals zure AD Federated Domain) 

An adversary may also add a new federated identity provider to an identity tenant such as Okta or AWS IAM Identity Center, which may enable the adversary to authenticate as any user of the tenant.(Citation: Okta Cross-Tenant Impersonation 2023) This may enable the threat actor to gain broad access into a variety of cloud-based services that leverage the identity tenant. For example, in AWS environments, an adversary that creates a new identity provider for an AWS Organization will be able to federate into all of the AWS Organization member accounts without creating identities for each of the member accounts.(Citation: AWS re Inforce Trust Mod)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1484/002)

**Tactics**  [Privilege Escalation](../../README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md)

**Platforms**  [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can create a backdoor by converting a domain to a federated domain which will be able to authenticate any user across the tenant. [AADInternals](https://attack.mitre.org/software/S0677) can also modify DesktopSSO information.(Citation: AADInternals Documentation)(Citation: Azure AD Federation Vulnerability) [AADInternals Documentation](https://o365blog.com/aadinternals) · [Azure AD Federation Vulnerability](https://o365blog.com/post/federation-vulnerability/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) adds a federated identity provider to the victim’s SSO tenant and activates automatic account linking.(Citation: CISA Scattered Spider Advisory November 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) changed domain federation trust settings using Azure AD administrative permissions to configure the domain to accept authorization tokens signed by their own SAML signing certificate.(Citation: Secureworks IRON RITUAL Profile)(Citation: Microsoft 365 Defender Solorigate) [Microsoft 365 Defender Solorigate](https://www.microsoft.com/security/blog/2020/12/28/using-microsoft-365-defender-to-coordinate-protection-against-solorigate/) · [Secureworks IRON RITUAL Profile](https://www.sophos.com/en-us/threat-profiles/iron-ritual)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) created a new federated domain within the victim Microsoft Entra tenant using Global Administrator level access to establish a persistent backdoor for later use.(Citation: Microsoft Storm-501 Sabbath Ransomware Embargo September 2024)(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-501 Sabbath Ransomware Embargo September 2024](https://www.microsoft.com/en-us/security/blog/2024/09/26/storm-0501-ransomware-attacks-expanding-to-hybrid-cloud-environments/) · [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Mitigations

- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Use the principal of least privilege and protect administrative access to domain trusts and identity tenants.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — In cloud environments, limit permissions to create new identity providers to only those accounts that require them. In AWS environments, consider using Service Control policies to limit the use of API calls such as `CreateSAMLProvider` or `CreateOpenIDConnectProvider`.

## Detection strategies

- [DET0458 - Detection of Trust Relationship Modifications in Domain or Tenant Policies](../../../../Defenses/Detection%20Strategies/DET0458%20-%20Detection%20of%20Trust%20Relationship%20Modifications%20in%20Domain%20or%20Tenant%20Policies.md)

## Sources

- [AWS re Inforce Trust Mod](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/events/approved/reinforce-2025/reinforce/2024/slides/TDR432_New-tactics-and-techniques-for-proactive-threat-detection.pdf)
- [AADInternals zure AD Federated Domain](https://o365blog.com/post/federation-vulnerability/)
- [Microsoft - Azure AD Federation](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-fed)
- [Okta Cross-Tenant Impersonation 2023](https://sec.okta.com/articles/2023/08/cross-tenant-impersonation-prevention-and-detection)
