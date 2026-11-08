# AML.M0002 - Predictive AI Output Obfuscation

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Reduce the fidelity and amount of information returned by predictive AI inference endpoints to make model discovery, extraction, replication, and black-box adversarial-example optimization more difficult.

Limit outputs to those required by the application. Depending on the use case, this may include withholding or reducing the precision of confidence scores, logits, class rankings, labels, embeddings, or additional model metadata.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Evaluation, Deployment

## Techniques mitigated

- [AML.T0005 - Replicate AI Model Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) — Obfuscating model outputs can reduce an adversary's ability to produce an accurate proxy model.
- [AML.T0005.001 - Replicate Behavior from Model Outputs](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md) — Obfuscating model outputs restricts an adversary's ability to create an accurate proxy model by querying a model and observing its outputs.
- [AML.T0013 - Discover AI Model Ontology](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0013%20-%20Discover%20AI%20Model%20Ontology/README.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.T0014 - Discover AI Model Family](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0014%20-%20Discover%20AI%20Model%20Family/README.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.T0042 - Verify Attack](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) — Obfuscating model outputs reduces an adversary's ability to verify the efficacy of an attack.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Obfuscating model outputs reduces an adversary's ability to generate effective adversarial data.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Obfuscating model outputs reduces an adversary's ability to create effective adversarial inputs.
- [AML.T0063 - Discover AI Model Outputs](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0063%20-%20Discover%20AI%20Model%20Outputs/README.md) — Obfuscating model outputs can prevent adversaries from collecting sensitive information about the model outputs.
- [AML.T0137.000 - Infer Membership](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.000%20-%20Infer%20Membership/README.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs
- [AML.T0137.002 - Invert AI Model](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.002%20-%20Invert%20AI%20Model/README.md) — Suggested approaches:
  - Restrict the number of results shown
  - Limit specificity of output class ontology
  - Use randomized smoothing techniques
  - Reduce the precision of numerical outputs

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0002)
