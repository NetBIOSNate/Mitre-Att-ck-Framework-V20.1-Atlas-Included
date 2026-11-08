# T1598 - Phishing for Information

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may send phishing messages to elicit sensitive information that can be used during targeting. Phishing for information is an attempt to trick targets into divulging information, frequently credentials or other actionable information. Phishing for information is different from [Phishing](https://attack.mitre.org/techniques/T1566) in that the objective is gathering data from the victim rather than executing malicious code.

All forms of phishing are electronically delivered social engineering. Phishing can be targeted, known as spearphishing. In spearphishing, a specific individual, company, or industry will be targeted by the adversary. More generally, adversaries can conduct non-targeted phishing, such as in mass credential harvesting campaigns.

Adversaries may also try to obtain information directly through the exchange of emails, instant messages, or other electronic conversation means.(Citation: ThreatPost Social Media Phishing)(Citation: TrendMictro Phishing)(Citation: PCMag FakeLogin)(Citation: Sophos Attachment)(Citation: GitHub Phishery) Victims may also receive phishing messages that direct them to call a phone number where the adversary attempts to collect confidential information.(Citation: Avertium callback phishing)

Phishing for information frequently involves social engineering techniques, such as posing as a source with a reason to collect information (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)) and/or sending multiple, seemingly urgent messages. Another way to accomplish this is by [Email Spoofing](https://attack.mitre.org/techniques/T1684/002)(Citation: Proofpoint-spoof) the identity of the sender, which can be used to fool both the human recipient as well as automated security tools.(Citation: cyberproof-double-bounce) 

Phishing for information may also involve evasive techniques, such as removing or manipulating emails or metadata/headers from compromised accounts being abused to send messages (e.g., [Email Hiding Rules](https://attack.mitre.org/techniques/T1564/008)).(Citation: Microsoft OAuth Spam 2022)(Citation: Palo Alto Unit 42 VBA Infostealer 2014)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1598)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1598.002 - Spearphishing Attachment](T1598.002%20-%20Spearphishing%20Attachment/README.md)
- [T1598.003 - Spearphishing Link](T1598.003%20-%20Spearphishing%20Link/README.md)
- [T1598.001 - Spearphishing Service](T1598.001%20-%20Spearphishing%20Service/README.md)
- [T1598.004 - Spearphishing Voice](T1598.004%20-%20Spearphishing%20Voice/README.md)

## Procedure examples

- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has used spearphishing to compromise credentials.(Citation: Microsoft Targeting Elections September 2020)(Citation: Secureworks IRON TWILIGHT Active Measures March 2017) [Microsoft Targeting Elections September 2020](https://blogs.microsoft.com/on-the-issues/2020/09/10/cyberattacks-us-elections-trump-biden/) · [Secureworks IRON TWILIGHT Active Measures March 2017](https://www.secureworks.com/research/iron-twilight-supports-active-measures)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used tailored spearphishing emails to gather victim information including contat lists to identify additional targets.(Citation: Mandiant APT43 March 2024) [Mandiant APT43 March 2024](https://services.google.com/fh/files/misc/apt43-report-en.pdf)
- [G1036 - Moonstone Sleet](../../../Threat%20Intelligence/Groups/G1036%20-%20Moonstone%20Sleet.md) — [Moonstone Sleet](https://attack.mitre.org/groups/G1036) has interacted with victims to gather information via email.(Citation: Microsoft Moonstone Sleet 2024) [Microsoft Moonstone Sleet 2024](https://www.microsoft.com/en-us/security/blog/2024/05/28/moonstone-sleet-emerges-as-new-north-korean-threat-actor-with-new-bag-of-tricks/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has used a combination of credential phishing and social engineering to capture one-time-password (OTP) codes.(Citation: CrowdStrike Scattered Spider BYOVD January 2023) [CrowdStrike Scattered Spider BYOVD January 2023](https://www.crowdstrike.com/blog/scattered-spider-attempts-to-avoid-detection-with-bring-your-own-vulnerable-driver-tactic/)
- [G1057 - ShinyHunters](../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has sent phishing emails to Microsoft Office 365 corporate users in order to steal credentials.(Citation: Intel471_SH_Aug2021) [Intel471_SH_Aug2021](https://www.intel471.com/blog/shinyhunters-data-breach-mitre-attack)
- [G0128 - ZIRCONIUM](../../../Threat%20Intelligence/Groups/G0128%20-%20ZIRCONIUM.md) — [ZIRCONIUM](https://attack.mitre.org/groups/G0128) targeted presidential campaign staffers with credential phishing e-mails.(Citation: Google Election Threats October 2020) [Google Election Threats October 2020](https://blog.google/threat-analysis-group/how-were-tackling-evolving-online-threats/)

## Mitigations

- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Use anti-spoofing and email authentication mechanisms to filter messages based on validity checks of the sender domain (using SPF) and integrity of messages (using DKIM). Enabling these mechanisms within an organization (through policies such as DMARC) may enable recipients (intra-org and cross domain) to perform similar message filtering and validation.(Citation: Microsoft Anti Spoofing)(Citation: ACSC Email Spoofing) [ACSC Email Spoofing](https://web.archive.org/web/20210708014107/https://www.cyber.gov.au/sites/default/files/2019-03/spoof_email_sender_policy_framework.pdf) · [Microsoft Anti Spoofing](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spoofing-protection?view=o365-worldwide)
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Users can be trained to identify social engineering techniques and spearphishing attempts.

## Detection strategies

- [DET0823 - Detection of Phishing for Information](../../../Defenses/Detection%20Strategies/DET0823%20-%20Detection%20of%20Phishing%20for%20Information.md)

## Sources

- [Avertium callback phishing](https://www.avertium.com/resources/threat-reports/everything-you-need-to-know-about-callback-phishing)
- [TrendMictro Phishing](https://www.trendmicro.com/en_us/research/20/i/tricky-forms-of-phishing.html)
- [Sophos Attachment](https://nakedsecurity.sophos.com/2020/10/02/serious-security-phishing-without-links-when-phishers-bring-along-their-own-web-pages/)
- [cyberproof-double-bounce](https://blog.cyberproof.com/blog/double-bounced-attacks-with-email-spoofing-2022-trends)
- [PCMag FakeLogin](https://www.pcmag.com/news/hackers-try-to-phish-united-nations-staffers-with-fake-login-pages)
- [Microsoft OAuth Spam 2022](https://www.microsoft.com/en-us/security/blog/2022/09/22/malicious-oauth-applications-used-to-compromise-email-servers-and-spread-spam/)
- [ThreatPost Social Media Phishing](https://threatpost.com/facebook-launching-pad-phishing-attacks/160351/)
- [Proofpoint-spoof](https://www.proofpoint.com/us/threat-reference/email-spoofing)
- [GitHub Phishery](https://github.com/ryhanson/phishery)
- [Palo Alto Unit 42 VBA Infostealer 2014](https://unit42.paloaltonetworks.com/examining-vba-initiated-infostealer-campaign/)
