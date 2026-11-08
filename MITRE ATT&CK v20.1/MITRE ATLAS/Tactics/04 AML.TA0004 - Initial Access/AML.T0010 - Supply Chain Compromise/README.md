# AML.T0010 - Supply Chain Compromise

[MITRE ATLAS](../../../README.md) / [AML.TA0004 - Initial Access](../README.md)

Adversaries may manipulate products, components, or their development and delivery mechanisms before they reach downstream consumers to compromise data or systems. Manipulation may involve source code, dependencies, development tools, build environments, software updates, distribution channels, or hardware.

In AI environments, targets may include [Hardware](AML.T0010.000%20-%20Hardware/README.md), [Software](AML.T0010.001%20-%20Software/README.md), [Data Repositories](AML.T0010.002%20-%20Data%20Repository/README.md), [Model Repositories](AML.T0010.003%20-%20Model%20Repository/README.md), [Container Registries](AML.T0010.004%20-%20Container%20Registry/README.md), and [AI Agent Tools](AML.T0010.005%20-%20AI%20Agent%20Tool/README.md). Compromised components may introduce malicious executable behavior, alter model behavior, or provide unauthorized access when incorporated into downstream systems.

Autonomous AI agents may also select and conduct supply-chain attacks against software or services outside the AI supply chain. An agent may develop a malicious contribution, submit it through an established development workflow, and attempt to persuade maintainers to approve and distribute it. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

**Tactics**  [AML.TA0004 - Initial Access](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1195](../../../../Enterprise/Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md) · [MITRE ATT&CK T1195](https://attack.mitre.org/techniques/T1195/)

## Sub-techniques

- [AML.T0010.005 - AI Agent Tool](AML.T0010.005%20-%20AI%20Agent%20Tool/README.md)
- [AML.T0010.004 - Container Registry](AML.T0010.004%20-%20Container%20Registry/README.md)
- [AML.T0010.002 - Data Repository](AML.T0010.002%20-%20Data%20Repository/README.md)
- [AML.T0010.000 - Hardware](AML.T0010.000%20-%20Hardware/README.md)
- [AML.T0010.003 - Model Repository](AML.T0010.003%20-%20Model%20Repository/README.md)
- [AML.T0010.001 - Software](AML.T0010.001%20-%20Software/README.md)

## Case studies

- [AML.CS0031 - Malicious Models on Hugging Face](../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md#step-s03)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S11](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s11)

## Mitigations

- [AML.M0014 - Verify AI Artifacts](../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify AI artifacts and associated software, data, and configuration against protected approval records before incorporating them into downstream systems.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record component identities, versions, sources, and dependencies across the AI supply chain. Use these records to identify builds and deployments affected by reported compromises and guide replacement or rollback.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Exercise the introduction of controlled untrusted software, data, models, and agent tools through representative acquisition and deployment paths. Remediate weaknesses in provenance, validation, approvals, isolation, and rollback.
- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on compromised suppliers, components, and distribution channels. Use this intelligence to identify affected dependencies, prevent their introduction into downstream systems, and prioritize investigation and replacement of compromised components.

## References

- [Incident Report: unsanctioned agent behaviour during cyber testing](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010)
