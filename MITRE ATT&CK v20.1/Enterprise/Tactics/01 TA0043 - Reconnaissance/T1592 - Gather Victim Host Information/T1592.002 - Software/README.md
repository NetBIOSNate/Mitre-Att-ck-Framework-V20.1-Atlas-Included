# T1592.002 - Software

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1592 - Gather Victim Host Information](../README.md)

Adversaries may gather information about the victim's host software that can be used during targeting. Information about installed software may include a variety of details such as types and versions on specific hosts, as well as the presence of additional components that might be indicative of added defensive protections (ex: antivirus, SIEMs, etc.).

Adversaries may gather this information in various ways, such as direct collection actions via [Active Scanning](https://attack.mitre.org/techniques/T1595) (ex: listening ports, server banners, user agent strings) or [Phishing for Information](https://attack.mitre.org/techniques/T1598). Adversaries may also compromise sites then include malicious content designed to collect host information from visitors.(Citation: ATT ScanBox) Information about the installed software may also be exposed to adversaries via online or other accessible data sets (ex: job postings, network maps, assessment reports, resumes, or purchase invoices). Additionally, adversaries may analyze metadata from victim-owned files (e.g., PDFs, DOCs, images, and sound files hosted on victim-owned websites) to extract information about the software and hardware used to create or process those files. Metadata may reveal software versions, configurations, or timestamps that indicate outdated or vulnerable software. This information can be cross-referenced with known CVEs to identify potential vectors for exploitation in future operations.(Citation: Outpost24)

Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or for initial access (ex: [Supply Chain Compromise](https://attack.mitre.org/techniques/T1195) or [External Remote Services](https://attack.mitre.org/techniques/T1133)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1592/002)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0888 - Detection of Software](../../../../Defenses/Detection%20Strategies/DET0888%20-%20Detection%20of%20Software.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Procedure examples

- [G0138 - Andariel](../../../../Threat%20Intelligence/Groups/G0138%20-%20Andariel.md) — [Andariel](https://attack.mitre.org/groups/G0138) has inserted a malicious script within compromised websites to collect potential victim information such as browser type, system language, Flash Player version, and other data.(Citation: TrendMicro New Andariel Tactics July 2018) [TrendMicro New Andariel Tactics July 2018](https://www.trendmicro.com/en_us/research/18/g/new-andariel-reconnaissance-tactics-hint-at-next-targets.html)
- [C0062 - Anthropic AI-orchestrated Campaign](../../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary utilized Claude Code to catalog services and data on discovered endpoints.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has captured the user-agent strings from visitors to their phishing sites.(Citation: Google Iran Threats October 2021) [Google Iran Threats October 2021](https://blog.google/threat-analysis-group/countering-threats-iran/)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) has researched software code to enable supply-chain operations, most notably for the 2017 [NotPetya](https://attack.mitre.org/software/S0368) attack. [Sandworm Team](https://attack.mitre.org/groups/G0034) also collected a list of computers using specific software as part of its targeting efforts.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)

## Sources

- [ATT ScanBox](https://cybersecurity.att.com/blogs/labs-research/scanbox-a-reconnaissance-framework-used-on-watering-hole-attacks)
- [Outpost24](https://outpost24.com/blog/metadata-hackers-best-friend/)
- [ThreatConnect Infrastructure Dec 2020](https://web.archive.org/web/20221130114004/https://threatconnect.com/blog/infrastructure-research-hunting/)
