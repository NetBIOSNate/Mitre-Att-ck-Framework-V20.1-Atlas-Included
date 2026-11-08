# AML.T0115.000 - Datasets

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0115 - Publish Poisoned AI Artifacts](../README.md)

Adversaries may publish poisoned datasets intended for training or fine-tuning AI models. The dataset may be newly created or a modified variant of a legitimate dataset and may contain manipulated samples, labels, annotations, or metadata.

Adversaries may distribute poisoned datasets through dataset repositories, code repositories, file-sharing services, or compromised data sources. A victim that incorporates the dataset into a training pipeline may be affected by [Training Data Poisoning](../../../07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md), potentially through [Supply Chain Compromise](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md).

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0025 - Web-Scale Data Poisoning: Split-View Attack](../../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md#step-s03)

## Mitigations

- [AML.M0007 - Sanitize Training Data](../../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Dataset publishers and repositories should screen submissions for poisoned samples, annotations, or metadata. Quarantine suspected data before publication and remediate confirmed poisoning.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on published poisoned datasets, including identifiers, versions, distribution locations, and evidence of manipulated samples, labels, annotations, or metadata. Use this intelligence to block acquisition and use of identified datasets, investigate training workflows and models that have consumed them, and support reporting to distribution platforms for removal.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0115.000)
