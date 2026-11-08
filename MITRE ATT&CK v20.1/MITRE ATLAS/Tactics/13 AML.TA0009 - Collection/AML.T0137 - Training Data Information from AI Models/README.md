# AML.T0137 - Training Data Information from AI Models

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may obtain sensitive information about the data used to train or fine-tune an AI model by analyzing its outputs or behavior. This can expose private associations, personally identifiable information, or proprietary data, creating data privacy concerns and supporting subsequent adversarial operations.

Adversaries may determine whether particular samples were used in training through [Infer Membership](AML.T0137.000%20-%20Infer%20Membership/README.md), identify aggregate characteristics of the training dataset through [Infer Properties](AML.T0137.001%20-%20Infer%20Properties/README.md), infer sensitive attributes or reconstruct representative examples through [Invert AI Model](AML.T0137.002%20-%20Invert%20AI%20Model/README.md), or recover retained training content through [Extract Memorized Data](AML.T0137.003%20-%20Extract%20Memorized%20Data/README.md).

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Sub-techniques

- [AML.T0137.003 - Extract Memorized Data](AML.T0137.003%20-%20Extract%20Memorized%20Data/README.md)
- [AML.T0137.000 - Infer Membership](AML.T0137.000%20-%20Infer%20Membership/README.md)
- [AML.T0137.001 - Infer Properties](AML.T0137.001%20-%20Infer%20Properties/README.md)
- [AML.T0137.002 - Invert AI Model](AML.T0137.002%20-%20Invert%20AI%20Model/README.md)

## Mitigations

- [AML.M0040 - Adaptive AI Response Degradation](../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit signals used to infer information about private data used in model training.
- [AML.M0041 - Privacy-Preserving AI Training and Inference](../../../Mitigations/AML.M0041%20-%20Privacy-Preserving%20AI%20Training%20and%20Inference.md) — Use privacy-preserving mechanisms to limit how much individual training data influences model behavior and outputs, reducing disclosure of sensitive information about the data used to train or fine-tune the model.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0137)
