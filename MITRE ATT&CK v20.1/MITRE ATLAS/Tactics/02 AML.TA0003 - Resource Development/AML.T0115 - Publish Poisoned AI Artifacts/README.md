# AML.T0115 - Publish Poisoned AI Artifacts

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may create or modify AI artifacts and publish them through public or shared distribution channels to facilitate compromise of downstream AI systems. Poisoned AI artifacts may include datasets, models, and AI agent tools containing malicious content, behaviors, code, or configurations.

Adversaries may publish novel artifacts or malicious variants of legitimate artifacts through dataset or model repositories, package registries, source code repositories, tool hubs, or remotely hosted services. Victims may subsequently acquire and integrate these artifacts through [Supply Chain Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md).

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0115.002 - AI Agent Tools](AML.T0115.002%20-%20AI%20Agent%20Tools/README.md)
- [AML.T0115.000 - Datasets](AML.T0115.000%20-%20Datasets/README.md)
- [AML.T0115.001 - Models](AML.T0115.001%20-%20Models/README.md)

## Mitigations

- [AML.M0007 - Sanitize Training Data](../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Dataset publishers and repositories should screen submissions for poisoned samples, annotations, or metadata. Quarantine suspected data before publication and remediate confirmed poisoning.
- [AML.M0016 - Vulnerability Scanning](../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Model and agent tool registries scan uploaded artifacts for malicious content before listing.
- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on published poisoned AI artifacts, including identifiers, versions, distribution locations, and evidence of malicious content or behavior. Use this intelligence to block acquisition and use of identified artifacts, investigate existing exposure, and support reporting to distribution platforms for removal.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0115)
