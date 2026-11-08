# T1595 - Active Scanning

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may execute active reconnaissance scans to gather information that can be used during targeting. Active scans are those where the adversary probes victim infrastructure via network traffic, as opposed to other forms of reconnaissance that do not involve direct interaction.

Adversaries may perform different forms of active scanning depending on what information they seek to gather. These scans can also be performed in various ways, including using native features of network protocols such as ICMP.(Citation: Botnet Scan)(Citation: OWASP Fingerprinting) Information from these scans may reveal opportunities for other forms of reconnaissance (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133) or [Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1595)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1595.001 - Scanning IP Blocks](T1595.001%20-%20Scanning%20IP%20Blocks/README.md)
- [T1595.002 - Vulnerability Scanning](T1595.002%20-%20Vulnerability%20Scanning/README.md)
- [T1595.003 - Wordlist Scanning](T1595.003%20-%20Wordlist%20Scanning/README.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0830 - Detection of Active Scanning](../../../Defenses/Detection%20Strategies/DET0830%20-%20Detection%20of%20Active%20Scanning.md)

## Procedure examples

- [G1045 - Salt Typhoon](../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has scanned victim environments for open ports and services.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) engaged in network reconnaissance against targets of interest.(Citation: FireEye TEMP.Veles 2018) [FireEye TEMP.Veles 2018](https://web.archive.org/web/20190202205824/https://www.fireeye.com/blog/threat-research/2018/10/triton-attribution-russian-government-owned-lab-most-likely-built-tools.html)

## Sources

- [Botnet Scan](https://www.caida.org/publications/papers/2012/analysis_slash_zero/analysis_slash_zero.pdf)
- [OWASP Fingerprinting](https://wiki.owasp.org/index.php/OAT-004_Fingerprinting)
