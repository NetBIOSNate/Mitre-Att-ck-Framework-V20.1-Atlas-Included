# AML.T0005 - Replicate AI Model Behavior

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may replicate an AI model's behavior or selected capabilities by training or adapting another model to approximate the target's responses, decision regions, or other characteristics. The result may be a surrogate for attack development, a functional replica, or a student model incorporating selected target capabilities.

Replication may cover a whole model or only the behaviors relevant to the adversary's objective. Models may be developed from gathered artifacts, collected model outputs, or adaptation of an existing model. How closely the model must reproduce the target's behavior depends on the adversary's goals. 

Replicate AI Model Behavior supports adversaries' ability to achieve [Resource Development](../README.md) when producing a reusable model capability and [AI Attack Adaptation](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) when tailoring a model for a particular target or operation.

**Tactics**  [AML.TA0003 - Resource Development](../README.md), [AML.TA0001 - AI Attack Adaptation](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0005.002 - Adapt Existing Model to Replicate Behavior](AML.T0005.002%20-%20Adapt%20Existing%20Model%20to%20Replicate%20Behavior/README.md)
- [AML.T0005.000 - Replicate Behavior from Gathered AI Artifacts](AML.T0005.000%20-%20Replicate%20Behavior%20from%20Gathered%20AI%20Artifacts/README.md)
- [AML.T0005.001 - Replicate Behavior from Model Outputs](AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)

## Case studies

- [AML.CS0000 - Evasion of Deep Learning Detector for Malware C&C Traffic](../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md#step-s02)
- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s05)
- [AML.CS0014 - Confusing Antimalware Neural Networks](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md#step-s04)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limiting release of technical information about a model and training data can reduce an adversary's ability to create an accurate proxy model.
- [AML.M0001 - Limit Model Artifact Release](../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Limiting the release of model artifacts can reduce an adversary's ability to create an accurate proxy model.
- [AML.M0002 - Predictive AI Output Obfuscation](../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Obfuscating model outputs can reduce an adversary's ability to produce an accurate proxy model.
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit inference queries to reduce the labeled outputs available for training a proxy model.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Access controls on models APIs can reduce an adversary's ability to produce an accurate proxy model.
- [AML.M0040 - Adaptive AI Response Degradation](../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected replication activity to reduce the usefulness of collected outputs for reproducing the target model's behavior or capabilities.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0005)
