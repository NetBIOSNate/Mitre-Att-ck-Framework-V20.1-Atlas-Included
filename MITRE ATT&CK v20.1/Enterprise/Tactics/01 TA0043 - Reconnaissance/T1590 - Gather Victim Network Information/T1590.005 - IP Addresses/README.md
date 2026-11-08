# T1590.005 - IP Addresses

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1590 - Gather Victim Network Information](../README.md)

Adversaries may gather the victim's IP addresses that can be used during targeting. Public IP addresses may be allocated to organizations by block, or a range of sequential addresses. Information about assigned IP addresses may include a variety of details, such as which IP addresses are in use. IP addresses may also enable an adversary to derive other details about a victim, such as organizational size, physical location(s), Internet service provider, and where/how their publicly-facing infrastructure is hosted.

Adversaries may gather this information in various ways, such as direct collection actions via [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about assigned IP addresses may also be exposed to adversaries via online or other accessible data sets (ex: [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)).(Citation: WHOIS)(Citation: DNS Dumpster)(Citation: Circl Passive DNS) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1590/005)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Procedure examples

- [G0138 - Andariel](../../../../Threat%20Intelligence/Groups/G0138%20-%20Andariel.md) — [Andariel](https://attack.mitre.org/groups/G0138) has limited its watering hole attacks to specific IP address ranges.(Citation: AhnLab Andariel Subgroup of Lazarus June 2018) [AhnLab Andariel Subgroup of Lazarus June 2018](https://web.archive.org/web/20230213154832/http://download.ahnlab.com/global/brochure/%5BAnalysis%5DAndariel_Group.pdf)
- [G0125 - HAFNIUM](../../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has obtained IP addresses for publicly-accessible Exchange servers.(Citation: Volexity Exchange Marauder March 2021) [Volexity Exchange Marauder March 2021](https://www.volexity.com/blog/2021/03/02/active-exploitation-of-microsoft-exchange-zero-day-vulnerabilities/)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has captured the IP addresses of visitors to their phishing sites.(Citation: Google Iran Threats October 2021) [Google Iran Threats October 2021](https://blog.google/threat-analysis-group/countering-threats-iran/)

## Detection strategies

- [DET0815 - Detection of IP Addresses](../../../../Defenses/Detection%20Strategies/DET0815%20-%20Detection%20of%20IP%20Addresses.md)

## Sources

- [Circl Passive DNS](https://www.circl.lu/services/passive-dns/)
- [DNS Dumpster](https://dnsdumpster.com/)
- [WHOIS](https://who.is/)
