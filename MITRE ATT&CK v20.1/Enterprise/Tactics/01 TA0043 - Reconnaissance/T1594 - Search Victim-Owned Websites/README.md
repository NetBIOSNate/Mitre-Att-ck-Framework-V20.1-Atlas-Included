# T1594 - Search Victim-Owned Websites

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may search websites owned by the victim for information that can be used during targeting. Victim-owned websites may contain a variety of details, including names of departments/divisions, physical locations, and data about key employees such as names, roles, and contact info (ex: [Email Addresses](https://attack.mitre.org/techniques/T1589/002)). These sites may also have details highlighting business operations and relationships.(Citation: Comparitech Leak)

Adversaries may search victim-owned websites to gather actionable information. Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [Trusted Relationship](https://attack.mitre.org/techniques/T1199) or [Phishing](https://attack.mitre.org/techniques/T1566)).

In addition to manually browsing the website, adversaries may attempt to identify hidden directories or files that could contain additional sensitive information or vulnerable functionality. They may do this through automated activities such as [Wordlist Scanning](https://attack.mitre.org/techniques/T1595/003), as well as by leveraging files such as sitemap.xml and robots.txt.(Citation: Perez Sitemap XML 2023)(Citation: Register Robots TXT 2015)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1594)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Procedure examples

- [C0040 - APT41 DUST](../../../Threat%20Intelligence/Campaigns/C0040%20-%20APT41%20DUST.md) — [APT41 DUST](https://attack.mitre.org/campaigns/C0040) involved access of external victim websites for target development.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [C0029 - Cutting Edge](../../../Threat%20Intelligence/Campaigns/C0029%20-%20Cutting%20Edge.md) — During [Cutting Edge](https://attack.mitre.org/campaigns/C0029), threat actors peformed reconnaissance of victims' internal websites via proxied connections.(Citation: Volexity Ivanti Zero-Day Exploitation January 2024) [Volexity Ivanti Zero-Day Exploitation January 2024](https://www.volexity.com/blog/2024/01/10/active-exploitation-of-two-zero-day-vulnerabilities-in-ivanti-connect-secure-vpn/)
- [G1011 - EXOTIC LILY](../../../Threat%20Intelligence/Groups/G1011%20-%20EXOTIC%20LILY.md) — [EXOTIC LILY](https://attack.mitre.org/groups/G1011) has used contact forms on victim websites to generate phishing e-mails.(Citation: Google EXOTIC LILY March 2022) [Google EXOTIC LILY March 2022](https://blog.google/threat-analysis-group/exposing-initial-access-broker-ties-conti/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has searched for information on the target company's website.(Citation: KISA Operation Muzabi) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf)
- [C0049 - Leviathan Australian Intrusions](../../../Threat%20Intelligence/Campaigns/C0049%20-%20Leviathan%20Australian%20Intrusions.md) — [Leviathan](https://attack.mitre.org/groups/G0065) enumerated compromised web application resources to identify additional endpoints and resources linkd to the website for follow-on access during [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049).(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [G0034 - Sandworm Team](../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) has conducted research against potential victim websites as part of its operational planning.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)
- [G0122 - Silent Librarian](../../../Threat%20Intelligence/Groups/G0122%20-%20Silent%20Librarian.md) — [Silent Librarian](https://attack.mitre.org/groups/G0122) has searched victim's websites to identify the interests and academic areas of targeted individuals and to scrape source code, branding, and organizational contact information for phishing pages.(Citation: DOJ Iran Indictments March 2018)(Citation: Phish Labs Silent Librarian)(Citation: Proofpoint TA407 September 2019) [DOJ Iran Indictments March 2018](https://www.justice.gov/usao-sdny/press-release/file/1045781/download) · [Phish Labs Silent Librarian](https://info.phishlabs.com/blog/silent-librarian-more-to-the-story-of-the-iranian-mabna-institute-indictment) · [Proofpoint TA407 September 2019](https://www.proofpoint.com/us/threat-insight/post/threat-actor-profile-ta407-silent-librarian)
- [G1038 - TA578](../../../Threat%20Intelligence/Groups/G1038%20-%20TA578.md) — [TA578](https://attack.mitre.org/groups/G1038) has filled out contact forms on victims' websites to direct them to adversary-controlled URLs.(Citation: Latrodectus APR 2024) [Latrodectus APR 2024](https://www.proofpoint.com/us/blog/threat-insight/latrodectus-spider-bytes-ice)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has conducted pre-compromise reconnaissance on victim-owned sites.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0810 - Detection of Search Victim-Owned Websites](../../../Defenses/Detection%20Strategies/DET0810%20-%20Detection%20of%20Search%20Victim-Owned%20Websites.md)

## Sources

- [Perez Sitemap XML 2023](https://medium.com/@adimenia/how-attackers-can-misuse-sitemaps-to-enumerate-users-and-discover-sensitive-information-361a5065857a)
- [Comparitech Leak](https://www.comparitech.com/blog/vpn-privacy/350-million-customer-records-exposed-online/)
- [Register Robots TXT 2015](https://www.theregister.com/2015/05/19/robotstxt/)
