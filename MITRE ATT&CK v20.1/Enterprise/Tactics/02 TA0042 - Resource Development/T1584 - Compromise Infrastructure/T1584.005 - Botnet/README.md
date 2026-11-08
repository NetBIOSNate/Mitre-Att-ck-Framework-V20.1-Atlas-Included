# T1584.005 - Botnet

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1584 - Compromise Infrastructure](../README.md)

Adversaries may compromise numerous third-party systems to form a botnet that can be used during targeting. A botnet is a network of compromised systems that can be instructed to perform coordinated tasks.(Citation: Norton Botnet) Instead of purchasing/renting a botnet from a booter/stresser service, adversaries may build their own botnet by compromising numerous third-party systems.(Citation: Imperva DDoS for Hire) Adversaries may also conduct a takeover of an existing botnet, such as redirecting bots to adversary-controlled C2 servers.(Citation: Dell Dridex Oct 2015) With a botnet at their disposal, adversaries may perform follow-on activity such as large-scale [Phishing](https://attack.mitre.org/techniques/T1566) or Distributed Denial of Service (DDoS).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1584/005)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0099 - APT-C-36](../../../../Threat%20Intelligence/Groups/G0099%20-%20APT-C-36.md) — [APT-C-36](https://attack.mitre.org/groups/G0099) has used a botnet management interface to control large numbers of compromised hosts.(Citation: LevelBlue Blind Eagle Proton66 JUN 2025) [LevelBlue Blind Eagle Proton66 JUN 2025](https://www.levelblue.com/blogs/spiderlabs-blog/tracing-blind-eagle-to-proton66/)
- [G0001 - Axiom](../../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) has used large groups of compromised machines for use as proxy nodes.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [G0125 - HAFNIUM](../../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has used compromised devices in covert networks to obfuscate communications.(Citation: Microsoft Silk Typhoon MAR 2025) [Microsoft Silk Typhoon MAR 2025](https://www.microsoft.com/en-us/security/blog/2025/03/05/silk-typhoon-targeting-it-supply-chain/)
- [C0055 - Quad7 Activity](../../../../Threat%20Intelligence/Campaigns/C0055%20-%20Quad7%20Activity.md) — [Quad7 Activity](https://attack.mitre.org/campaigns/C0055) has compromised various branded SOHO routers to form a botnet that has been leveraged in password spraying activity.(Citation: Bitsight 7777 Botnet)(Citation: Microsoft Storm-0940) [Bitsight 7777 Botnet](https://www.bitsight.com/blog/7777-botnet-insights-multi-target-botnet) · [Microsoft Storm-0940](https://www.microsoft.com/en-us/security/blog/2024/10/31/chinese-threat-actor-storm-0940-uses-credentials-from-password-spray-attacks-from-a-covert-network/)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) has used a large-scale botnet to target Small Office/Home Office (SOHO) network devices.(Citation: NCSC Cyclops Blink February 2022) [NCSC Cyclops Blink February 2022](https://www.ncsc.gov.uk/files/Cyclops-Blink-Malware-Analysis-Report.pdf)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has used compromised Cisco and NETGEAR end-of-life SOHO routers implanted with KV Botnet malware to support operations.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0883 - Detection of Botnet](../../../../Defenses/Detection%20Strategies/DET0883%20-%20Detection%20of%20Botnet.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Dell Dridex Oct 2015](https://www.secureworks.com/research/dridex-bugat-v5-botnet-takeover-operation)
- [Imperva DDoS for Hire](https://www.imperva.com/learn/ddos/booters-stressers-ddosers/)
- [Norton Botnet](https://us.norton.com/internetsecurity-malware-what-is-a-botnet.html)
