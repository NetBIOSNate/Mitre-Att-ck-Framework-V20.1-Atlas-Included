# T1589 - Gather Victim Identity Information

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may gather information about the victim's identity that can be used during targeting. Information about identities may include a variety of details, including personal data (ex: employee names, email addresses, security question responses, etc.) as well as sensitive details such as credentials or multi-factor authentication (MFA) configurations.

Adversaries may gather this information in various ways, such as direct elicitation via [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about users could also be enumerated via other active means (i.e. [Active Scanning](https://attack.mitre.org/techniques/T1595)) such as probing and analyzing responses from authentication services that may reveal valid usernames in a system or permitted MFA /methods associated with those usernames.(Citation: GrimBlog UsernameEnum)(Citation: Obsidian SSPR Abuse 2023) Information about victims may also be exposed to adversaries via online or other accessible data sets (ex: [Social Media](https://attack.mitre.org/techniques/T1593/001) or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)).(Citation: OPM Leak)(Citation: Register Deloitte)(Citation: Register Uber)(Citation: Detectify Slack Tokens)(Citation: Forbes GitHub Creds)(Citation: GitHub truffleHog)(Citation: GitHub Gitrob)(Citation: CNET Leaks)

Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Phishing for Information](https://attack.mitre.org/techniques/T1598)), establishing operational resources (ex: [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [Phishing](https://attack.mitre.org/techniques/T1566) or [Valid Accounts](https://attack.mitre.org/techniques/T1078)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1589)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1589.001 - Credentials](T1589.001%20-%20Credentials/README.md)
- [T1589.002 - Email Addresses](T1589.002%20-%20Email%20Addresses/README.md)
- [T1589.003 - Employee Names](T1589.003%20-%20Employee%20Names/README.md)

## Procedure examples

- [G0050 - APT32](../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) has conducted targeted surveillance against activists and bloggers.(Citation: Amnesty Intl. Ocean Lotus February 2021) [Amnesty Intl. Ocean Lotus February 2021](https://www.amnestyusa.org/wp-content/uploads/2021/02/Click-and-Bait_Vietnamese-Human-Rights-Defenders-Targeted-with-Spyware-Attacks.pdf)
- [G1052 - Contagious Interview](../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has researched specific professional groups such as software developers for targeting.(Citation: Socket HexEval BeaverTail Contagious Interview June 2025)(Citation: SecurityScorecard Contagious Interview October 2024)(Citation: Securonix Contagious Interview DEVPOPPER April 2024)(Citation: SecurityScorecard Contagious Interview FamousChollima October 2024)(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023)(Citation: PaloAlto Unit42 ContagiousInterview BeaverTail InvisibileFerret October 2024) [Contagious Interview](https://attack.mitre.org/groups/G1052) has also researched individuals who work in roles related to cryptocurrency and blockchain technologies.(Citation: Sentinel One Contagious Interview ClickFix September 2025)(Citation: Sekoia ClickFake 2025) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/) · [Sekoia ClickFake 2025](https://blog.sekoia.io/clickfake-interview-campaign-by-lazarus/) · [Socket HexEval BeaverTail Contagious Interview June 2025](https://socket.dev/blog/north-korean-contagious-interview-campaign-drops-35-new-malicious-npm-packages) · [SecurityScorecard Contagious Interview October 2024](https://securityscorecard.com/blog/inside-a-north-korean-phishing-operation-targeting-devops-employees/) · [Securonix Contagious Interview DEVPOPPER April 2024](https://www.securonix.com/blog/analysis-of-devpopper-new-attack-campaign-targeting-software-developers-likely-associated-with-north-korean-threat-actors/) · [SecurityScorecard Contagious Interview FamousChollima October 2024](https://securityscorecard.com/blog/the-job-offer-that-wasnt-how-we-stopped-an-espionage-plot/) · [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/) · [PaloAlto Unit42 ContagiousInterview BeaverTail InvisibileFerret October 2024](https://unit42.paloaltonetworks.com/north-korean-threat-actors-lure-tech-job-seekers-as-fake-recruiters/)
- [G1016 - FIN13](../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has researched employees to target for social engineering attacks.(Citation: Mandiant FIN13 Aug 2022) [Mandiant FIN13 Aug 2022](https://www.mandiant.com/resources/blog/fin13-cybercriminal-mexico)
- [G1001 - HEXANE](../../../Threat%20Intelligence/Groups/G1001%20-%20HEXANE.md) — [HEXANE](https://attack.mitre.org/groups/G1001) has identified specific potential victims at targeted organizations.(Citation: ClearSky Siamesekitten August 2021) [ClearSky Siamesekitten August 2021](https://www.clearskysec.com/siamesekitten/)
- [G1004 - LAPSUS$](../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has gathered detailed information of target employees to enhance their social engineering lures.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G0059 - Magic Hound](../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has acquired mobile phone numbers of potential targets, possibly for mobile malware or additional phishing operations.(Citation: Proofpoint TA453 July2021) [Proofpoint TA453 July2021](https://www.proofpoint.com/us/blog/threat-insight/operation-spoofedscholars-conversation-ta453)
- [C0022 - Operation Dream Job](../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — For [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) conducted extensive reconnaissance research on potential targets.(Citation: ClearSky Lazarus Aug 2020) [ClearSky Lazarus Aug 2020](https://www.clearskysec.com/wp-content/uploads/2020/08/Dream-Job-Campaign.pdf)
- [C0014 - Operation Wocao](../../../Threat%20Intelligence/Campaigns/C0014%20-%20Operation%20Wocao.md) — During [Operation Wocao](https://attack.mitre.org/campaigns/C0014), threat actors targeted people based on their organizational roles and privileges.(Citation: FoxIT Wocao December 2019) [FoxIT Wocao December 2019](https://www.fox-it.com/media/kadlze5c/201912_report_operation_wocao.pdf)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has used information from previous data breaches to identify employee names to be used in social engineering.(Citation: Mandiant VMware vSphere JUL 2025) [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [G1033 - Star Blizzard](../../../Threat%20Intelligence/Groups/G1033%20-%20Star%20Blizzard.md) — [Star Blizzard](https://attack.mitre.org/groups/G1033) has identified ways to engage targets by researching potential victims' interests and social or professional contacts.(Citation: CISA Star Blizzard Advisory December 2023) [CISA Star Blizzard Advisory December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-341a)
- [G1055 - VOID MANTICORE](../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has gathered details on their intended victims to aid in social engineering efforts for leveraging tailored themes of attacks.(Citation: FBI IC3 Flash VOID MANTICORE Handala Hack March 2026) [FBI IC3 Flash VOID MANTICORE Handala Hack March 2026](https://www.ic3.gov/CSA/2026/260320.pdf)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has gathered victim identify information during pre-compromise reconnaissance. (Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0841 - Detection of Gather Victim Identity Information](../../../Defenses/Detection%20Strategies/DET0841%20-%20Detection%20of%20Gather%20Victim%20Identity%20Information.md)

## Sources

- [OPM Leak](https://web.archive.org/web/20230602111604/https://www.opm.gov/cybersecurity/cybersecurity-incidents/)
- [Detectify Slack Tokens](https://labs.detectify.com/writeups/slack-bot-token-leakage-exposing-business-critical-information/)
- [GitHub truffleHog](https://github.com/dxa4481/truffleHog)
- [GrimBlog UsernameEnum](https://grimhacker.com/2017/07/24/office365-activesync-username-enumeration/)
- [Register Uber](https://www.theregister.com/2015/02/28/uber_subpoenas_github_for_hacker_details/)
- [GitHub Gitrob](https://github.com/michenriksen/gitrob)
- [CNET Leaks](https://www.cnet.com/news/massive-breach-leaks-773-million-emails-21-million-passwords/)
- [Obsidian SSPR Abuse 2023](https://www.obsidiansecurity.com/blog/behind-the-breach-self-service-password-reset-azure-ad/)
- [Forbes GitHub Creds](https://www.forbes.com/sites/runasandvik/2014/01/14/attackers-scrape-github-for-cloud-service-credentials-hijack-account-to-mine-virtual-currency/#242c479d3196)
- [Register Deloitte](https://www.theregister.com/2017/09/26/deloitte_leak_github_and_google/)
