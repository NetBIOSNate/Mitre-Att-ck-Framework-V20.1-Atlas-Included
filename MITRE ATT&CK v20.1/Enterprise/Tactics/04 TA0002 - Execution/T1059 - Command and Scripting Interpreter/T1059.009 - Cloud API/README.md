# T1059.009 - Cloud API

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1059 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse cloud APIs to execute malicious commands. APIs available in cloud environments provide various functionalities and are a feature-rich method for programmatic access to nearly all aspects of a tenant. These APIs may be utilized through various methods such as command line interpreters (CLIs), in-browser Cloud Shells, [PowerShell](https://attack.mitre.org/techniques/T1059/001) modules like Azure for PowerShell(Citation: Microsoft - Azure PowerShell), or software developer kits (SDKs) available for languages such as [Python](https://attack.mitre.org/techniques/T1059/006).  

Cloud API functionality may allow for administrative access across all major services in a tenant such as compute, storage, identity and access management (IAM), networking, and security policies.

With proper permissions (often via use of credentials such as [Application Access Token](https://attack.mitre.org/techniques/T1550/001) and [Web Session Cookie](https://attack.mitre.org/techniques/T1550/004)), adversaries may abuse cloud APIs to invoke various functions that execute malicious actions. For example, CLI and PowerShell functionality may be accessed through binaries installed on cloud-hosted or on-premises hosts or accessed through a browser-based cloud shell offered by many cloud platforms (such as AWS, Azure, and GCP). These cloud shells are often a packaged unified environment to use CLI and/or scripting modules hosted as a container in the cloud environment.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1059/009)

**Tactics**  [Execution](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary utilized Cloud APIs for interacting with victim environments and exfiltrating data to include OpenAI’s GPT-4.1 API, and AWS API.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has leveraged the Microsoft Graph API to perform various actions across Azure and M365 environments. They have also utilized AADInternals PowerShell Modules to access the API (Citation: MSTIC Nobelium Toolset May 2021) [MSTIC Nobelium Toolset May 2021](https://www.microsoft.com/security/blog/2021/05/28/breaking-down-nobeliums-latest-early-stage-toolset/)
- [S9045 - BACKUPOSINT v9.0 APEX PREDATOR](../../../../Threat%20Intelligence/Software/Malware/S9045%20-%20BACKUPOSINT%20v9.0%20APEX%20PREDATOR.md) — [BACKUPOSINT v9.0 APEX PREDATOR](https://attack.mitre.org/software/S9045) has leveraged OpenAI’s GPT-4.1 API to analyze extracted data.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [S1091 - Pacu](../../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) leverages the AWS CLI for its operations.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has used the AWS Command Line Interface (CLI) for operations to include a variety of API calls, such as `ListBuckets`, `CreateBucket` and `DeleteBucket`.(Citation: Unit42KelleyVaya_BlingLibra_Aug2024) [Unit42KelleyVaya_BlingLibra_Aug2024](https://unit42.paloaltonetworks.com/shinyhunters-ransomware-extortion/)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has leveraged Cloud CLI to execute commands and exfiltrate data from compromised environments.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has leveraged AWS CLI to enumerate cloud environments with compromised credentials.(Citation: Talos TeamTNT) [Talos TeamTNT](https://blog.talosintelligence.com/2022/04/teamtnt-targeting-aws-alibaba.html)
- [S9009 - TruffleHog](../../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) has leveraged Cloud CLI in order to enumerate and gather credentials.(Citation: Github TruffleSecurity Trufflehog April 2025) [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Detection strategies

- [DET0078 - Behavioral Detection of Malicious Cloud API Scripting](../../../../Defenses/Detection%20Strategies/DET0078%20-%20Behavioral%20Detection%20of%20Malicious%20Cloud%20API%20Scripting.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control where appropriate to block use of PowerShell CmdLets or other host based resources to access cloud API resources.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Use of proper Identity and Access Management (IAM) with Role Based Access Control (RBAC) policies to limit actions administrators can perform and provide a history of administrative actions to detect unauthorized use and abuse.

## Sources

- [Microsoft - Azure PowerShell](https://github.com/Azure/azure-powershell)
