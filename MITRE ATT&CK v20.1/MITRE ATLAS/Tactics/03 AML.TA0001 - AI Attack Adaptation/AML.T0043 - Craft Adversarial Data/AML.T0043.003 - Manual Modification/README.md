# AML.T0043.003 - Manual Modification

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0043 - Craft Adversarial Data](../README.md)

Adversaries may manually modify the input data to craft adversarial data.
They may use their knowledge of the target model to modify parts of the data they suspect helps the model in performing its task.
The adversary may use trial and error until they are able to verify they have a working adversarial input.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0000 - Evasion of Deep Learning Detector for Malware C&C Traffic](../../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0000%20-%20Evasion%20of%20Deep%20Learning%20Detector%20for%20Malware%20C%26C%20Traffic.md#step-s03)
- [AML.CS0003 - Bypassing Cylance's AI Malware Detection](../../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md#step-s04)
- [AML.CS0032 - Attempted Evasion of ML Phishing Webpage Detection System](../../../../Case%20Studies/Incidents/AML.CS0032%20-%20Attempted%20Evasion%20of%20ML%20Phishing%20Webpage%20Detection%20System.md) · [S00](../../../../Case%20Studies/Incidents/AML.CS0032%20-%20Attempted%20Evasion%20of%20ML%20Phishing%20Webpage%20Detection%20System.md#step-s00)

## Mitigations

- [AML.M0003 - Predictive AI Model Hardening](../../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more robust to adversarial inputs.
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit volume of model queries to prevent or slow an adversary's ability to refine manually crafted adversarial inputs.
- [AML.M0006 - Predictive AI Ensembles](../../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.M0010 - Predictive AI Input Restoration](../../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Input restoration can help remediate adversarial inputs.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Incorporate adversarial input detection to block malicious inputs at inference time.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0043.003)
