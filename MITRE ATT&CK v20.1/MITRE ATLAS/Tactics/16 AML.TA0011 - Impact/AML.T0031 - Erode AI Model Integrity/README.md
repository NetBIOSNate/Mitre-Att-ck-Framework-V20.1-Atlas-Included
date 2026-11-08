# AML.T0031 - Erode AI Model Integrity

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may degrade the target model's performance with adversarial data inputs to erode confidence in the system over time.
This can lead to the victim organization wasting time and money both attempting to fix the system and performing the tasks it was meant to automate by hand.

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0005 - Attack on Machine Translation Services](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s08)
- [AML.CS0006 - ClearviewAI Misconfiguration](../../../Case%20Studies/Incidents/AML.CS0006%20-%20ClearviewAI%20Misconfiguration.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0006%20-%20ClearviewAI%20Misconfiguration.md#step-s03)
- [AML.CS0009 - Tay Poisoning](../../../Case%20Studies/Incidents/AML.CS0009%20-%20Tay%20Poisoning.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0009%20-%20Tay%20Poisoning.md#step-s03)
- [AML.CS0019 - PoisonGPT](../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md#step-s05)
- [AML.CS0025 - Web-Scale Data Poisoning: Split-View Attack](../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md#step-s05)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s08)

## Mitigations

- [AML.M0003 - Predictive AI Model Hardening](../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are less susceptible to integrity attacks.
- [AML.M0006 - Predictive AI Ensembles](../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using multiple different models increases robustness to attack.
- [AML.M0010 - Predictive AI Input Restoration](../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Preprocessing model inputs can prevent malicious data from going through the machine learning pipeline.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Incorporate adversarial input detection into the pipeline before inputs reach the model.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0031)
