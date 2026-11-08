# T0879 - Damage to Property

[ICS](../../../README.md) / [Impact](../README.md)

Adversaries may cause damage and destruction of property to infrastructure, equipment, and the surrounding environment when attacking control systems. This technique may result in device and operational equipment breakdown, or represent tangential damage from other techniques used in an attack. Depending on the severity of physical damage and disruption caused to control processes and systems, this technique may result in [Loss of Safety](https://attack.mitre.org/techniques/T0880). Operations that result in [Loss of Control](https://attack.mitre.org/techniques/T0827) may also cause damage to property, which may be directly or indirectly motivated by an adversary seeking to cause impact in the form of [Loss of Productivity and Revenue](https://attack.mitre.org/techniques/T0828). 


The German Federal Office for Information Security (BSI) reported a targeted attack on a steel mill under an incidents affecting business section of its 2014 IT Security Report. (Citation: BSI State of IT Security 2014)  These targeted attacks affected industrial operations and resulted in breakdowns of control system components and even entire installations. As a result of these breakdowns, massive impact and damage resulted from the uncontrolled shutdown of a blast furnace. 

A Polish student used a remote controller device to interface with the Lodz city tram system in Poland. (Citation: John Bill May 2017) (Citation: Shelley Smith February 2008) (Citation: Bruce Schneier January 2008) Using this remote, the student was able to capture and replay legitimate tram signals. This resulted in damage to impacted trams, people, and the surrounding property. Reportedly, four trams were derailed and were forced to make emergency stops. (Citation: Shelley Smith February 2008) Commands issued by the student may have also resulted in tram collisions, causing harm to those on board and the environment outside. (Citation: Bruce Schneier January 2008)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0879)

**Tactics**  [Impact](../README.md)

**Platforms**  [No platform specified](../../../Platforms/None.md)

## Procedure examples

- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) disrupted water operations that have included loss of water pressure and flooding.(Citation: Tenable Minnesota Water Utilities) [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)
- [C0020 - Maroochy Water Breach](../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary gained remote computer access to the control system and altered data so that whatever function should have occurred at affected pumping stations did not occur or occurred in a different way. This ultimately led to 800,000 liters of raw sewage being spilled out into the community. The raw sewage affected local parks, rivers, and even a local hotel. This resulted in harm to marine life and produced a sickening stench from the community's affected rivers.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)

## Detection strategies

- [DET0762 - Detection of Damage to Property](../../../Defenses/Detection%20Strategies/DET0762%20-%20Detection%20of%20Damage%20to%20Property.md)

## Mitigations

- [M0805 - Mechanical Protection Layers](../../../Defenses/Mitigations/M0805%20-%20Mechanical%20Protection%20Layers.md) — Protection devices should have minimal digital components to prevent exposure to related adversarial techniques. Examples include interlocks, rupture disks, release valves, etc. (Citation: A G Foord, W G Gulland, C R Howard, T Kellacher, W H Smith 2004) [A G Foord, W G Gulland, C R Howard, T Kellacher, W H Smith 2004](https://www.icheme.org/media/9906/xviii-paper-23.pdf)
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0812 - Safety Instrumented Systems](../../../Defenses/Mitigations/M0812%20-%20Safety%20Instrumented%20Systems.md) — Ensure that all SIS are segmented from operational networks to prevent them from being targeted by additional adversarial behavior.

## Sources

- [Bruce Schneier January 2008](https://www.schneier.com/blog/archives/2008/01/hacking_the_pol.html)
- [BSI State of IT Security 2014](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/Securitysituation/IT-Security-Situation-in-Germany-2014.pdf?__blob=publicationFile&v=3)
- [John Bill May 2017](https://www.londonreconnections.com/2017/hacked-cyber-security-railways/)
- [Shelley Smith February 2008](https://inhomelandsecurity.com/teen_hacker_in_poland_plays_tr/)
