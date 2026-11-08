# T1598.001 - Spearphishing Service

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1598 - Phishing for Information](../README.md)

Adversaries may send spearphishing messages via third-party services to elicit sensitive information that can be used during targeting. Spearphishing for information is an attempt to trick targets into divulging information, frequently credentials or other actionable information. Spearphishing for information frequently involves social engineering techniques, such as posing as a source with a reason to collect information (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)) and/or sending multiple, seemingly urgent messages.

All forms of spearphishing are electronically delivered social engineering targeted at a specific individual, company, or industry. In this scenario, adversaries send messages through various social media services, personal webmail, and other non-enterprise controlled services.(Citation: ThreatPost Social Media Phishing) These services are more likely to have a less-strict security policy than an enterprise. As with most kinds of spearphishing, the goal is to generate rapport with the target or get the target's interest in some way. Adversaries may create fake social media accounts and message employees for potential job opportunities. Doing so allows a plausible reason for asking about services, policies, and information about their environment. Adversaries may also use information from previous reconnaissance efforts (ex: [Social Media](https://attack.mitre.org/techniques/T1593/001) or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)) to craft persuasive and believable lures.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1598/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) sent Telegram messages impersonating IT personnel to harvest credentials.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has corresponded and disseminated links to victims through social media.(Citation: Mandiant_UNC1549_Feb2024) [Mandiant_UNC1549_Feb2024](https://cloud.google.com/blog/topics/threat-intelligence/suspected-iranian-unc1549-targets-israel-middle-east)

## Detection strategies

- [DET0821 - Detection of Spearphishing Service](../../../../Defenses/Detection%20Strategies/DET0821%20-%20Detection%20of%20Spearphishing%20Service.md)

## Mitigations

- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Users can be trained to identify social engineering techniques and spearphishing attempts.

## Sources

- [ThreatPost Social Media Phishing](https://threatpost.com/facebook-launching-pad-phishing-attacks/160351/)
