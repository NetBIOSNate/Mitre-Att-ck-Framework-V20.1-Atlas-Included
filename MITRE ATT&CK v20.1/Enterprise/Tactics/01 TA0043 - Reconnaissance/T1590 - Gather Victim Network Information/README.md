# T1590 - Gather Victim Network Information

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may gather information about the victim's networks that can be used during targeting. Information about networks may include a variety of details, including administrative data (ex: IP ranges, domain names, etc.) as well as specifics regarding its topology and operations.

Adversaries may gather this information in various ways, such as direct collection actions via [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about networks may also be exposed to adversaries via online or other accessible data sets (ex: [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)).(Citation: WHOIS)(Citation: DNS Dumpster)(Citation: Circl Passive DNS) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [Trusted Relationship](https://attack.mitre.org/techniques/T1199)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1590)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1590.002 - DNS](T1590.002%20-%20DNS/README.md)
- [T1590.001 - Domain Properties](T1590.001%20-%20Domain%20Properties/README.md)
- [T1590.005 - IP Addresses](T1590.005%20-%20IP%20Addresses/README.md)
- [T1590.006 - Network Security Appliances](T1590.006%20-%20Network%20Security%20Appliances/README.md)
- [T1590.004 - Network Topology](T1590.004%20-%20Network%20Topology/README.md)
- [T1590.003 - Network Trust Dependencies](T1590.003%20-%20Network%20Trust%20Dependencies/README.md)

## Procedure examples

- [G0125 - HAFNIUM](../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) gathered the fully qualified domain names (FQDNs) for targeted Exchange servers in the victim's environment.(Citation: Volexity Exchange Marauder March 2021) [Volexity Exchange Marauder March 2021](https://www.volexity.com/blog/2021/03/02/active-exploitation-of-microsoft-exchange-zero-day-vulnerabilities/)
- [G0119 - Indrik Spider](../../../Threat%20Intelligence/Groups/G0119%20-%20Indrik%20Spider.md) — [Indrik Spider](https://attack.mitre.org/groups/G0119) has downloaded tools, such as the Advanced Port Scanner utility and Lansweeper, to conduct internal reconnaissance of the victim network. [Indrik Spider](https://attack.mitre.org/groups/G0119) has also accessed the victim’s VMware VCenter, which had information about host configuration, clusters, etc.(Citation: Mandiant_UNC2165) [Mandiant_UNC2165](https://cloud.google.com/blog/topics/threat-intelligence/unc2165-shifts-to-evade-sanctions/)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has conducted extensive pre-compromise reconnaissance to learn about the target organization’s network.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0869 - Detection of Gather Victim Network Information](../../../Defenses/Detection%20Strategies/DET0869%20-%20Detection%20of%20Gather%20Victim%20Network%20Information.md)

## Sources

- [Circl Passive DNS](https://www.circl.lu/services/passive-dns/)
- [DNS Dumpster](https://dnsdumpster.com/)
- [WHOIS](https://who.is/)
