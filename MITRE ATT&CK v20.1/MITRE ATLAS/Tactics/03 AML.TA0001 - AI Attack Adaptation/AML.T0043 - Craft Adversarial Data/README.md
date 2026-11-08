# AML.T0043 - Craft Adversarial Data

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversarial data are inputs to an AI model that have been modified such that they cause the adversary's desired effect in the target model.
Effects can range from misclassification, to missed detections, to maximizing energy consumption.
Typically, the modification is constrained in magnitude or location so that a human still perceives the data as if it were unmodified, but human perceptibility may not always be a concern depending on the adversary's intended effect.
For example, an adversarial input for an image classification task is an image the AI model would misclassify, but a human would still recognize as containing the correct class.

Depending on the adversary's knowledge of and access to the target model, the adversary may use different classes of algorithms to develop the adversarial example such as [White-Box Optimization](AML.T0043.000%20-%20White-Box%20Optimization/README.md), [Black-Box Optimization](AML.T0043.001%20-%20Black-Box%20Optimization/README.md), [Black-Box Transfer](AML.T0043.002%20-%20Black-Box%20Transfer/README.md), or [Manual Modification](AML.T0043.003%20-%20Manual%20Modification/README.md).

The adversary may perform [Verify Attack](../AML.T0042%20-%20Verify%20Attack/README.md) to confirm that their approach works if they have white-box or inference API access to the model.
This allows the adversary to gain confidence their attack is effective in a live environment where their attack may be noticed.
They can then use the attack at a later time to accomplish their goals.
An adversary may optimize adversarial examples for [Evade AI Model](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md), or to [Erode AI Model Integrity](../../16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md).

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0043.001 - Black-Box Optimization](AML.T0043.001%20-%20Black-Box%20Optimization/README.md)
- [AML.T0043.002 - Black-Box Transfer](AML.T0043.002%20-%20Black-Box%20Transfer/README.md)
- [AML.T0043.004 - Insert Backdoor Trigger](AML.T0043.004%20-%20Insert%20Backdoor%20Trigger/README.md)
- [AML.T0043.003 - Manual Modification](AML.T0043.003%20-%20Manual%20Modification/README.md)
- [AML.T0043.000 - White-Box Optimization](AML.T0043.000%20-%20White-Box%20Optimization/README.md)

## Case studies

- [AML.CS0002 - VirusTotal Poisoning](../../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md#step-s01)

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Obfuscating model outputs reduces an adversary's ability to generate effective adversarial data.
- [AML.M0003 - Predictive AI Model Hardening](../../../Mitigations/AML.M0003%20-%20Predictive%20AI%20Model%20Hardening.md) — Hardened models are more robust to adversarial inputs.
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit volume of model queries to prevent or slow an adversary's ability to create adversarial inputs.
- [AML.M0006 - Predictive AI Ensembles](../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Using an ensemble of models increases the difficulty of crafting effective adversarial data and improves overall robustness.
- [AML.M0010 - Predictive AI Input Restoration](../../../Mitigations/AML.M0010%20-%20Predictive%20AI%20Input%20Restoration.md) — Input restoration can help remediate adversarial inputs.
- [AML.M0015 - Predictive AI Adversarial Input Detection](../../../Mitigations/AML.M0015%20-%20Predictive%20AI%20Adversarial%20Input%20Detection.md) — Incorporate adversarial input detection to block malicious inputs at inference time.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Access controls on model APIs can restrict an adversary's access required to generate adversarial data.
- [AML.M0040 - Adaptive AI Response Degradation](../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit feedback used to optimize adversarial inputs against the target model.

## Software implementations

- [AML.S0001 - metame](../../../Software/Tools/AML.S0001%20-%20metame.md) — [metame](../../../Software/Tools/AML.S0001%20-%20metame.md) generates modified executables by randomly substituting instructions with logically equivalent, same-sized alternatives. These mutations alter the binary representation while aiming to preserve program behavior. [github](https://github.com/a0rtega/metame)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0043)
