# AML.T0144 - Recover AI Model Internals

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may infer or recover non-public AI model internals through analysis of model behavior or exposed information. Targets may include architecture, layer dimensions, hyperparameters, decision-tree structure, projection matrices, or numerical parameters.

Methods may use strategically selected queries, equation solving, numerical reconstruction, or statistical identification. Recovery may be partial, approximate, or exact.

**Tactics**  [AML.TA0008 - Discovery](../../11%20AML.TA0008%20-%20Discovery/README.md), [AML.TA0009 - Collection](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0040 - Adaptive AI Response Degradation](../../../Mitigations/AML.M0040%20-%20Adaptive%20AI%20Response%20Degradation.md) — Degrade responses during suspected adversarial activity to limit observations used to infer model architecture, internal structure, or numerical parameters.

## References

- [Stealing Machine Learning Models via Prediction APIs](https://arxiv.org/abs/1609.02943)
- [High Accuracy and High Fidelity Extraction of Neural Networks](https://arxiv.org/abs/1909.01838)
- [Stealing Part of a Production Language Model](https://arxiv.org/abs/2403.06634)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0144)
