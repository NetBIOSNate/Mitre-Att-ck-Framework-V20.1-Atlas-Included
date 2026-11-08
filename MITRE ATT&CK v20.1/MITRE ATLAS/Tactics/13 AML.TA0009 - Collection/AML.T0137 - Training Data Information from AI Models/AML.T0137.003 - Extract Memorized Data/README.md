# AML.T0137.003 - Extract Memorized Data

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0137 - Training Data Information from AI Models](../README.md)

Adversaries may elicit and recover sensitive content memorized by a generative AI model during training or fine-tuning. Recovered material may include complete training examples or recognizable portions of text, source code, or images, potentially exposing personal information, private communications, or proprietary material. Recovery may take the form of verbatim reproduction or near-duplicate outputs that reveal specific training content.

Adversaries may supply partial passages, contextual cues, or repeated and varied inputs that encourage reproduction of memorized content. They may generate and filter candidate outputs or compare them with available reference material to identify likely training examples. Researchers have recovered verbatim training passages through language-model queries, including from production systems, [scalable-extraction](https://arxiv.org/abs/2311.17035) and extracted memorized training images from diffusion models. [diffusion-extraction](https://arxiv.org/abs/2301.13188)

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Mitigations

- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate generative models for reproduction of sensitive training data using controlled extraction attempts and comparisons with known samples. Investigate confirmed disclosures and repeat evaluation after remediation.
- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect generated outputs for sensitive training content or recognizable portions of protected records before release. Use sensitive-data detection and protected reference matching where available. Block or redact detected disclosures.
- [AML.M0040 - Adaptive AI Response Degradation](../../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to reduce disclosure of memorized training content.
- [AML.M0041 - Privacy-Preserving AI Training and Inference](../../../../Mitigations/AML.M0041%20-%20Privacy-Preserving%20AI%20Training%20and%20Inference.md) — Use privacy-preserving mechanisms to limit model memorization of individual training records and their influence on outputs, reducing the ability to elicit training content.

## References

- [Extracting Training Data from Large Language Models](https://arxiv.org/abs/2012.07805)
- [Scalable Extraction of Training Data from (Production) Language Models](https://arxiv.org/abs/2311.17035)
- [Extracting Training Data from Diffusion Models](https://arxiv.org/abs/2301.13188)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0137.003)
