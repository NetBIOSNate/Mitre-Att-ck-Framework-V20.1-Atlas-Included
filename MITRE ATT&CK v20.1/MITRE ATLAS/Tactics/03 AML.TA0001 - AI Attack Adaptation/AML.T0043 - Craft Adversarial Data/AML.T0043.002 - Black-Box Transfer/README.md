# AML.T0043.002 - Black-Box Transfer

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0043 - Craft Adversarial Data](../README.md)

In Black-Box Transfer attacks, the adversary uses one or more proxy models (trained via [Replicate AI Model Behavior](../../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) or [Replicate Behavior from Model Outputs](../../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md)) they have full access to and are representative of the target model.
The adversary uses [White-Box Optimization](../AML.T0043.000%20-%20White-Box%20Optimization/README.md) on the proxy models to generate adversarial examples.
If the set of proxy models are close enough to the target model, the adversarial example should generalize from one to another.
This means that an attack that works for the proxy models will likely then work for the target model.
If the adversary has [AI Model Inference API Access](../../../05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md), they may use [Verify Attack](../../AML.T0042%20-%20Verify%20Attack/README.md) to confirm the attack is working and incorporate that information into their training process.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0005 - Attack on Machine Translation Services](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s06)
- [AML.CS0008 - ProofPoint Evasion](../../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md#step-s03)
- [AML.CS0014 - Confusing Antimalware Neural Networks](../../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md#step-s06)

## Mitigations

- [AML.M0003 - Predictive AI Model Hardening](../../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more robust to adversarial inputs.
- [AML.M0006 - Predictive AI Ensembles](../../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.M0010 - Predictive AI Input Restoration](../../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Input restoration can help remediate adversarial inputs.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Incorporate adversarial input detection to block malicious inputs at inference time.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0043.002)
