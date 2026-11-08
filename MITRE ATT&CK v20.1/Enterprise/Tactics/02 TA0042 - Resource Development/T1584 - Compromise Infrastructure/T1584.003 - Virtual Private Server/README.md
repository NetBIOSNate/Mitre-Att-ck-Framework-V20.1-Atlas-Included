# T1584.003 - Virtual Private Server

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1584 - Compromise Infrastructure](../README.md)

Adversaries may compromise third-party Virtual Private Servers (VPSs) that can be used during targeting. There exist a variety of cloud service providers that will sell virtual machines/containers as a service. Adversaries may compromise VPSs purchased by third-party entities. By compromising a VPS to use as infrastructure, adversaries can make it difficult to physically tie back operations to themselves.(Citation: NSA NCSC Turla OilRig)

Compromising a VPS for use in later stages of the adversary lifecycle, such as Command and Control, can allow adversaries to benefit from the ubiquity and trust associated with higher reputation cloud service providers as well as that added by the compromised third-party.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1584/003)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0854 - Detection of Virtual Private Server](../../../../Defenses/Detection%20Strategies/DET0854%20-%20Detection%20of%20Virtual%20Private%20Server.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used compromised VPS servers for C2.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0048 - Operation MidnightEclipse](../../../../Threat%20Intelligence/Campaigns/C0048%20-%20Operation%20MidnightEclipse.md) — During [Operation MidnightEclipse](https://attack.mitre.org/campaigns/C0048), threat actors abused Virtual Private Servers to store malicious files.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has used the VPS infrastructure of compromised Iranian threat actors.(Citation: NSA NCSC Turla OilRig) [NSA NCSC Turla OilRig](https://media.defense.gov/2019/Oct/18/2002197242/-1/-1/0/NSA_CSA_Turla_20191021%20ver%204%20-%20nsa.gov.pdf)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has compromised Virtual Private Servers (VPS) to proxy C2 traffic.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Koczwara Beacon Hunting Sep 2021](https://michaelkoczwara.medium.com/cobalt-strike-c2-hunting-with-shodan-c448d501a6e2)
- [NSA NCSC Turla OilRig](https://media.defense.gov/2019/Oct/18/2002197242/-1/-1/0/NSA_CSA_Turla_20191021%20ver%204%20-%20nsa.gov.pdf)
- [Mandiant SCANdalous Jul 2020](https://cloud.google.com/blog/topics/threat-intelligence/scandalous-external-detection-using-network-scan-data-and-automation/)
- [ThreatConnect Infrastructure Dec 2020](https://web.archive.org/web/20221130114004/https://threatconnect.com/blog/infrastructure-research-hunting/)
