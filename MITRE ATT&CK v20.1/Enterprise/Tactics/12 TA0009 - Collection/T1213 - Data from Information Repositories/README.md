# T1213 - Data from Information Repositories

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may leverage information repositories to mine valuable information. Information repositories are tools that allow for storage of information, typically to facilitate collaboration or information sharing between users, and can store a wide variety of data that may aid adversaries in further objectives, such as Credential Access, Lateral Movement, or Defense Evasion, or direct access to the target information. Adversaries may also abuse external sharing features to share sensitive documents with recipients outside of the organization (i.e., [Transfer Data to Cloud Account](https://attack.mitre.org/techniques/T1537)). 

The following is a brief list of example information that may hold potential value to an adversary and may also be found on an information repository:

* Policies, procedures, and standards
* Physical / logical network diagrams
* System architecture diagrams
* Technical system documentation
* Testing / development credentials (i.e., [Unsecured Credentials](https://attack.mitre.org/techniques/T1552)) 
* Work / project schedules
* Source code snippets
* Links to network shares and other internal resources
* Contact or other sensitive information about business partners and customers, including personally identifiable information (PII) 

Information stored in a repository may vary based on the specific instance or environment. Specific common information repositories include the following:

* Storage services such as IaaS databases, enterprise databases, and more specialized platforms such as customer relationship management (CRM) databases 
* Collaboration platforms such as SharePoint, Confluence, and code repositories
* Messaging platforms such as Slack and Microsoft Teams 

In some cases, information repositories have been improperly secured, typically by unintentionally allowing for overly-broad access by all users or even public access to unauthenticated users. This is particularly common with cloud-native or cloud-hosted services, such as AWS Relational Database Service (RDS), Redis, or ElasticSearch.(Citation: Mitiga)(Citation: TrendMicro Exposed Redis 2020)(Citation: Cybernews Reuters Leak 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1213)

**Tactics**  [Collection](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), [SaaS](../../../Platforms/SaaS.md), [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Sub-techniques

- [T1213.003 - Code Repositories](T1213.003%20-%20Code%20Repositories/README.md)
- [T1213.001 - Confluence](T1213.001%20-%20Confluence/README.md)
- [T1213.004 - Customer Relationship Management Software](T1213.004%20-%20Customer%20Relationship%20Management%20Software/README.md)
- [T1213.006 - Databases](T1213.006%20-%20Databases/README.md)
- [T1213.005 - Messaging Applications](T1213.005%20-%20Messaging%20Applications/README.md)
- [T1213.002 - Sharepoint](T1213.002%20-%20Sharepoint/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Consider periodic review of accounts and privileges for critical and sensitive repositories. Ensure that repositories such as cloud-hosted databases are not unintentionally exposed to the public, and that security groups assigned to them permit only necessary and authorized hosts.(Citation: AWS DB VPC) [AWS DB VPC](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_VPC.WorkingWithRDSInstanceinaVPC.html)
- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Encrypt data stored at rest in databases.
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use two or more pieces of evidence to authenticate to a system; such as username and password in addition to a token from a physical smart card or token generator.
- [M1060 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M1060%20-%20Out-of-Band%20Communications%20Channel.md) — Create plans for leveraging a secure out-of-band communications channel, rather than existing in-network chat applications, in case of a security incident.(Citation: TrustedSec OOB Communications) [TrustedSec OOB Communications](https://trustedsec.com/blog/to-oob-or-not-to-oob-why-out-of-band-communications-are-essential-for-incident-response)
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Consider implementing data retention policies to automate periodically archiving and/or deleting data that is no longer needed.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least-privilege. Consider implementing access control mechanisms that include both authentication and authorization.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored in repositories.

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code to gather and exfiltrate data stored in victim repositories to include sensitive government and civilian records.(Citation: AI-Mexico-Govt-Breach)(Citation: AI-Mexico-Govt-Compromise) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf) · [AI-Mexico-Govt-Compromise](https://5943619.hs-sites.com/hubfs/116-Whitepapers/dragos-2026-ai-mexico-water-attack-intel-brief.pdf)
- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has collected files from various information repositories.(Citation: Cybersecurity Advisory GRU Brute Force Campaign July 2021) [Cybersecurity Advisory GRU Brute Force Campaign July 2021](https://media.defense.gov/2021/Jul/01/2002753896/-1/-1/1/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21.PDF)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has gathered data from internal service ticketing systems to include credentials.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [S1148 - Raccoon Stealer](../../../Threat%20Intelligence/Software/Malware/S1148%20-%20Raccoon%20Stealer.md) — [Raccoon Stealer](https://attack.mitre.org/software/S1148) gathers information from repositories associated with cryptocurrency wallets and the Telegram messaging service.(Citation: Sekoia Raccoon2 2022) [Sekoia Raccoon2 2022](https://blog.sekoia.io/raccoon-stealer-v2-part-2-in-depth-analysis/)
- [C0024 - SolarWinds Compromise](../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) accessed victims' internal knowledge repositories (wikis) to view sensitive corporate information on products, services, and internal business operations.(Citation: CrowdStrike StellarParticle January 2022) [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/)
- [S1196 - Troll Stealer](../../../Threat%20Intelligence/Software/Malware/S1196%20-%20Troll%20Stealer.md) — [Troll Stealer](https://attack.mitre.org/software/S1196) gathers information from the Government Public Key Infrastructure (GPKI) folder, associated with South Korean government public key infrastructure, on infected systems.(Citation: S2W Troll Stealer 2024)(Citation: Symantec Troll Stealer 2024) [S2W Troll Stealer 2024](https://medium.com/s2wblog/kimsuky-disguised-as-a-korean-company-signed-with-a-valid-certificate-to-distribute-troll-stealer-cfa5d54314e2) · [Symantec Troll Stealer 2024](https://www.security.com/threat-intelligence/springtail-kimsuky-backdoor-espionage)

## Detection strategies

- [DET0413 - Abuse of Information Repositories for Data Collection](../../../Defenses/Detection%20Strategies/DET0413%20-%20Abuse%20of%20Information%20Repositories%20for%20Data%20Collection.md)

## Sources

- [Mitiga](https://www.mitiga.io/blog/how-mitiga-found-pii-in-exposed-amazon-rds-snapshots)
- [Atlassian Confluence Logging](https://confluence.atlassian.com/confkb/how-to-enable-user-access-logging-182943.html)
- [TrendMicro Exposed Redis 2020](https://www.trendmicro.com/en_us/research/20/d/exposed-redis-instances-abused-for-remote-code-execution-cryptocurrency-mining.html)
- [Microsoft SharePoint Logging](https://support.office.com/en-us/article/configure-audit-settings-for-a-site-collection-a9920c97-38c0-44f2-8bcb-4cf1e2ae22d2)
- [Sharepoint Sharing Events](https://docs.microsoft.com/en-us/microsoft-365/compliance/use-sharing-auditing?view=o365-worldwide#sharepoint-sharing-events)
- [Cybernews Reuters Leak 2022](https://cybernews.com/security/thomson-reuters-leaked-terabytes-sensitive-data/)
