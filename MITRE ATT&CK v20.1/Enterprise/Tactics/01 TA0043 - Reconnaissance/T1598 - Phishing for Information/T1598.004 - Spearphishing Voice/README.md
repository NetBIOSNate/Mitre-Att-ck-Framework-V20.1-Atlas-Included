# T1598.004 - Spearphishing Voice

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1598 - Phishing for Information](../README.md)

Adversaries may use voice communications to elicit sensitive information that can be used during targeting. Spearphishing for information is an attempt to trick targets into divulging information, frequently credentials or other actionable information. Spearphishing for information frequently involves social engineering techniques, such as posing as a source with a reason to collect information (ex: [Impersonation](https://attack.mitre.org/techniques/T1684/001)) and/or creating a sense of urgency or alarm for the recipient.

All forms of phishing are electronically delivered social engineering. In this scenario, adversaries use phone calls to elicit sensitive information from victims. Known as voice phishing (or "vishing"), these communications can be manually executed by adversaries, hired call centers, or even automated via robocalls. Voice phishers may spoof their phone number while also posing as a trusted entity, such as a business partner or technical support staff.(Citation: BOA Telephone Scams)

Victims may also receive phishing messages that direct them to call a phone number ("callback phishing") where the adversary attempts to collect confidential information.(Citation: Avertium callback phishing)

Adversaries may also use information from previous reconnaissance efforts (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)) to tailor pretexts to be even more persuasive and believable for the victim.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1598/004)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) used phone calls to instruct victims to navigate to credential-harvesting websites.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has called victims' help desk to convince the support personnel to reset a privileged account’s credentials.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [C0059 - Salesforce Data Exfiltration](../../../../Threat%20Intelligence/Campaigns/C0059%20-%20Salesforce%20Data%20Exfiltration.md) — During [Salesforce Data Exfiltration](https://attack.mitre.org/campaigns/C0059), threat actors initiated voice calls with victims to socially engineer them into authorizing malicious applications or divulging sensitive credentials.(Citation: FBI Salesforce Data Theft SEP 2025)(Citation: Google Salesforce JUN 2025) [FBI Salesforce Data Theft SEP 2025](https://www.ic3.gov/CSA/2025/250912.pdf) · [Google Salesforce JUN 2025](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has used help desk voice-based phishing and also called employees at target organizations and compelled them to navigate to fake login portals using adversary-in-the-middle toolkits.(Citation: MSTIC Octo Tempest Operations October 2023)(Citation: CrowdStrike Scattered Spider JUL 2025)(Citation: Mandiant VMware vSphere JUL 2025) [CrowdStrike Scattered Spider JUL 2025](https://www.crowdstrike.com/en-us/blog/crowdstrike-services-observes-scattered-spider-escalate-attacks/) · [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944) · [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)

## Mitigations

- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Users can be trained to identify and report social engineering techniques and spearphishing attempts, while also being suspicious of and verifying the identify of callers.(Citation: CISA Phishing) [CISA Phishing](https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks)

## Detection strategies

- [DET0886 - Detection of Spearphishing Voice](../../../../Defenses/Detection%20Strategies/DET0886%20-%20Detection%20of%20Spearphishing%20Voice.md)

## Sources

- [Avertium callback phishing](https://www.avertium.com/resources/threat-reports/everything-you-need-to-know-about-callback-phishing)
- [BOA Telephone Scams](https://business.bofa.com/en-us/content/what-is-vishing.html)
