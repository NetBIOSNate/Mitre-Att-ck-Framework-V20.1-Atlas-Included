# AML.T0137.001 - Infer Properties

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0137 - Training Data Information from AI Models](../README.md)

Adversaries may infer sensitive global properties of the data used to train an AI model. Properties may include dataset provenance, population composition, relative class proportions, domain coverage, collection period, or the presence of a category or group.

The adversary may compare output distributions, fit analytical or learned estimators, use auxiliary datasets, or contrast models trained with different known properties. The target is a property of the training data rather than membership of an individual record.

Inferred properties of the training dataset may help adversaries identify a model's likely origin, distinguish between candidate models, identify underrepresented populations or domains, and tailor subsequent attacks to suspected weaknesses.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0040 - Adaptive AI Response Degradation](../../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit signals used to infer sensitive characteristics of the training dataset.
- [AML.M0041 - Privacy-Preserving AI Training and Inference](../../../../Mitigations/AML.M0041%20-%20Privacy-Preserving%20AI%20Training%20and%20Inference.md) — Use privacy-preserving mechanisms to limit information about training data reflected in model behavior and outputs, reducing the ability to infer its aggregate properties.

## References

- [Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations](https://csrc.nist.gov/pubs/ai/100/2/e2025/final)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0137.001)
