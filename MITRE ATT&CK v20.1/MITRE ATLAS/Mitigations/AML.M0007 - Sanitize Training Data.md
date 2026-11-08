# AML.M0007 - Sanitize Training Data

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Detect, quarantine, and remove or remediate poisoned data before it is used to train an AI model. Apply screening when datasets are acquired or updated, and before new data is incorporated into active learning workflows.

Inspect data samples, annotations, and metadata for evidence of manipulation. Depending on the data and intended task, checks may include label inconsistencies, anomalous samples, unexpected shifts in source or class distributions, suspicious duplication or repeated patterns, and backdoor triggers. Compare findings with trusted dataset versions and combine automated screening with targeted review.

Quarantine suspicious records while they are investigated. Remove malicious additions, correct affected labels or annotations, or restore data from a trusted version where appropriate. Repeat screening after remediation and before utilizing the dataset for training tasks.

If affected data has already been used for training, identify the resulting models and evaluate whether retraining, rollback, or other corrective action is needed. Combine sanitization with [Maintain AI Dataset Provenance](AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) and [Validate AI Model](AML.M0008%20-%20Validate%20AI%20Model.md).

Tools that support screening and sanitizing training data include:

- Adversarial Robustness Toolbox (ART) [art](https://github.com/trusted-ai/adversarial-robustness-toolbox)
- Cleanlab [cleanlab](https://github.com/cleanlab/cleanlab)

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Business and Data Understanding, Data Preparation, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0010.002 - Data Repository](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md) — Screen acquired datasets for upstream manipulation, comparing them with trusted source records or dataset versions. Quarantine and remediate affected data before training.
- [AML.T0018.000 - Poison AI Model](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0018%20-%20Manipulate%20AI%20Model/AML.T0018.000%20-%20Poison%20AI%20Model/README.md) — Screen training data for poisoning that could introduce malicious model behavior. Quarantine and remediate affected data before training.
- [AML.T0020 - Training Data Poisoning](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md) — Screen training samples, labels, annotations, and metadata for poisoning. Quarantine and remediate affected data before training.
- [AML.T0059 - Erode Dataset Integrity](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0059%20-%20Erode%20Dataset%20Integrity/README.md) — Screen samples, labels, annotations, and metadata for manipulation that degrades dataset quality or usefulness. Quarantine and remediate affected data before use.
- [AML.T0115 - Publish Poisoned AI Artifacts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/README.md) — Dataset publishers and repositories should screen submissions for poisoned samples, annotations, or metadata. Quarantine suspected data before publication and remediate confirmed poisoning.
- [AML.T0115.000 - Datasets](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.000%20-%20Datasets/README.md) — Dataset publishers and repositories should screen submissions for poisoned samples, annotations, or metadata. Quarantine suspected data before publication and remediate confirmed poisoning.
- [AML.T0145 - Poison AI Agent Learning Environment](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0145%20-%20Poison%20AI%20Agent%20Learning%20Environment/README.md) — Screen environmental content and resulting interaction data for poisoning before use in learning or adaptation. Quarantine and remediate affected data before use.

## References

- [Adversarial Robustness Toolbox GitHub](https://github.com/trusted-ai/adversarial-robustness-toolbox)
- [Cleanlab GitHub](https://github.com/cleanlab/cleanlab)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0007)
