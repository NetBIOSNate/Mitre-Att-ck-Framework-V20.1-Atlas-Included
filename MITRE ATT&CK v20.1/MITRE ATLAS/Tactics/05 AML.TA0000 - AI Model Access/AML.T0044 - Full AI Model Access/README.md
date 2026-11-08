# AML.T0044 - Full AI Model Access

[MITRE ATLAS](../../../README.md) / [AML.TA0000 - AI Model Access](../README.md)

Adversaries may gain full "white-box" access to an AI model.
This means the adversary has complete knowledge of the model architecture, its parameters, and class ontology.
They may exfiltrate the model to [Craft Adversarial Data](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) and [Verify Attack](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) in an offline environment where it is hard to detect their behavior.

**Tactics**  [AML.TA0000 - AI Model Access](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s02)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s02)
- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s03)
- [AML.CS0058 - Google Photos AI Model Extraction](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md#step-s03)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls on models and data at rest can help prevent full model access.
- [AML.M0017 - AI Model Distribution Methods](../../../Mitigations/AML.M0017%20-%20AI%20Model%20Distribution%20Methods.md) — Not distributing the model in software to edge devices, can limit an adversary's ability to gain full access to the model.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0044)
