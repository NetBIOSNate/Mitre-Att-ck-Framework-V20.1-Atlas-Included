# T1526 - Cloud Service Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

An adversary may attempt to enumerate the cloud services running on a system after gaining access. These methods can differ from platform-as-a-service (PaaS), to infrastructure-as-a-service (IaaS), or software-as-a-service (SaaS). Many services exist throughout the various cloud providers and can include Continuous Integration and Continuous Delivery (CI/CD), Lambda Functions, Entra ID, etc. They may also include security services, such as AWS GuardDuty and Microsoft Defender for Cloud, and logging services, such as AWS CloudTrail and Google Cloud Audit Logs.

Adversaries may attempt to discover information about the services enabled throughout the environment. Azure tools and APIs, such as the Microsoft Graph API and Azure Resource Manager API, can enumerate resources and services, including applications, management groups, resources and policy definitions, and their relationships that are accessible by an identity.(Citation: Azure - Resource Manager API)(Citation: Azure AD Graph API)

For example, Stormspotter is an open source tool for enumerating and constructing a graph for Azure resources and services, and Pacu is an open source AWS exploitation framework that supports several methods for discovering cloud services.(Citation: Azure - Stormspotter)(Citation: GitHub Pacu)

Adversaries may use the information gained to shape follow-on behaviors, such as targeting data or credentials from enumerated services or evading identified defenses through [Disable or Modify Tools](https://attack.mitre.org/techniques/T1685) or [Disable or Modify Cloud Log](https://attack.mitre.org/techniques/T1685/002).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1526)

**Tactics**  [Discovery](../README.md)

**Platforms**  [IaaS](../../../Platforms/IaaS.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md)

## Procedure examples

- [S0677 - AADInternals](../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can enumerate information about a variety of cloud services, such as Office 365 and Sharepoint instances or OpenID Configurations.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary identified and connected to victim AWS databases and systems through the use of client tools.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can enumerate AWS services, such as CloudTrail and CloudWatch.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [S0684 - ROADTools](../../../Threat%20Intelligence/Software/Tools/S0684%20-%20ROADTools.md) — [ROADTools](https://attack.mitre.org/software/S0684) can enumerate Azure AD applications and service principals.(Citation: Roadtools) [Roadtools](https://dirkjanm.io/introducing-roadtools-and-roadrecon-azure-ad-exploration-framework/)
- [G1053 - Storm-0501](../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has discovered the victim environment’s protections to include Azure policies, resource locks, and Azure Storage immutability policies.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)
- [S9041 - TeamPCP Cloud Stealer](../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can search GitHub for Actions runner processes.(Citation: Aqua Security Blog Trivy Compromise APR 2026)(Citation: Aqua Security Trivy Compromise MAR 2026)(Citation: Wiz Trivy Compromise MAR 2026)(Citation: Wiz TeamPCP KICS MAR 2026) [Aqua Security Trivy Compromise MAR 2026](https://github.com/aquasecurity/trivy/security/advisories/GHSA-69fq-xp46-6x23) · [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know) · [Wiz Trivy Compromise MAR 2026](https://www.wiz.io/blog/trivy-compromised-teampcp-supply-chain-attack) · [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action)
- [S9009 - TruffleHog](../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) has the ability to scan code repositories and CI/CD platforms.(Citation: Black Hills Information Security TruffleHog January 2024)(Citation: Github TruffleSecurity Trufflehog April 2025) [Black Hills Information Security TruffleHog January 2024](https://www.blackhillsinfosec.com/rooting-for-secrets-with-trufflehog/) · [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Detection strategies

- [DET0402 - Detection Strategy for Cloud Service Discovery](../../../Defenses/Detection%20Strategies/DET0402%20-%20Detection%20Strategy%20for%20Cloud%20Service%20Discovery.md)

## Sources

- [Azure AD Graph API](https://docs.microsoft.com/en-us/previous-versions/azure/ad/graph/howto/azure-ad-graph-api-operations-overview)
- [Azure - Resource Manager API](https://docs.microsoft.com/en-us/rest/api/resources/)
- [Azure - Stormspotter](https://github.com/Azure/Stormspotter)
- [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
