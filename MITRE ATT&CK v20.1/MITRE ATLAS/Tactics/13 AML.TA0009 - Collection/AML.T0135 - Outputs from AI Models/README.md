# AML.T0135 - Outputs from AI Models

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may gather, retain, and organize outputs from an AI model or service as material for subsequent adversarial operations. Systematic selection and aggregation of responses can produce datasets or observations useful for analyzing the target, reproducing its behavior, or developing further attacks.

Collected material may include predictions and scores, embeddings or other exposed feature representations, generated content, reasoning traces, grades or preference judgments, and model-generated plans or tool calls. Outputs may be acquired directly from inference responses or indirectly from product-generated artifacts and records in which they are embedded or retained.

[Discover AI Model Outputs](../../11%20AML.TA0008%20-%20Discovery/AML.T0063%20-%20Discover%20AI%20Model%20Outputs/README.md) may help adversaries identify available outputs and useful signals before collection. Adversaries may perform [LLM Prompt Crafting](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md) to elicit the outputs they require for follow-on actions. The resulting material may support collection of [Training Data Information from AI Models](../AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/README.md), [Recover AI Model Internals](../../11%20AML.TA0008%20-%20Discovery/AML.T0144%20-%20Recover%20AI%20Model%20Internals/README.md), or [Replicate Behavior from Model Outputs](../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md). Adversaries may also use [Centralized AI Service Request Routing](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md), [Indicator Removal](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0138%20-%20Indicator%20Removal/README.md), and [AI Service Request Metadata Sanitization](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0141%20-%20AI%20Service%20Request%20Metadata%20Sanitization/README.md) to obscure coordinated collection activity.

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0005 - Attack on Machine Translation Services](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0005%20-%20Attack%20on%20Machine%20Translation%20Services.md#step-s03)
- [AML.CS0008 - ProofPoint Evasion](../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0008%20-%20ProofPoint%20Evasion.md#step-s01)
- [AML.CS0014 - Confusing Antimalware Neural Networks](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0014%20-%20Confusing%20Antimalware%20Neural%20Networks.md#step-s03)
- [AML.CS0056 - Model Distillation Campaigns Targeting Anthropic Claude](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0056%20-%20Model%20Distillation%20Campaigns%20Targeting%20Anthropic%20Claude.md#step-s05)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S08](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s08)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S11](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s11)

## Mitigations

- [AML.M0040 - Adaptive AI Response Degradation](../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected collection to reduce the information available for subsequent adversarial operations.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0135)
