# T1597 - Search Closed Sources

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may search and gather information about victims from closed (e.g., paid, private, or otherwise not freely available) sources that can be used during targeting. Information about victims may be available for purchase from reputable private sources and databases, such as paid subscriptions to feeds of technical/threat intelligence data. Adversaries may also purchase information from less-reputable sources such as dark web or cybercrime blackmarkets.(Citation: ZDNET Selling Data)

Adversaries may search in different closed databases depending on what information they seek to gather. Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133) or [Valid Accounts](https://attack.mitre.org/techniques/T1078)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1597)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1597.002 - Purchase Technical Data](T1597.002%20-%20Purchase%20Technical%20Data/README.md)
- [T1597.001 - Threat Intel Vendors](T1597.001%20-%20Threat%20Intel%20Vendors/README.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Procedure examples

- [G1011 - EXOTIC LILY](../../../Threat%20Intelligence/Groups/G1011%20-%20EXOTIC%20LILY.md) — [EXOTIC LILY](https://attack.mitre.org/groups/G1011) has searched for information on targeted individuals on business databases including RocketReach and CrunchBase.(Citation: Google EXOTIC LILY March 2022) [Google EXOTIC LILY March 2022](https://blog.google/threat-analysis-group/exposing-initial-access-broker-ties-conti/)

## Detection strategies

- [DET0822 - Detection of Search Closed Sources](../../../Defenses/Detection%20Strategies/DET0822%20-%20Detection%20of%20Search%20Closed%20Sources.md)

## Sources

- [ZDNET Selling Data](https://www.zdnet.com/article/a-hacker-group-is-selling-more-than-73-million-user-records-on-the-dark-web/)
