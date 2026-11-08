# AML.T0014 - Discover AI Model Family

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may discover the general family of a model.
General information about the model may be revealed in documentation, or the adversary may use carefully constructed examples and analyze the model's responses to categorize it.

Knowledge of the model family can help the adversary identify means of attacking the model and help tailor the attack.

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit inference queries to reduce an adversary's ability to infer the family of AI model.
- [AML.M0006 - Predictive AI Ensembles](../../../Mitigations/AML.M0006%20-%20Predictive%20AI%20Ensembles.md) — Use multiple different models to fool adversaries of which type of model is used and how the model used.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0014)
