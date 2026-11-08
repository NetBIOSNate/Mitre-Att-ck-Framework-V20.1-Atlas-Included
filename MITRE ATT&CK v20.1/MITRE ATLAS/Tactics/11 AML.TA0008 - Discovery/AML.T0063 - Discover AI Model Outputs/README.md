# AML.T0063 - Discover AI Model Outputs

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may discover what information an AI model or service exposes through its outputs. They may investigate both the intended responses and additional model-generated information exposed through the surrounding application. Relevant outputs may include predictions, scores, rankings, representations, generated content, reasoning, explanations, or evaluation results.

Adversaries may inspect responses and related records and submit targeted inputs to determine what information is available, how it relates to the inputs, and what it reveals about the model's behavior. These observations may help identify useful signals for subsequent collection and exploitation.

Identified outputs may guide collection of [Outputs from AI Models](../../13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md) or [Training Data Information from AI Models](../../13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/README.md), support [Recover AI Model Internals](../AML.T0144%20-%20Recover%20AI%20Model%20Internals/README.md), or be used to [Replicate AI Model Behavior](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md).

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0003 - Bypassing Cylance's AI Malware Detection](../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0003%20-%20Bypassing%20Cylance's%20AI%20Malware%20Detection.md#step-s02)
- [AML.CS0008 - ProofPoint Evasion](../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md#step-s00)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s06)

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Obfuscating model outputs can prevent adversaries from collecting sensitive information about the model outputs.
- [AML.M0012 - Encrypt Sensitive Information](../../../Mitigations/AML.M0012%20-%20Encrypt%20Sensitive%20Information.md) — Encrypting model outputs can prevent adversaries from discovering sensitive information about the AI-enabled system or its operations.
- [AML.M0017 - AI Model Distribution Methods](../../../Mitigations/AML.M0017%20-%20AI%20Model%20Distribution%20Methods.md) — Avoiding the deployment of models to edge devices reduces an adversary's ability to collect sensitive information about the model outputs.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Controlling access to the model in production can help prevent adversaries from inferring information from the model outputs.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0063)
