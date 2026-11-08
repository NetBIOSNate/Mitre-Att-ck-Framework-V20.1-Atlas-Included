# T1213.004 - Customer Relationship Management Software

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1213 - Data from Information Repositories](../README.md)

Adversaries may leverage Customer Relationship Management (CRM) software to mine valuable information. CRM software is used to assist organizations in tracking and managing customer interactions, as well as storing customer data.

Once adversaries gain access to a victim organization, they may mine CRM software for customer data. This may include personally identifiable information (PII) such as full names, emails, phone numbers, and addresses, as well as additional details such as purchase histories and IT support interactions. By collecting this data, an adversary may be able to send personalized [Phishing](https://attack.mitre.org/techniques/T1566) emails, engage in SIM swapping, or otherwise target the organization’s customers in ways that enable financial gain or the compromise of additional organizations.(Citation: Bleeping Computer US Cellular Hack 2022)(Citation: Bleeping Computer Mint Mobile Hack 2021)(Citation: Bleeping Computer Bank Hack 2020)

CRM software may be hosted on-premises or in the cloud. Information stored in these solutions may vary based on the specific instance or environment. Examples of CRM software include Microsoft Dynamics 365, Salesforce, Zoho, Zendesk, and HubSpot.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1213/004)

**Tactics**  [Collection](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Consider periodic review of accounts and privileges for critical and sensitive CRM data.
- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Consider implementing data retention policies to automate periodically archiving and/or deleting data that is no longer needed.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least-privilege. Consider implementing access control mechanisms that include both authentication and authorization.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored in CRM databases and acceptable handling of customer data. Only store customer information required for business operations.

## Procedure examples

- [C0059 - Salesforce Data Exfiltration](../../../../Threat%20Intelligence/Campaigns/C0059%20-%20Salesforce%20Data%20Exfiltration.md) — During [Salesforce Data Exfiltration](https://attack.mitre.org/campaigns/C0059), threat actors accessed and exfiltrated sensitive information from compromised Salesforce instances.(Citation: Google Salesforce JUN 2025) [Google Salesforce JUN 2025](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion)

## Detection strategies

- [DET0550 - Detecting Suspicious Access to CRM Data in SaaS Environments](../../../../Defenses/Detection%20Strategies/DET0550%20-%20Detecting%20Suspicious%20Access%20to%20CRM%20Data%20in%20SaaS%20Environments.md)

## Sources

- [Bleeping Computer Bank Hack 2020](https://www.bleepingcomputer.com/news/security/customer-owned-bank-informs-100k-of-breach-exposing-account-balance-pii/)
- [Bleeping Computer Mint Mobile Hack 2021](https://www.bleepingcomputer.com/news/security/mint-mobile-hit-by-a-data-breach-after-numbers-ported-data-accessed/)
- [Bleeping Computer US Cellular Hack 2022](https://www.bleepingcomputer.com/news/security/uscellular-discloses-data-breach-after-billing-system-hack/)
