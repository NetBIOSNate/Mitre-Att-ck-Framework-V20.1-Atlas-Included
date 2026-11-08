# AML.T0115.001 - Models

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0115 - Publish Poisoned AI Artifacts](../README.md)

Adversaries may publish poisoned AI models through model registries, code repositories, or other model distribution channels. The model may be newly created or a modified variant of a legitimate model and may contain manipulated weights, configurations, architecture, serialized code, or other components that produce malicious behavior or execute malicious code.

Victims may subsequently download and integrate the model through [Supply Chain Compromise](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md).

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0019 - PoisonGPT](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md#step-s03)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s05)
- [AML.CS0031 - Malicious Models on Hugging Face](../../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md) · [S01](../../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md#step-s01)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s04)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s04)

## Mitigations

- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Model repositories and downstream consumers should evaluate submitted or acquired models for unexpected outputs, backdoor behavior, and sensitive information disclosure before listing or deployment. Reject or quarantine models that fail acceptance criteria.
- [AML.M0016 - Vulnerability Scanning](../../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Model registries scan uploaded models for unsafe serialization, embedded code, malware, and known vulnerabilities before listing.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on published poisoned models, including identifiers, versions, distribution locations, and evidence of malicious content or behavior. Use this intelligence to block acquisition and use of identified models, investigate systems that have loaded or incorporated them, and support reporting to distribution platforms for removal.

## Software implementations

- [AML.S0007 - huggingface-cli](../../../../Software/Tools/AML.S0007%20-%20huggingface-cli.md) — [huggingface-cli](../../../../Software/Tools/AML.S0007%20-%20huggingface-cli.md) was used to publish model artifacts containing embedded malicious code to Hugging Face repositories through its model upload workflow. [source-2](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0115.001)
