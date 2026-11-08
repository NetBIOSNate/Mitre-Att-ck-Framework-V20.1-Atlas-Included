# T1591.002 - Business Relationships

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1591 - Gather Victim Org Information](../README.md)

Adversaries may gather information about the victim's business relationships that can be used during targeting. Information about an organization’s business relationships may include a variety of details, including second or third-party organizations/domains (ex: managed service providers, contractors, etc.) that have connected (and potentially elevated) network access. This information may also reveal supply chains and shipment paths for the victim’s hardware and software resources.

Adversaries may gather this information in various ways, such as direct elicitation via [Phishing for Information](https://attack.mitre.org/techniques/T1598). Information about business relationships may also be exposed to adversaries via online or other accessible data sets (ex: [Social Media](https://attack.mitre.org/techniques/T1593/001) or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)).(Citation: ThreatPost Broadvoice Leak) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [Supply Chain Compromise](https://attack.mitre.org/techniques/T1195), [Drive-by Compromise](https://attack.mitre.org/techniques/T1189), or [Trusted Relationship](https://attack.mitre.org/techniques/T1199)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1591/002)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0855 - Detection of Business Relationships](../../../../Defenses/Detection%20Strategies/DET0855%20-%20Detection%20of%20Business%20Relationships.md)

## Procedure examples

- [G0035 - Dragonfly](../../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has collected open source information to identify relationships between organizations for targeting purposes.(Citation: Gigamon Berserk Bear October 2021) [Gigamon Berserk Bear October 2021](https://vblocalhost.com/uploads/VB2021-Slowik.pdf)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has gathered detailed knowledge of an organization's supply chain relationships.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — In preparation for its attack against the 2018 Winter Olympics, [Sandworm Team](https://attack.mitre.org/groups/G0034) conducted online research of partner organizations listed on an official PyeongChang Olympics partnership site.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [ThreatPost Broadvoice Leak](https://threatpost.com/broadvoice-leaks-350m-records-voicemail-transcripts/160158/)
