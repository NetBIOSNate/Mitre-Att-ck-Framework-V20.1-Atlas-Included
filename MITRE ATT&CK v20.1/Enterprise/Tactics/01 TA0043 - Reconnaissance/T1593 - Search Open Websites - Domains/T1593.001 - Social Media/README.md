# T1593.001 - Social Media

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1593 - Search Open Websites/Domains](../README.md)

Adversaries may search social media for information about victims that can be used during targeting. Social media sites may contain various information about a victim organization, such as business announcements as well as information about the roles, locations, and interests of staff.

Adversaries may search in different social media sites depending on what information they seek to gather. Threat actors may passively harvest data from these sites, as well as use information gathered to create fake profiles/groups to entice victims into revealing specific information (i.e. [Spearphishing Service](https://attack.mitre.org/techniques/T1598/001)).(Citation: Cyware Social Media) Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [Spearphishing via Service](https://attack.mitre.org/techniques/T1566/003)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1593/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0812 - Detection of Social Media](../../../../Defenses/Detection%20Strategies/DET0812%20-%20Detection%20of%20Social%20Media.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) had identified and solicited victims through social media such as LinkedIn, X, and Telegram.(Citation: Sekoia ClickFake 2025)(Citation: Validin Contagious Interview North Korea ClickFix January 2025)(Citation: SecurityScorecard Contagious Interview October 2024)(Citation: SecurityScorecard Contagious Interview FamousChollima October 2024)(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023)(Citation: PaloAlto Unit42 ContagiousInterview BeaverTail InvisibileFerret October 2024) [Sekoia ClickFake 2025](https://blog.sekoia.io/clickfake-interview-campaign-by-lazarus/) · [Validin Contagious Interview North Korea ClickFix January 2025](https://www.validin.com/blog/inoculating_contagious_interview_with_validin/) · [SecurityScorecard Contagious Interview October 2024](https://securityscorecard.com/blog/inside-a-north-korean-phishing-operation-targeting-devops-employees/) · [SecurityScorecard Contagious Interview FamousChollima October 2024](https://securityscorecard.com/blog/the-job-offer-that-wasnt-how-we-stopped-an-espionage-plot/) · [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/) · [PaloAlto Unit42 ContagiousInterview BeaverTail InvisibileFerret October 2024](https://unit42.paloaltonetworks.com/north-korean-threat-actors-lure-tech-job-seekers-as-fake-recruiters/)
- [G1011 - EXOTIC LILY](../../../../Threat%20Intelligence/Groups/G1011%20-%20EXOTIC%20LILY.md) — [EXOTIC LILY](https://attack.mitre.org/groups/G1011) has copied data from social media sites to impersonate targeted individuals.(Citation: Google EXOTIC LILY March 2022) [Google EXOTIC LILY March 2022](https://blog.google/threat-analysis-group/exposing-initial-access-broker-ties-conti/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used Twitter to monitor potential victims and to prepare targeted phishing e-mails.(Citation: Malwarebytes Kimsuky June 2021) [Malwarebytes Kimsuky June 2021](https://blog.malwarebytes.com/threat-analysis/2021/06/kimsuky-apt-continues-to-target-south-korean-government-using-appleseed-backdoor/)
- [C0022 - Operation Dream Job](../../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — For [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) used LinkedIn to identify and target employees within a chosen organization.(Citation: ESET Lazarus Jun 2020) [ESET Lazarus Jun 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_Operation_Interception.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [Cyware Social Media](https://cyware.com/news/how-hackers-exploit-social-media-to-break-into-your-company-88e8da8e)
