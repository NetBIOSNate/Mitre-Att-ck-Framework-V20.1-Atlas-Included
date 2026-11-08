# T0880 - Loss of Safety

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may compromise safety system functions designed to maintain safe operation of a process when unacceptable or dangerous conditions occur. Safety systems are often composed of the same elements as control systems but have the sole purpose of ensuring the process fails in a predetermined safe manner. 

Many unsafe conditions in process control happen too quickly for a human operator to react to. Speed is critical in correcting these conditions to limit serious impacts such as Loss of Control and Property Damage. 

Adversaries may target and disable safety system functions as a prerequisite to subsequent attack execution or to allow for future unsafe conditionals to go unchecked. Detection of a Loss of Safety by operators can result in the shutdown of a process due to strict policies regarding safety systems. This can cause a Loss of Productivity and Revenue and may meet the technical goals of adversaries seeking to cause process disruptions.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0880)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Mitigations

- [M0805 - Mechanical Protection Layers](../../../Defenses/Mitigations/M0805%20-%20Mechanical%20Protection%20Layers.md) — Protection devices should have minimal digital components to prevent exposure to related adversarial techniques. Examples include interlocks, rupture disks, release valves, etc. (Citation: A G Foord, W G Gulland, C R Howard, T Kellacher, W H Smith 2004) [A G Foord, W G Gulland, C R Howard, T Kellacher, W H Smith 2004](https://www.icheme.org/media/9906/xviii-paper-23.pdf)
- [M0812 - Safety Instrumented Systems](../../../Defenses/Mitigations/M0812%20-%20Safety%20Instrumented%20Systems.md) — Ensure that all SIS are segmented from operational networks to prevent them from being targeted by additional adversarial behavior.

## Procedure examples

- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) manipulated critical shutdown and alarm logic, which would allow the system to enter unsafe process states without proper notification or protections.(Citation: CISA-AA26-097A) [CISA-AA26-097A](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-097a)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) has the capability to reprogram the SIS logic to allow unsafe conditions to persist or reprogram the SIS to allow an unsafe state while using the DCS to create an unsafe state or hazard. (Citation: Blake Johnson, Dan Caban, Marina Krotofil, Dan Scali, Nathan Brubaker, Christopher Glyer December 2017) [Blake Johnson, Dan Caban, Marina Krotofil, Dan Scali, Nathan Brubaker, Christopher Glyer December 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)

## Detection strategies

- [DET0779 - Detection of Loss of Safety](../../../Defenses/Detection%20Strategies/DET0779%20-%20Detection%20of%20Loss%20of%20Safety.md)
