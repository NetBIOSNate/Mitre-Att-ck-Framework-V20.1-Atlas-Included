# T1598.002 - Spearphishing Attachment

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1598 - Phishing for Information](../README.md)

Adversaries may send spearphishing messages with a malicious attachment to elicit sensitive information that can be used during targeting. Spearphishing for information is an attempt to trick targets into divulging information, frequently credentials or other actionable information. Spearphishing for information frequently involves social engineering techniques, such as posing as a source with a reason to collect information (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)) and/or sending multiple, seemingly urgent messages.

All forms of spearphishing are electronically delivered social engineering targeted at a specific individual, company, or industry. In this scenario, adversaries attach a file to the spearphishing email. In some cases, they may rely upon the recipient populating information, then returning the file.(Citation: Sophos Attachment)(Citation: GitHub Phishery) The text of the spearphishing email usually tries to give a plausible reason why the file should be filled-in, such as a request for information from a business associate. In other cases, adversaries may leverage techniques such as [HTML Smuggling](https://attack.mitre.org/techniques/T1027/006) to harvest user credentials via fake login portals.(Citation: Huntress HTML Smuggling 2024)

Adversaries may also use information from previous reconnaissance efforts (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)) to craft persuasive and believable lures.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1598/002)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0035 - Dragonfly](../../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has used spearphishing with Microsoft Office attachments to enable harvesting of user credentials.(Citation: US-CERT TA18-074A) [US-CERT TA18-074A](https://www.us-cert.gov/ncas/alerts/TA18-074A)
- [G1008 - SideCopy](../../../../Threat%20Intelligence/Groups/G1008%20-%20SideCopy.md) — [SideCopy](https://attack.mitre.org/groups/G1008) has crafted generic lures for spam campaigns to collect emails and credentials for targeting efforts.(Citation: MalwareBytes SideCopy Dec 2021) [MalwareBytes SideCopy Dec 2021](https://www.malwarebytes.com/blog/news/2021/12/sidecopy-apt-connecting-lures-to-victims-payloads-to-infrastructure)
- [G0121 - Sidewinder](../../../../Threat%20Intelligence/Groups/G0121%20-%20Sidewinder.md) — [Sidewinder](https://attack.mitre.org/groups/G0121) has sent e-mails with malicious attachments that lead victims to credential harvesting websites.(Citation: ATT Sidewinder January 2021)(Citation: Rewterz Sidewinder APT April 2020)(Citation: Cyble Sidewinder September 2020) [ATT Sidewinder January 2021](https://cdn-cybersecurity.att.com/docs/global-perspective-of-the-sidewinder-apt.pdf) · [Rewterz Sidewinder APT April 2020](https://www.rewterz.com/threats/sidewinder-apt-group-campaign-analysis) · [Cyble Sidewinder September 2020](https://cybleinc.com/2020/09/26/sidewinder-apt-targets-with-futuristic-tactics-and-techniques/)
- [G1033 - Star Blizzard](../../../../Threat%20Intelligence/Groups/G1033%20-%20Star%20Blizzard.md) — [Star Blizzard](https://attack.mitre.org/groups/G1033) has sent emails to establish rapport with targets eventually sending messages with attachments containing links to credential-stealing sites.(Citation: Microsoft Star Blizzard August 2022)(Citation: CISA Star Blizzard Advisory December 2023)(Citation: StarBlizzard)(Citation: Google TAG COLDRIVER January 2024) [CISA Star Blizzard Advisory December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-341a) · [Microsoft Star Blizzard August 2022](https://www.microsoft.com/en-us/security/blog/2022/08/15/disrupting-seaborgiums-ongoing-phishing-operations/) · [StarBlizzard](https://www.microsoft.com/en-us/security/blog/2023/12/07/star-blizzard-increases-sophistication-and-evasion-in-ongoing-attacks/) · [Google TAG COLDRIVER January 2024](https://blog.google/threat-analysis-group/google-tag-coldriver-russian-phishing-malware/)

## Mitigations

- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Use anti-spoofing and email authentication mechanisms to filter messages based on validity checks of the sender domain (using SPF) and integrity of messages (using DKIM). Enabling these mechanisms within an organization (through policies such as DMARC) may enable recipients (intra-org and cross domain) to perform similar message filtering and validation.(Citation: Microsoft Anti Spoofing)(Citation: ACSC Email Spoofing) [ACSC Email Spoofing](https://web.archive.org/web/20210708014107/https://www.cyber.gov.au/sites/default/files/2019-03/spoof_email_sender_policy_framework.pdf) · [Microsoft Anti Spoofing](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spoofing-protection?view=o365-worldwide)
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Users can be trained to identify social engineering techniques and spearphishing attempts.

## Detection strategies

- [DET0865 - Detection of Spearphishing Attachment](../../../../Defenses/Detection%20Strategies/DET0865%20-%20Detection%20of%20Spearphishing%20Attachment.md)

## Sources

- [ACSC Email Spoofing](https://web.archive.org/web/20210708014107/https://www.cyber.gov.au/sites/default/files/2019-03/spoof_email_sender_policy_framework.pdf)
- [Sophos Attachment](https://nakedsecurity.sophos.com/2020/10/02/serious-security-phishing-without-links-when-phishers-bring-along-their-own-web-pages/)
- [Huntress HTML Smuggling 2024](https://www.huntress.com/blog/smugglers-gambit-uncovering-html-smuggling-adversary-in-the-middle-tradecraft)
- [Microsoft Anti Spoofing](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spoofing-protection?view=o365-worldwide)
- [GitHub Phishery](https://github.com/ryhanson/phishery)
