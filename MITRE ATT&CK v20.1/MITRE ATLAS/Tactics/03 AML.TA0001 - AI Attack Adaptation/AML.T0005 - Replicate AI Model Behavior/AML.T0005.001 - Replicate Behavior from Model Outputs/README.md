# AML.T0005.001 - Replicate Behavior from Model Outputs

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0005 - Replicate AI Model Behavior](../README.md)

Adversaries may replicate an AI model's behavior or selected capabilities by training or adapting another model using outputs or other sources of supervision obtained from the target. Supervisory material may include labels, scores, probabilities, generated responses, reasoning explanations, evaluations, reward or preference signals, and tool-use or agent interaction trajectories.

The adversary may use supervised learning, knowledge distillation, supervised fine-tuning, reinforcement learning, or related methods. Target-generated material may be filtered, combined with other data, or acquired from multiple teacher models. The resulting model may reproduce selected capabilities rather than the target's full behavior, architecture, parameters, or output ontology.

**Tactics**  [AML.TA0003 - Resource Development](../../../02%20AML.TA0003%20-%20Resource%20Development/README.md), [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0005 - Attack on Machine Translation Services](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s04)
- [AML.CS0008 - ProofPoint Evasion](../../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md#step-s02)
- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S06](../../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s06)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S09](../../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s09)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S13](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s13)

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Obfuscating model outputs restricts an adversary's ability to create an accurate proxy model by querying a model and observing its outputs.
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit inference queries to reduce the labeled outputs available for training a proxy model.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if a proxy training dataset has been exfiltrated.
- [AML.M0040 - Adaptive AI Response Degradation](../../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected replication activity to reduce the usefulness of collected outputs for reproducing the target model's behavior or capabilities.

## Software implementations

- [AML.S0000 - Proof Pudding](../../../../Software/Tools/AML.S0000%20-%20Proof%20Pudding.md) — [Proof Pudding](../../../../Software/Tools/AML.S0000%20-%20Proof%20Pudding.md) trains proxy models using bag-of-words representations of email text and links paired with Proofpoint scores. These models approximate the target's scoring behavior and predict scores for new inputs before delivery. [github](https://github.com/moohax/Proof-Pudding)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0005.001)
