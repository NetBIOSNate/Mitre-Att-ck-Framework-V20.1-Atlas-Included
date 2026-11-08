# AML.T0020 - Training Data Poisoning

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may manipulate data used for training or fine-tuning an AI model to influence the resulting model's behavior. Adversaries may add, remove, or modify data samples; alter labels or annotations; or manipulate feedback and data-collection processes.

Training data poisoning may cause targeted errors, introduce biased or unsafe behavior, degrade model performance, or embed backdoors activated by specific inputs. The resulting behavior may persist in the trained model after the poisoned data is no longer accessible.

Adversaries may poison data directly after gaining access to a training pipeline, or poisoned datasets may be introduced through [Supply Chain Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md).

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0002 - VirusTotal Poisoning](../../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md#step-s03)
- [AML.CS0009 - Tay Poisoning](../../../Case%20Studies/Incidents/AML.CS0009%20-%20Tay%20Poisoning.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0009%20-%20Tay%20Poisoning.md#step-s02)
- [AML.CS0025 - Web-Scale Data Poisoning: Split-View Attack](../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0025%20-%20Web-Scale%20Data%20Poisoning%20-%20Split-View%20Attack.md#step-s02)

## Mitigations

- [AML.M0001 - Limit Model Artifact Release](../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Published datasets can be a target for poisoning attacks.
- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.M0007 - Sanitize Training Data](../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Screen training samples, labels, annotations, and metadata for poisoning. Quarantine and remediate affected data before training.
- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models against independently maintained evaluation data for targeted errors, backdoor behavior, or performance changes caused by poisoning. Repeat evaluation after dataset remediation and retraining.
- [AML.M0014 - Verify AI Artifacts](../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify training datasets and annotations against protected manifests before training. Investigate unexpected additions, removals, or changes, and update reference values only through an authorized approval process.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record training and fine-tuning dataset identities, versions, and relationships to derived models and deployed applications. Use these records to trace poisoned data to affected models and applications and guide dataset replacement, model reevaluation, or retraining.
- [AML.M0025 - Maintain AI Dataset Provenance](../../../Mitigations/AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) — Dataset provenance can protect against poisoning of training data
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce controlled poisoned records or triggers into representative data pipelines. Verify and improve provenance, sanitization, review, drift detection, model validation, and rollback controls.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0020)
