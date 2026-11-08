# AML.T0013 - Discover AI Model Ontology

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may discover the ontology of an AI model's output space, for example, the types of objects a model can detect.
The adversary may discover the ontology by repeated queries to the model, forcing it to enumerate its output space.
Or the ontology may be discovered in a configuration file or in documentation about the model.

The model ontology helps the adversary understand how the model is being used by the victim.
It is useful to the adversary in creating targeted attacks.

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0012 - Face Identification System Evasion via Physical Countermeasures](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0012%20-%20Face%20Identification%20System%20Evasion%20via%20Physical%20Countermeasures.md#step-s03)

## Mitigations

- [AML.M0002 - Predictive AI Output Obfuscation](../../../Mitigations/AML.M0002%20-%20Predictive%20AI%20Output%20Obfuscation.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.M0004 - Limit AI Service Query Volume and Rate](../../../Mitigations/AML.M0004%20-%20Limit%20AI%20Service%20Query%20Volume%20and%20Rate.md) — Limit inference queries to reduce an adversary's ability to discover the model's full output ontology.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0013)
