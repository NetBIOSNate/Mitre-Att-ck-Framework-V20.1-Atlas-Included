# AML.T0010.002 - Data Repository

[MITRE ATLAS](../../../../README.md) / [AML.TA0004 - Initial Access](../../README.md) / [AML.T0010 - Supply Chain Compromise](../README.md)

Adversaries may abuse data repositories or other dataset distribution services to introduce compromised data into downstream AI workflows. They may replace or modify published datasets, manipulate versions or references that consumers resolve, or publish malicious datasets under identities or locations that consumers trust.

The repository or distribution service need not itself be compromised. Adversaries may use legitimate publishing functionality or control an upstream account, namespace, or artifact referenced by a downstream workflow. Compromised data may subsequently be downloaded, synchronized, or incorporated into training, fine-tuning, evaluation, or retrieval systems.

**Tactics**  [AML.TA0004 - Initial Access](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0002 - VirusTotal Poisoning](../../../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md#step-s02)
- [AML.CS0009 - Tay Poisoning](../../../../Case%20Studies/Incidents/AML.CS0009%20-%20Tay%20Poisoning.md) · [S01](../../../../Case%20Studies/Incidents/AML.CS0009%20-%20Tay%20Poisoning.md#step-s01)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.M0007 - Sanitize Training Data](../../../../Mitigations/AML.M0007%20-%20Sanitize%20Training%20Data.md) — Screen acquired datasets for upstream manipulation, comparing them with trusted source records or dataset versions. Quarantine and remediate affected data before training.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify datasets against protected manifests of approved versions and digests before use in training, fine-tuning, evaluation, or retrieval. Reject unauthorized substitutions or changes.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record dataset sources, releases, and relationships to training, evaluation, and retrieval workflows. Use these records to identify systems exposed to compromised sources or releases and trace downstream effects.
- [AML.M0025 - Maintain AI Dataset Provenance](../../../../Mitigations/AML.M0025%20-%20Maintain%20AI%20Dataset%20Provenance.md) — Dataset provenance can protect against supply chain compromise of data.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce controlled untrusted datasets through representative acquisition and ingestion paths. Verify provenance, integrity, sanitization, review, and rejection controls.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on data repositories and distribution services delivering compromised datasets, including affected publishing accounts, dataset versions, and references. Use this intelligence to identify affected data dependencies, prevent ingestion of compromised datasets, and prioritize investigation of workflows that have already consumed them.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010.002)
