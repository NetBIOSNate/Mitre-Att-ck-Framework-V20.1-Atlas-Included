# T1591.001 - Determine Physical Locations

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1591 - Gather Victim Org Information](../README.md)

Adversaries may gather the victim's physical location(s) that can be used during targeting. Information about physical locations of a target organization may include a variety of details, including where key resources and infrastructure are housed. Physical locations may also indicate what legal jurisdiction and/or authorities the victim operates within.

Adversaries may gather this information in various ways, such as direct elicitation via [Phishing for Information](https://attack.mitre.org/techniques/T1598). Physical locations of a target organization may also be exposed to adversaries via online or other accessible data sets (ex: [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594) or [Social Media](https://attack.mitre.org/techniques/T1593/001)).(Citation: ThreatPost Broadvoice Leak)(Citation: SEC EDGAR Search) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Develop Capabilities](https://attack.mitre.org/techniques/T1587) or [Obtain Capabilities](https://attack.mitre.org/techniques/T1588)), and/or initial access (ex: [Phishing](https://attack.mitre.org/techniques/T1566) or [Hardware Additions](https://attack.mitre.org/techniques/T1200)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1591/001)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has collected location information from visitors to their phishing sites.(Citation: Google Iran Threats October 2021) [Google Iran Threats October 2021](https://blog.google/threat-analysis-group/countering-threats-iran/)

## Detection strategies

- [DET0806 - Detection of Determine Physical Locations](../../../../Defenses/Detection%20Strategies/DET0806%20-%20Detection%20of%20Determine%20Physical%20Locations.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Sources

- [ThreatPost Broadvoice Leak](https://threatpost.com/broadvoice-leaks-350m-records-voicemail-transcripts/160158/)
- [SEC EDGAR Search](https://www.sec.gov/edgar/search/)
