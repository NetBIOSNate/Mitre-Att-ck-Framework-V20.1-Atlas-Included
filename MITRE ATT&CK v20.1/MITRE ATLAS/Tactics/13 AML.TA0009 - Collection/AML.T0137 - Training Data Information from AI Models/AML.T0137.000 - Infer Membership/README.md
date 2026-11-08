# AML.T0137.000 - Infer Membership

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0137 - Training Data Information from AI Models](../README.md)

Adversaries may infer whether a particular data sample was included in an AI model's training dataset. Samples may include records, text passages, images, or audio samples. Establishing membership may reveal sensitive associations, participation in a private dataset, or use of proprietary information.

Membership inference is a data privacy concern because identifying a sample's inclusion may reveal sensitive associations or participation in a private dataset, even without recovering the underlying data.

Methods may analyze prediction scores, token probabilities, loss values, generated responses, or other differences in model behavior. Adversaries may use statistical tests, shadow models, or auxiliary datasets to distinguish likely training members from nonmembers.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit the volume of API queries in a given period of time to regulate the amount and fidelity of potentially sensitive information an attacker can learn.
- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models for training-data membership disclosure using controlled member and nonmember samples. Use measured privacy risk to guide model selection, training changes, or output restrictions.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if sensitive data has been exfiltrated.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Test whether model outputs reveal the membership of known training samples. Improve privacy-preserving training, output restriction, access controls, and query monitoring.
- [AML.M0040 - Adaptive AI Response Degradation](../../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit signals used to determine whether particular samples were included in training.
- [AML.M0041 - Privacy-Preserving AI Training and Inference](../../../../Mitigations/AML.M0041%20-%20Privacy-Preserving%20AI%20Training%20and%20Inference.md) — Use privacy-preserving mechanisms to limit how much an individual sample's inclusion in training influences model behavior and outputs, reducing the ability to infer whether that sample was used.

## References

- [Membership Inference Attacks against Machine Learning Models](https://arxiv.org/abs/1610.05820)
- [Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations](https://csrc.nist.gov/pubs/ai/100/2/e2025/final)
- [ML04:2023 Membership Inference Attack](https://mltop10.info/ML04_2023-Membership_Inference_Attack.html)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0137.000)
