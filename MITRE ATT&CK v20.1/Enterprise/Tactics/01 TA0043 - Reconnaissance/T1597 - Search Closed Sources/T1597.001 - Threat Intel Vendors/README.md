# T1597.001 - Threat Intel Vendors

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1597 - Search Closed Sources](../README.md)

Adversaries may search private data from threat intelligence vendors for information that can be used during targeting. Threat intelligence vendors may offer paid feeds or portals that offer more data than what is publicly reported. Although sensitive details (such as customer names and other identifiers) may be redacted, this information may contain trends regarding breaches such as target industries, attribution claims, and successful TTPs/countermeasures.(Citation: D3Secutrity CTI Feeds)

Adversaries may search in private threat intelligence vendor data to gather actionable information. If a threat actor is searching for information on their own activities, that falls under [Search Threat Vendor Data](https://attack.mitre.org/techniques/T1681). Information reported by vendors may also reveal opportunities other forms of reconnaissance (ex: [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or initial access (ex: [Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190) or [External Remote Services](https://attack.mitre.org/techniques/T1133)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1597/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0816 - Detection of Threat Intel Vendors](../../../../Defenses/Detection%20Strategies/DET0816%20-%20Detection%20of%20Threat%20Intel%20Vendors.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [D3Secutrity CTI Feeds](https://d3security.com/blog/10-of-the-best-open-source-threat-intelligence-feeds/)
