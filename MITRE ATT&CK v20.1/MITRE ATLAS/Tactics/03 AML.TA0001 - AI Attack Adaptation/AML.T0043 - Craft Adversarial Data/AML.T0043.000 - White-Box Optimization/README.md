# AML.T0043.000 - White-Box Optimization

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0043 - Craft Adversarial Data](../README.md)

In White-Box Optimization, the adversary has full access to the target model and optimizes the adversarial example directly.
Adversarial examples trained in this manner are most effective against the target model.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0010 - Microsoft Azure Service Disruption](../../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s04)
- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s06)
- [AML.CS0058 - Google Photos AI Model Extraction](../../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md#step-s04)

## Mitigations

- [AML.M0003 - Predictive AI Model Hardening](../../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more robust to adversarial inputs.
- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can reduce unnecessary access to AI models and prevent an adversary from achieving white-box access.
- [AML.M0006 - Predictive AI Ensembles](../../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.M0010 - Predictive AI Input Restoration](../../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Input restoration can help remediate adversarial inputs.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Incorporate adversarial input detection to block malicious inputs at inference time.
- [AML.M0017 - AI Model Distribution Methods](../../../../Mitigations/AML.M0017%20-%20AI%20Model%20Distribution%20Methods.md) — With full access to the model, an adversary could perform white-box attacks.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0043.000)
