# T1590.004 - Network Topology

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1590 - Gather Victim Network Information](../README.md)

Adversaries may gather information about the victim's network topology that can be used during targeting. Information about network topologies may include a variety of details, including the physical and/or logical arrangement of both external-facing and internal network environments. This information may also include specifics regarding network devices (gateways, routers, etc.) and other infrastructure.

Adversaries may gather this information in various ways, such as direct collection actions via [Active Scanning](https://attack.mitre.org/techniques/T1595) or [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about network topologies may also be exposed to adversaries via online or other accessible data sets (ex: [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)).(Citation: DNS Dumpster) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1590/004)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0819 - Detection of Network Topology](../../../../Defenses/Detection%20Strategies/DET0819%20-%20Detection%20of%20Network%20Topology.md)

## Procedure examples

- [C0062 - Anthropic AI-orchestrated Campaign](../../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary used Claude Code to map a complete network topology of the target infrastructure.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
- [G1016 - FIN13](../../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has searched for infrastructure that can provide remote access to an environment for targeting efforts.(Citation: Mandiant FIN13 Aug 2022) [Mandiant FIN13 Aug 2022](https://www.mandiant.com/resources/blog/fin13-cybercriminal-mexico)
- [G0069 - MuddyWater](../../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has mapped target networks; access to this information and more is then shared/sold to other Iran threat actors.(Citation: FalconFeeds_MuddyWaterPSRust_Mar2026) [FalconFeeds_MuddyWaterPSRust_Mar2026](https://falconfeeds.io/blogs/muddywater-in-the-iran-israel-cyber-war-from-powershell-scripts-to-rust-implants)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has used configuration files from exploited network devices to help discover upstream and downstream network segments.(Citation: Cisco Salt Typhoon FEB 2025)(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a) · [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has conducted extensive reconnaissance of victim networks including identifying network topologies.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [DNS Dumpster](https://dnsdumpster.com/)
