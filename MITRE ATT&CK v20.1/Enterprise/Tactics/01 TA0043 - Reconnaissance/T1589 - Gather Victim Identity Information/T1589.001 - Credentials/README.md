# T1589.001 - Credentials

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1589 - Gather Victim Identity Information](../README.md)

Adversaries may gather credentials that can be used during targeting. Account credentials gathered by adversaries may be those directly associated with the target victim organization or attempt to take advantage of the tendency for users to use the same passwords across personal and business accounts.

Adversaries may gather credentials from potential victims in various ways, such as direct elicitation via [Phishing for Information](https://attack.mitre.org/techniques/T1598). Adversaries may also compromise sites then add malicious content designed to collect website authentication cookies from visitors.(Citation: ATT ScanBox)(Citation: Register Deloitte)(Citation: Register Uber)(Citation: Detectify Slack Tokens)(Citation: Forbes GitHub Creds)(Citation: GitHub truffleHog)(Citation: GitHub Gitrob)(Citation: CNET Leaks) Where multi-factor authentication (MFA) based on out-of-band communications is in use, adversaries may compromise a service provider to gain access to MFA codes and one-time passwords (OTP).(Citation: Okta Scatter Swine 2022)

Credential information may also be exposed to adversaries via leaks to online or other accessible data sets (ex: [Search Engines](https://attack.mitre.org/techniques/T1593/002), breach dumps, code repositories, etc.). Adversaries may purchase credentials from dark web markets, such as Russian Market and 2easy, or through access to Telegram channels that distribute logs from infostealer malware.(Citation: Bleeping Computer 2easy 2021)(Citation: SecureWorks Infostealers 2023)(Citation: Bleeping Computer Stealer Logs 2023)

Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Phishing for Information](https://attack.mitre.org/techniques/T1598)), establishing operational resources (ex: [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133) or [Valid Accounts](https://attack.mitre.org/techniques/T1078)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1589/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has harvested user's login credentials.(Citation: Microsoft Targeting Elections September 2020) [Microsoft Targeting Elections September 2020](https://blogs.microsoft.com/on-the-issues/2020/09/10/cyberattacks-us-elections-trump-biden/)
- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) sent phishing messages via SMS to steal credentials.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G0114 - Chimera](../../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has collected credentials for the target organization from previous breaches for use in brute force attacks.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has gathered user identities and credentials to gain initial access to a victim's organization; the group has also called an organization's help desk to reset a target's credentials.(Citation: MSTIC DEV-0537 Mar 2022)(Citation: NCC Group LAPSUS Apr 2022) [NCC Group LAPSUS Apr 2022](https://www.nccgroup.com/research-blog/lapsus-recent-techniques-tactics-and-procedures/) · [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G0065 - Leviathan](../../../../Threat%20Intelligence/Groups/G0065%20-%20Leviathan.md) — [Leviathan](https://attack.mitre.org/groups/G0065) has collected compromised credentials to use for targeting efforts.(Citation: CISA AA21-200A APT40 July 2021) [CISA AA21-200A APT40 July 2021](https://us-cert.cisa.gov/ncas/alerts/aa21-200a)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) gathered credentials from two victims that they then attempted to validate across 75 different websites. [Magic Hound](https://attack.mitre.org/groups/G0059) has also collected credentials from over 900 Fortinet VPN servers in the US, Europe, and Israel.(Citation: IBM ITG18 2020)(Citation: Microsoft Iranian Threat Actor Trends November 2021) [Microsoft Iranian Threat Actor Trends November 2021](https://www.microsoft.com/en-us/security/blog/2021/11/16/evolving-trends-in-iranian-threat-actor-activity-mstic-presentation-at-cyberwarcon-2021) · [IBM ITG18 2020](https://securityintelligence.com/posts/new-research-exposes-iranian-threat-group-operations/)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has collected credentials containing PII, ultimately selling the information on their DLS.(Citation: Intel471_SH_Aug2021)(Citation: Unit42KelleyVaya_BlingLibra_Aug2024) [Intel471_SH_Aug2021](https://www.intel471.com/blog/shinyhunters-data-breach-mitre-attack) · [Unit42KelleyVaya_BlingLibra_Aug2024](https://unit42.paloaltonetworks.com/shinyhunters-ransomware-extortion/)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — For the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) conducted credential theft operations to obtain credentials to be used for access to victim environments.(Citation: CrowdStrike StellarParticle January 2022) [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0813 - Detection of Credentials](../../../../Defenses/Detection%20Strategies/DET0813%20-%20Detection%20of%20Credentials.md)

## Sources

- [Bleeping Computer 2easy 2021](https://www.bleepingcomputer.com/news/security/2easy-now-a-significant-dark-web-marketplace-for-stolen-data/)
- [ATT ScanBox](https://cybersecurity.att.com/blogs/labs-research/scanbox-a-reconnaissance-framework-used-on-watering-hole-attacks)
- [Detectify Slack Tokens](https://labs.detectify.com/writeups/slack-bot-token-leakage-exposing-business-critical-information/)
- [GitHub truffleHog](https://github.com/dxa4481/truffleHog)
- [Bleeping Computer Stealer Logs 2023](https://www.bleepingcomputer.com/news/security/dissecting-the-dark-web-supply-chain-stealer-logs-in-context/)
- [Register Uber](https://www.theregister.com/2015/02/28/uber_subpoenas_github_for_hacker_details/)
- [GitHub Gitrob](https://github.com/michenriksen/gitrob)
- [CNET Leaks](https://www.cnet.com/news/massive-breach-leaks-773-million-emails-21-million-passwords/)
- [Okta Scatter Swine 2022](https://sec.okta.com/scatterswine)
- [Forbes GitHub Creds](https://www.forbes.com/sites/runasandvik/2014/01/14/attackers-scrape-github-for-cloud-service-credentials-hijack-account-to-mine-virtual-currency/#242c479d3196)
- [SecureWorks Infostealers 2023](https://www.secureworks.com/research/the-growing-threat-from-infostealers)
- [Register Deloitte](https://www.theregister.com/2017/09/26/deloitte_leak_github_and_google/)
