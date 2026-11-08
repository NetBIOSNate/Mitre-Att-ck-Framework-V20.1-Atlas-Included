# AML.T0043.004 - Insert Backdoor Trigger

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0043 - Craft Adversarial Data](../README.md)

The adversary may add a perceptual trigger into inference data.
The trigger may be imperceptible or non-obvious to humans.
This technique is used in conjunction with [Poison AI Model](../../AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) and allows the adversary to produce their desired effect in the target model.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s07)

## Mitigations

- [AML.M0003 - Predictive AI Model Hardening](../../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more robust to adversarial inputs.
- [AML.M0006 - Predictive AI Ensembles](../../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models with candidate trigger patterns and input variations for attacker-selected behavior. Reject or remediate affected models and retain trigger tests for subsequent validation.
- [AML.M0010 - Predictive AI Input Restoration](../../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Input restoration can help remediate adversarial inputs.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Incorporate adversarial input detection to block malicious inputs at inference time.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0043.004)
