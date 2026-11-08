# T1566 - Phishing

[Enterprise](../../../README.md) / [Initial Access](../README.md)

Adversaries may send phishing messages to gain access to victim systems. All forms of phishing are electronically delivered social engineering. Phishing can be targeted, known as spearphishing. In spearphishing, a specific individual, company, or industry will be targeted by the adversary. More generally, adversaries can conduct non-targeted phishing, such as in mass malware spam campaigns.

Adversaries may send victims emails containing malicious attachments or links, typically to execute malicious code on victim systems. Phishing may also be conducted via third-party services (like social media platforms) or delivered via calendar invites. Phishing may also involve social engineering techniques, such as posing as a trusted source, as well as evasive techniques such as removing or manipulating emails or metadata/headers from compromised accounts being abused to send messages (e.g., [Email Hiding Rules](https://attack.mitre.org/techniques/T1564/008)).(Citation: Microsoft OAuth Spam 2022)(Citation: Palo Alto Unit 42 VBA Infostealer 2014) Another way to accomplish this is by [Email Spoofing](https://attack.mitre.org/techniques/T1684/002)(Citation: Proofpoint-spoof) the identity of the sender, which can be used to fool both the human recipient as well as automated security tools,(Citation: cyberproof-double-bounce) or by including the intended target as a party to an existing email thread that includes malicious files or links (i.e., "thread hijacking").(Citation: phishing-krebs)

Victims may also receive phishing messages that instruct them to call a phone number where they are directed to visit a malicious URL, download malware,(Citation: sygnia Luna Month)(Citation: CISA Remote Monitoring and Management Software) or install adversary-accessible remote management tools onto their computer (i.e., [User Execution](https://attack.mitre.org/techniques/T1204)).(Citation: Unit42 Luna Moth)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1566)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Identity Provider](../../../Platforms/Identity%20Provider.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1566.001 - Spearphishing Attachment](T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1566.003 - Spearphishing via Service](T1566.003%20-%20Spearphishing%20via%20Service/README.md)
- [T1566.004 - Spearphishing Voice](T1566.004%20-%20Spearphishing%20Voice/README.md)

## Procedure examples

- [G1049 - AppleJeus](../../../Threat%20Intelligence/Groups/G1049%20-%20AppleJeus.md) — [AppleJeus](https://attack.mitre.org/groups/G1049) has used spearphishing emails to distribute malicious payloads.(Citation: dtex DPRK 2025 structure ITworkers) [dtex DPRK 2025 structure ITworkers](https://reports.dtexsystems.com/DTEX-Exposing+DPRK+Cyber+Syndicate+and+Hidden+IT+Workforce.pdf)
- [G0001 - Axiom](../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) has used spear phishing to initially compromise victims.(Citation: Cisco Group 72)(Citation: Novetta-Axiom) [Cisco Group 72](http://blogs.cisco.com/security/talos/threat-spotlight-group-72) · [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [G0115 - GOLD SOUTHFIELD](../../../Threat%20Intelligence/Groups/G0115%20-%20GOLD%20SOUTHFIELD.md) — [GOLD SOUTHFIELD](https://attack.mitre.org/groups/G0115) has conducted malicious spam (malspam) campaigns to gain access to victim's machines.(Citation: Secureworks REvil September 2019) [Secureworks REvil September 2019](https://www.secureworks.com/research/revil-sodinokibi-ransomware)
- [S0009 - Hikit](../../../Threat%20Intelligence/Software/Malware/S0009%20-%20Hikit.md) — [Hikit](https://attack.mitre.org/software/S0009) has been spread through spear phishing.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [G1032 - INC Ransom](../../../Threat%20Intelligence/Groups/G1032%20-%20INC%20Ransom.md) — [INC Ransom](https://attack.mitre.org/groups/G1032) has used phishing to gain initial access.(Citation: SOCRadar INC Ransom January 2024)(Citation: SentinelOne INC Ransomware) [SentinelOne INC Ransomware](https://www.sentinelone.com/anthology/inc-ransom/) · [SOCRadar INC Ransom January 2024](https://socradar.io/dark-web-profile-inc-ransom/)
- [S1139 - INC Ransomware](../../../Threat%20Intelligence/Software/Malware/S1139%20-%20INC%20Ransomware.md) — [INC Ransomware](https://attack.mitre.org/software/S1139) campaigns have used spearphishing emails for initial access.(Citation: SentinelOne INC Ransomware) [SentinelOne INC Ransomware](https://www.sentinelone.com/anthology/inc-ransom/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used spearphishing to gain initial access and intelligence.(Citation: MSFT-AI)(Citation: Mandiant APT43 March 2024) [Mandiant APT43 March 2024](https://services.google.com/fh/files/misc/apt43-report-en.pdf) · [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)
- [G0069 - MuddyWater](../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has sent phishing emails to targets from the email address support@microsoftonlines[.]com.(Citation: NaumaanProofpoint_GlobalClickFix_April2025) [NaumaanProofpoint_GlobalClickFix_April2025](https://www.proofpoint.com/us/blog/threat-insight/around-world-90-days-state-sponsored-actors-try-clickfix)
- [S1073 - Royal](../../../Threat%20Intelligence/Software/Malware/S1073%20-%20Royal.md) — [Royal](https://attack.mitre.org/software/S1073) has been spread through the use of phishing campaigns including "call back phishing" where victims are lured into calling a number provided through email.(Citation: Cybereason Royal December 2022)(Citation: Kroll Royal Deep Dive February 2023)(Citation: CISA Royal AA23-061A March 2023) [CISA Royal AA23-061A March 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-061a) · [Cybereason Royal December 2022](https://www.cybereason.com/blog/royal-ransomware-analysis) · [Kroll Royal Deep Dive February 2023](https://www.kroll.com/en/insights/publications/cyber/royal-ransomware-deep-dive)
- [G1041 - Sea Turtle](../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) used spear phishing to gain initial access to victims.(Citation: Talos Sea Turtle 2019) [Talos Sea Turtle 2019](https://blog.talosintelligence.com/seaturtle/)
- [G1055 - VOID MANTICORE](../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has emailed victims threatening messages.(Citation: DOJ FBI Handala Hack March 2026) [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has used phishing as an initial access vector.(Citation: Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026) [DOJ FBI Handala Hack March 2026](https://www.justice.gov/opa/media/1431956/dl?inline) · [Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026](https://dti.domaintools.com/research/handala-mois-linked-cyber-influence-ecosystem-threat-intelligence-assessment)

## Mitigations

- [M1049 - Antivirus/Antimalware](../../../Defenses/Mitigations/M1049%20-%20Antivirus%20-%20Antimalware.md) — Anti-virus can automatically quarantine suspicious files.
- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Perform audits or scans of systems, permissions, insecure software, insecure configurations, etc. to identify potential weaknesses.
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion prevention systems and systems designed to scan and remove malicious email attachments or links can be used to block activity.
- [M1021 - Restrict Web-Based Content](../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Determine if certain websites or attachment types (ex: .scr, .exe, .pif, .cpl, etc.) that can be used for phishing are necessary for business operations and consider blocking access if activity cannot be monitored well or if it poses a significant risk.
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Use anti-spoofing and email authentication mechanisms to filter messages based on validity checks of the sender domain (using SPF) and integrity of messages (using DKIM). Enabling these mechanisms within an organization (through policies such as DMARC) may enable recipients (intra-org and cross domain) to perform similar message filtering and validation.(Citation: Microsoft Anti Spoofing)(Citation: ACSC Email Spoofing) [ACSC Email Spoofing](https://web.archive.org/web/20210708014107/https://www.cyber.gov.au/sites/default/files/2019-03/spoof_email_sender_policy_framework.pdf) · [Microsoft Anti Spoofing](https://docs.microsoft.com/en-us/microsoft-365/security/office-365-security/anti-spoofing-protection?view=o365-worldwide)
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Users can be trained to identify social engineering techniques and phishing emails.

## Detection strategies

- [DET0070 - Detection Strategy for Phishing across platforms.](../../../Defenses/Detection%20Strategies/DET0070%20-%20Detection%20Strategy%20for%20Phishing%20across%20platforms.md)

## Sources

- [phishing-krebs](https://krebsonsecurity.com/2024/03/thread-hijacking-phishes-that-prey-on-your-curiosity/)
- [CISA Remote Monitoring and Management Software](https://www.cisa.gov/uscert/ncas/alerts/aa23-025a)
- [cyberproof-double-bounce](https://blog.cyberproof.com/blog/double-bounced-attacks-with-email-spoofing-2022-trends)
- [Unit42 Luna Moth](https://unit42.paloaltonetworks.com/luna-moth-callback-phishing/)
- [Microsoft OAuth Spam 2022](https://www.microsoft.com/en-us/security/blog/2022/09/22/malicious-oauth-applications-used-to-compromise-email-servers-and-spread-spam/)
- [sygnia Luna Month](https://blog.sygnia.co/luna-moth-false-subscription-scams)
- [Proofpoint-spoof](https://www.proofpoint.com/us/threat-reference/email-spoofing)
- [Palo Alto Unit 42 VBA Infostealer 2014](https://unit42.paloaltonetworks.com/examining-vba-initiated-infostealer-campaign/)
