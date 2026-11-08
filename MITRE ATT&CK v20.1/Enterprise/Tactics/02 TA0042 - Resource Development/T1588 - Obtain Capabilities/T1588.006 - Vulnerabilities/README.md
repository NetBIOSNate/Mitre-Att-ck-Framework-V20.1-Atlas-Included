# T1588.006 - Vulnerabilities

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1588 - Obtain Capabilities](../README.md)

Adversaries may acquire information about vulnerabilities that can be used during targeting. A vulnerability is a weakness in computer hardware or software that can, potentially, be exploited by an adversary to cause unintended or unanticipated behavior to occur. Adversaries may find vulnerability information by searching open databases or gaining access to closed vulnerability databases.(Citation: National Vulnerability Database)

An adversary may monitor vulnerability disclosures/databases to understand the state of existing, as well as newly discovered, vulnerabilities. There is usually a delay between when a vulnerability is discovered and when it is made public. An adversary may target the systems of those known to conduct vulnerability research (including commercial vendors). Knowledge of a vulnerability may cause an adversary to search for an existing exploit (i.e. [Exploits](https://attack.mitre.org/techniques/T1588/005)) or to attempt to develop one themselves (i.e. [Exploits](https://attack.mitre.org/techniques/T1587/004)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1588/006)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [C0049 - Leviathan Australian Intrusions](../../../../Threat%20Intelligence/Campaigns/C0049%20-%20Leviathan%20Australian%20Intrusions.md) — [Leviathan](https://attack.mitre.org/groups/G0065) weaponized publicly-known vulnerabilities for initial access and other purposes during [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049).(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — In 2017, [Sandworm Team](https://attack.mitre.org/groups/G0034) conducted technical research related to vulnerabilities associated with websites used by the Korean Sport and Olympic Committee, a Korean power company, and a Korean airport.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has obtained capabilities to exploit N-day vulnerabilities associated with public facing services to gain initial access to victim environments to include Zoho ManageEngine (CVE-2022-47966), Citrix NetScaler “Citrix Bleed” (CVE-2023-4966), and Adobe ColdFusion 2016 (CVE-2023-29300 or CVE-2023-38203).(Citation: Microsoft Storm-501 Sabbath Ransomware Embargo September 2024) [Microsoft Storm-501 Sabbath Ransomware Embargo September 2024](https://www.microsoft.com/en-us/security/blog/2024/09/26/storm-0501-ransomware-attacks-expanding-to-hybrid-cloud-environments/)
- [G1017 - Volt Typhoon](../../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has used publicly available exploit code for initial access.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0808 - Detection of Vulnerabilities](../../../../Defenses/Detection%20Strategies/DET0808%20-%20Detection%20of%20Vulnerabilities.md)

## Sources

- [National Vulnerability Database](https://nvd.nist.gov/)
