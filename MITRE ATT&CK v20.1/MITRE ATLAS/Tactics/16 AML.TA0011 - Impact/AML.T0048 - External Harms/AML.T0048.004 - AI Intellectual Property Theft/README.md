# AML.T0048.004 - AI Intellectual Property Theft

[MITRE ATLAS](../../../../README.md) / [AML.TA0011 - Impact](../../README.md) / [AML.T0048 - External Harms](../README.md)

Adversaries may appropriate AI-related intellectual property in a manner that causes economic or competitive harm to the victim organization. Targeted material may include model architectures and weights, training data, or model behaviors and capabilities.

Adversaries may steal AI models or other artifacts via exfiltration from the victim system. Access may be obtained through [Valid Accounts](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md), exposed storage, misconfigured permissions, or exploitation of systems that store or serve the AI artifacts. Alternatively, adversaries may collect [Outputs from AI Models](../../../13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md) to [Replicate AI Model Behavior](../../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) without obtaining the original model artifacts. Model training approaches include knowledge distillation, fine-tuning, and reinforcement learning.

Adversaries may use a stolen or replicated model internally themselves, sell or distribute it, offer competing AI services, or incorporate its capabilities into their own products without compensating the model owner. Possession of the model also allows adversaries to modify or fine-tune it and operate outside the original provider's access controls, usage restrictions, and monitoring. These activities may reduce the victim's competitive advantage and undermine the exclusivity of proprietary AI capabilities.

**Tactics**  [AML.TA0011 - Impact](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0005 - Attack on Machine Translation Services](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s05)
- [AML.CS0018 - Arbitrary Code Execution with Google Colab](../../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0018%20-%20Arbitrary%20Code%20Execution%20with%20Google%20Colab.md#step-s06)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s03)
- [AML.CS0028 - AI Model Tampering via Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0028%20-%20AI%20Model%20Tampering%20via%20Supply%20Chain%20Attack.md#step-s04)
- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S07](../../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s07)
- [AML.CS0058 - Google Photos AI Model Extraction](../../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0058%20-%20Google%20Photos%20AI%20Model%20Extraction.md#step-s06)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S10](../../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s10)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S14](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s14)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent theft of intellectual property.
- [AML.M0012 - Encrypt Sensitive Information](../../../../Mitigations/AML.M0012%20-%20Encrypt%20Sensitive%20Information.md) — Protect machine learning artifacts with encryption.
- [AML.M0017 - AI Model Distribution Methods](../../../../Mitigations/AML.M0017%20-%20AI%20Model%20Distribution%20Methods.md) — Avoiding  the deployment of models to edge devices reduces an adversary's potential access to models or AI artifacts.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0048.004)
