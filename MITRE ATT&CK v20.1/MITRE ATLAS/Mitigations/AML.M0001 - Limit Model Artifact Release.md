# AML.M0001 - Limit Model Artifact Release

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit public release of technical project details including data, algorithms, model architectures, and model checkpoints that are used in production, or that are representative of those used in production.

**Mitigation categories**  Policy

**Lifecycle phases**  Business and Data Understanding, Deployment

## Techniques mitigated

- [AML.T0002.000 - Datasets](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.000%20-%20Datasets/README.md) — Limiting the release of datasets can reduce an adversary's ability to target production models trained on the same or similar data.
- [AML.T0002.001 - Models](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/AML.T0002.001%20-%20Models/README.md) — Limiting the release of model architectures and checkpoints can reduce an adversary's ability to target those models.
- [AML.T0005 - Replicate AI Model Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) — Limiting the release of model artifacts can reduce an adversary's ability to create an accurate proxy model.
- [AML.T0005.000 - Replicate Behavior from Gathered AI Artifacts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.000%20-%20Replicate%20Behavior%20from%20Gathered%20AI%20Artifacts/README.md) — Limiting the release of model artifacts can reduce an adversary's ability to create an accurate proxy model.
- [AML.T0016 - Obtain Capabilities](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/README.md) — Limit public release of production model artifacts that adversaries could acquire and adapt as operational capabilities.
- [AML.T0016.002 - Generative AI](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.002%20-%20Generative%20AI/README.md) — Limit public release of production model artifacts that adversaries could acquire and adapt as operational capabilities.
- [AML.T0020 - Training Data Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md) — Published datasets can be a target for poisoning attacks.
- [AML.T0035 - AI Artifact Collection](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0035%20-%20AI%20Artifact%20Collection/README.md) — Limiting the release of artifacts can reduce an adversary's ability to collect model artifacts
- [AML.T0116 - Autonomous Reconnaissance](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — Limit release of AI artifacts to reduce an autonomous agent's ability to conduct targeting.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0001)
