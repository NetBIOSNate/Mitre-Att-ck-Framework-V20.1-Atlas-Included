# T1595.001 - Scanning IP Blocks

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1595 - Active Scanning](../README.md)

Adversaries may scan victim IP blocks to gather information that can be used during targeting. Public IP addresses may be allocated to organizations by block, or a range of sequential addresses.

Adversaries may scan IP blocks in order to [Gather Victim Network Information](https://attack.mitre.org/techniques/T1590), such as which IP addresses are actively in use as well as more detailed information about hosts assigned these addresses. Scans may range from simple pings (ICMP requests and responses) to more nuanced scans that may reveal host software/versions via server banners or other network artifacts.(Citation: Botnet Scan) Information from these scans may reveal opportunities for other forms of reconnaissance (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1595/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [C0062 - Anthropic AI-orchestrated Campaign](../../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary used Claude Code to scan infrastructure across IP ranges associated with the target organization.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
- [G1003 - Ember Bear](../../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) has targeted IP ranges for vulnerability scanning related to government and critical infrastructure organizations.(Citation: CISA GRU29155 2024) [CISA GRU29155 2024](https://www.cisa.gov/sites/default/files/2024-09/aa24-249a-russian-military-cyber-actors-target-us-and-global-critical-infrastructure.pdf)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has scanned specific lists of target IP addresses.(Citation: Trend Micro TeamTNT) [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0817 - Detection of Scanning IP Blocks](../../../../Defenses/Detection%20Strategies/DET0817%20-%20Detection%20of%20Scanning%20IP%20Blocks.md)

## Sources

- [Botnet Scan](https://www.caida.org/publications/papers/2012/analysis_slash_zero/analysis_slash_zero.pdf)
