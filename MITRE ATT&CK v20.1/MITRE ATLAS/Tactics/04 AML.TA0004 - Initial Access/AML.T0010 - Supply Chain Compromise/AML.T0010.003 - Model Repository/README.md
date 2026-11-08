# AML.T0010.003 - Model Repository

[MITRE ATLAS](../../../../README.md) / [AML.TA0004 - Initial Access](../../README.md) / [AML.T0010 - Supply Chain Compromise](../README.md)

Adversaries may abuse model repositories or other model distribution services to introduce compromised models into downstream AI systems. They may replace published artifacts, manipulate model versions or references that consumers resolve, or publish malicious models under identities or locations that consumers trust.

The repository or distribution service need not itself be compromised. Adversaries may use legitimate publishing functionality or control an upstream account, namespace, or artifact referenced by a downstream workflow. Consumers may retrieve the compromised model for inference, fine-tuning, or incorporation into another application.

**Tactics**  [AML.TA0004 - Initial Access](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0013 - Backdoor Attack on Deep Learning Models in Mobile Apps](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0013%20-%20Backdoor%20Attack%20on%20Deep%20Learning%20Models%20in%20Mobile%20Apps.md#step-s06)
- [AML.CS0019 - PoisonGPT](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0019%20-%20PoisonGPT.md#step-s04)
- [AML.CS0023 - ShadowRay: Hijacking Exposed Ray Clusters](../../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md) · [S05](../../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md#step-s05)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s06)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s05)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s05)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Access controls can prevent tampering with ML artifacts and prevent unauthorized copying.
- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate acquired models for unexpected outputs, backdoor behavior, and sensitive information disclosure before deployment. Reject or quarantine models that fail acceptance criteria and revalidate replacements.
- [AML.M0013 - Code Signing](../../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Enforce properly signed model files.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Pin models to approved versions and digests, and verify all model files and bundled components before loading. Obtain expected values from authenticated sources or protected approval records.
- [AML.M0017 - AI Model Distribution Methods](../../../../Mitigations/AML.M0017%20-%20AI%20Model%20Distribution%20Methods.md) — An adversary could repackage the application with a malicious version of the model.
- [AML.M0023 - Maintain an AI Bill of Materials](../../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record model publishers, repositories, versions, available digests, and bundled components. Use these records to trace compromised releases to fine-tuned derivatives and consuming applications and guide investigation, replacement, or rollback.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce a controlled untrusted or modified model through representative acquisition and deployment paths. Verify provenance, scanning, signing, approval, isolation, and rollback.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on model repositories and distribution services delivering compromised models, including affected publishing accounts, model versions, and references. Use this intelligence to identify affected model dependencies, prevent integration of compromised models, and prioritize investigation of systems that have already incorporated them.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010.003)
