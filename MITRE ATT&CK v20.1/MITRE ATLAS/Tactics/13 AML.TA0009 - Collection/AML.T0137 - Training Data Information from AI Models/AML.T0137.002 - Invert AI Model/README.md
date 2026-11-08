# AML.T0137.002 - Invert AI Model

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0137 - Training Data Information from AI Models](../README.md)

Adversaries may infer sensitive aggregate attributes or reconstruct representative examples of data used to train or fine-tune a target AI model by analyzing its behavior, outputs, or exposed representations. Reconstructed information may reveal characteristics of individuals, records, or classes represented in the training data without reproducing a particular training example.

Methods may optimize candidate inputs, combine known attributes with model-derived signals, or use learned inversion models. Useful observations may include prediction scores, probabilities, embeddings, or gradients where exposed.

Results may include inferred sensitive attributes, approximate reconstructions, or representative examples associated with a target identity or class. Such results do not by themselves establish that a reconstructed example was present in the training dataset.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit the volume of API queries in a given period of time to regulate the amount and fidelity of potentially sensitive information an attacker can learn.
- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models for reconstruction of sensitive attributes or representative training-data examples from outputs or representations exposed in deployment. Use demonstrated privacy risks to guide remediation or output restrictions.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if sensitive data has been exfiltrated.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Attempt to reconstruct sensitive records, attributes, or representative training information from model outputs. Remediate leakage through model changes, output minimization, privacy controls, and restricted inference access.
- [AML.M0040 - Adaptive AI Response Degradation](../../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit information used to reconstruct representative training examples.
- [AML.M0041 - Privacy-Preserving AI Training and Inference](../../../../Mitigations/AML.M0041%20-%20Privacy-Preserving%20AI%20Training%20and%20Inference.md) — Use privacy-preserving mechanisms to limit information about training data reflected in model behavior and outputs, reducing the ability to infer sensitive attributes or reconstruct representative examples.

## References

- [Model Inversion Attacks: A Survey of Approaches and Countermeasures](https://arxiv.org/abs/2411.10023)
- [Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations](https://csrc.nist.gov/pubs/ai/100/2/e2025/final)
- [ML03:2023 Model Inversion Attack](https://mltop10.info/ML03_2023-Model_Inversion_Attack.html)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0137.002)
