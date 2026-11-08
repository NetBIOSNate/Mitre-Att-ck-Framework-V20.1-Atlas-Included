# T1590.001 - Domain Properties

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1590 - Gather Victim Network Information](../README.md)

Adversaries may gather information about the victim's network domain(s) that can be used during targeting. Information about domains and their properties may include a variety of details, including what domain(s) the victim owns as well as administrative data (ex: name, registrar, etc.) and more directly actionable information such as contacts (email addresses and phone numbers), business addresses, and name servers.

Adversaries may gather this information in various ways, such as direct collection actions via [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about victim domains and their properties may also be exposed to adversaries via online or other accessible data sets (ex: [WHOIS](https://attack.mitre.org/techniques/T1596/002)).(Citation: WHOIS)(Citation: DNS Dumpster)(Citation: Circl Passive DNS) Where third-party cloud providers are in use, this information may also be exposed through publicly available API endpoints, such as GetUserRealm and autodiscover in Office 365 environments.(Citation: Azure Active Directory Reconnaisance)(Citation: Office 265 Azure Domain Availability) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596), [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593), or [Phishing for Information](https://attack.mitre.org/techniques/T1598)), establishing operational resources (ex: [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [Phishing](https://attack.mitre.org/techniques/T1566)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1590/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0847 - Detection of Domain Properties](../../../../Defenses/Detection%20Strategies/DET0847%20-%20Detection%20of%20Domain%20Properties.md)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can gather information about a tenant’s domains using public Microsoft APIs.(Citation: AADInternals Documentation)(Citation: Azure AD Recon) [AADInternals Documentation](https://o365blog.com/aadinternals) · [Azure AD Recon](https://o365blog.com/post/just-looking)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) conducted technical reconnaissance of the Parliament of Georgia's official internet domain prior to its 2019 attack.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [Circl Passive DNS](https://www.circl.lu/services/passive-dns/)
- [Azure Active Directory Reconnaisance](https://o365blog.com/post/just-looking/)
- [DNS Dumpster](https://dnsdumpster.com/)
- [Office 265 Azure Domain Availability](https://docs.microsoft.com/en-us/archive/blogs/tip_of_the_day/cloud-tip-of-the-day-advanced-way-to-check-domain-availability-for-office-365-and-azure)
- [WHOIS](https://who.is/)
