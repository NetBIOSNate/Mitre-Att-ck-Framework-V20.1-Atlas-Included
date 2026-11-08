# AML.T0128 - Compromise Infrastructure

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may compromise third-party infrastructure and repurpose it to support attacks against AI systems. Rather than buying, leasing, registering, or otherwise legitimately acquiring a resource, the adversary gains unauthorized control of infrastructure owned or operated by another party.

Compromised infrastructure may include physical or cloud servers, domains, network devices, third-party web and DNS services, software or artifact repositories, development workspaces, compute services, and other externally hosted resources.

In operations involving AI systems, adversaries may compromise infrastructure used for model development, artifact hosting, dataset processing, evaluation, inference, agent tooling, or AI operations. They may repurpose this infrastructure to host malicious artifacts, stage payloads, run tools or agents, relay traffic, capture credentials, provide command and control, process collected data, or launch attacks against additional systems.

Compromised infrastructure may appear trustworthy because it uses a legitimate provider, established domain, valid certificate, reputable service, or expected AI development platform. It may also provide network access, compute resources, service identities, or trusted relationships that would be difficult for the adversary to establish directly.

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1584](../../../../Enterprise/Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/README.md) · [MITRE ATT&CK T1584](https://attack.mitre.org/techniques/T1584/)

## Case studies

- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s05)

## Mitigations

- [AML.M0016 - Vulnerability Scanning](../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Identify and remediate vulnerabilities to reduce opportunities for adversaries to gain unauthorized control of infrastructure.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0128)
