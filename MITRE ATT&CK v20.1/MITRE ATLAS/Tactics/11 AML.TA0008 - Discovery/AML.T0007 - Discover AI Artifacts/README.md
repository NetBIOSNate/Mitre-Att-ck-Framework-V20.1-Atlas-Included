# AML.T0007 - Discover AI Artifacts

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may search private sources to identify AI learning artifacts that exist on the system and gather information about them.
These artifacts can include the software stack used to train and deploy models, training and testing data management systems, container registries, software repositories, and model zoos.

This information can be used to identify targets for further collection, exfiltration, or disruption, and to tailor and improve attacks.

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S12](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s12)
- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s02)
- [AML.CS0058 - Google Photos AI Model Extraction](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md#step-s00)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can limit an adversary's ability to identify AI models, datasets, and other artifacts on a system.
- [AML.M0012 - Encrypt Sensitive Information](../../../Mitigations/AML.M0012%20-%20Encrypt%20Sensitive%20Information.md) — Encrypting AI artifacts can protect against adversary attempts to discover sensitive information.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0007)
