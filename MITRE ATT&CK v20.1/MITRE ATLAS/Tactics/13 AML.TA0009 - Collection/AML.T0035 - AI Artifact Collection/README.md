# AML.T0035 - AI Artifact Collection

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may collect AI artifacts for [Exfiltration](../../15%20AML.TA0010%20-%20Exfiltration/README.md) or for use in [AI Attack Adaptation](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md).
AI artifacts include models and datasets as well as other telemetry data produced when interacting with a model.

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0010 - Microsoft Azure Service Disruption](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0010%20-%20Microsoft%20Azure%20Service%20Disruption.md#step-s02)
- [AML.CS0018 - Arbitrary Code Execution with Google Colab](../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md#step-s04)
- [AML.CS0023 - ShadowRay: Hijacking Exposed Ray Clusters](../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md#step-s02)
- [AML.CS0058 - Google Photos AI Model Extraction](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md#step-s01)

## Mitigations

- [AML.M0001 - Limit Model Artifact Release](../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Limiting the release of artifacts can reduce an adversary's ability to collect model artifacts
- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent or limit the collection of AI artifacts on the victim system.
- [AML.M0012 - Encrypt Sensitive Information](../../../Mitigations/AML.M0012%20-%20Encrypt%20Sensitive%20Information.md) — Protect machine learning artifacts with encryption.
- [AML.M0017 - AI Model Distribution Methods](../../../Mitigations/AML.M0017%20-%20AI%20Model%20Distribution%20Methods.md) — Avoiding the deployment of models to edge devices reduces the attack surface and can prevent adversary artifact collection.

## Software implementations

- [AML.S0002 - Apktool](../../../Software/Tools/AML.S0002%20-%20Apktool.md) — [Apktool](../../../Software/Tools/AML.S0002%20-%20Apktool.md) was used to unpack Android application packages and extract resource files containing embedded TensorFlow and TensorFlow Lite models, making the compiled models available for subsequent analysis and modification. [deep-payload](https://arxiv.org/abs/2101.06896)
- [AML.S0021 - Frida](../../../Software/Tools/AML.S0021%20-%20Frida.md) — [Frida](../../../Software/Tools/AML.S0021%20-%20Frida.md) was used to intercept Google Photos' model-decryption process and capture decrypted TensorFlow Lite models as they were loaded into memory, recovering model artifacts protected by encryption at rest. [skyld](https://skyld.io/google-photos-model-extraction)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0035)
