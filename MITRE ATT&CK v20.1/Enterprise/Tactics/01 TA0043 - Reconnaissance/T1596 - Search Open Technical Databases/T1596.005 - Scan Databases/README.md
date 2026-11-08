# T1596.005 - Scan Databases

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1596 - Search Open Technical Databases](../README.md)

Adversaries may search within public scan databases for information about victims that can be used during targeting. Various online services continuously publish the results of Internet scans/surveys, often harvesting information such as active IP addresses, hostnames, open ports, certificates, and even server banners.(Citation: Shodan)

Adversaries may search scan databases to gather actionable information. Threat actors can use online resources and lookup tools to harvest information from these services. Adversaries may seek information about their already identified targets, or use these datasets to discover opportunities for successful breaches. Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133) or [Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1596/005)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) uses the Chinese website fofa.su, similar to the Shodan scanning service, for passive scanning of victims.(Citation: Rostovcev APT41 2021) [Rostovcev APT41 2021](https://www.group-ib.com/blog/apt41-world-tour-2021/)
- [C0040 - APT41 DUST](../../../../Threat%20Intelligence/Campaigns/C0040%20-%20APT41%20DUST.md) — [APT41 DUST](https://attack.mitre.org/campaigns/C0040) used internet scan data for target development.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has used FOFA, Shodan, and Censys to search for exposed victim infrastructure.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0858 - Detection of Scan Databases](../../../../Defenses/Detection%20Strategies/DET0858%20-%20Detection%20of%20Scan%20Databases.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [Shodan](https://shodan.io)
