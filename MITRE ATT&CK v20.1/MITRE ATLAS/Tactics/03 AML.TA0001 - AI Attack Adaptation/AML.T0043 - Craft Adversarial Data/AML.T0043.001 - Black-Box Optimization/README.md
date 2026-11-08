# AML.T0043.001 - Black-Box Optimization

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0043 - Craft Adversarial Data](../README.md)

In Black-Box attacks, the adversary has black-box (i.e. [AI Model Inference API Access](../../../05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md) via API access) access to the target model.
With black-box attacks, the adversary may be using an API that the victim is monitoring.
These attacks are generally less effective and require more inferences than [White-Box Optimization](../AML.T0043.000%20-%20White-Box%20Optimization/README.md) attacks, but they require much less access.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0001 - Botnet Domain Generation Algorithm (DGA) Detection Evasion](../../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0001%20-%20Botnet%20Domain%20Generation%20Algorithm%20%28DGA%29%20Detection%20Evasion.md#step-s03)
- [AML.CS0011 - Microsoft Edge AI Evasion](../../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0011%20-%20Microsoft%20Edge%20AI%20Evasion.md#step-s03)

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Obfuscating model outputs reduces an adversary's ability to create effective adversarial inputs.
- [AML.M0003 - Predictive AI Model Hardening](../../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more robust to adversarial inputs.
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit volume of model queries to prevent or slow an adversary's ability to perform black-box optimization attacks.
- [AML.M0006 - Predictive AI Ensembles](../../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.M0010 - Predictive AI Input Restoration](../../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Input restoration adds an extra layer of unknowns and randomness when an adversary evaluates the input-output relationship.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Monitor queries and query patterns to the target model, block access if suspicious queries are detected.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Access controls on model APIs can deny adversaries the access required for black-box optimization methods.
- [AML.M0040 - Adaptive AI Response Degradation](../../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit feedback used to optimize adversarial inputs against the target model.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0043.001)
