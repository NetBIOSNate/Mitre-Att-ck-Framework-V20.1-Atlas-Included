# T1588 - Obtain Capabilities

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may buy and/or steal capabilities that can be used during targeting. Rather than developing their own capabilities in-house, adversaries may purchase, freely download, or steal them. Activities may include the acquisition of malware, software (including licenses), exploits, certificates, and information relating to vulnerabilities. Adversaries may obtain capabilities to support their operations throughout numerous phases of the adversary lifecycle.

In addition to downloading free malware, software, and exploits from the internet, adversaries may purchase these capabilities from third-party entities. Third-party entities can include technology companies that specialize in malware and exploits, criminal marketplaces, or individuals.(Citation: NationsBuying)(Citation: PegasusCitizenLab)

In addition to purchasing capabilities, adversaries may steal capabilities from third-party entities (including other adversaries). This can include stealing software licenses, malware, SSL/TLS and code-signing certificates, or raiding closed databases of vulnerabilities or exploits.(Citation: DiginotarCompromise)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1588)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1588.007 - Artificial Intelligence](T1588.007%20-%20Artificial%20Intelligence/README.md)
- [T1588.003 - Code Signing Certificates](T1588.003%20-%20Code%20Signing%20Certificates/README.md)
- [T1588.004 - Digital Certificates](T1588.004%20-%20Digital%20Certificates/README.md)
- [T1588.005 - Exploits](T1588.005%20-%20Exploits/README.md)
- [T1588.001 - Malware](T1588.001%20-%20Malware/README.md)
- [T1588.002 - Tool](T1588.002%20-%20Tool/README.md)
- [T1588.006 - Vulnerabilities](T1588.006%20-%20Vulnerabilities/README.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0850 - Detection of Obtain Capabilities](../../../Defenses/Detection%20Strategies/DET0850%20-%20Detection%20of%20Obtain%20Capabilities.md)

## Sources

- [PegasusCitizenLab](https://citizenlab.ca/2016/08/million-dollar-dissident-iphone-zero-day-nso-group-uae/)
- [DiginotarCompromise](https://threatpost.com/final-report-diginotar-hack-shows-total-compromise-ca-servers-103112/77170/)
- [NationsBuying](https://www.nytimes.com/2013/07/14/world/europe/nations-buying-as-hackers-sell-computer-flaws.html)
