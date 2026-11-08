# AML.T0011.000 - Unsafe AI Artifacts

[MITRE ATLAS](../../../../README.md) / [AML.TA0005 - Execution](../../README.md) / [AML.T0011 - User Execution](../README.md)

Adversaries may develop new AI artifacts or manipulate existing AI artifacts that have a deleterious effect when loaded, executed, interpreted, or used for inference by a victim. The unsafe artifacts may continue to work as expected from the victim's perspective.

Unsafe AI artifacts may include serialized models, model packages, and bundled components such as prompt or chat templates, tokenizer metadata, configuration, pre-processing logic, post-processing logic, or other executable or behavior-shaping metadata.

An unsafe artifact may exploit deserialization or another software vulnerability to execute code on the host. However, exploitation of a software vulnerability is not required. An artifact may instead use functionality intentionally supported by an AI runtime to alter model context, model outputs, safety behavior, or agent actions.

Adversaries may introduce unsafe artifacts through a [Supply Chain Compromise](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/README.md). Execution may occur when a user loads the artifact, starts an inference runtime, submits an inference request, or otherwise causes the artifact's bundled logic to be processed.

**Tactics**  [AML.TA0005 - Execution](../../README.md)

**Platforms**  [Predictive AI](../../../../Platforms/Predictive%20AI.md), [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0027 - Organization Confusion on Hugging Face](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s07)
- [AML.CS0031 - Malicious Models on Hugging Face](../../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md) · [S04](../../../../Case%20Studies/Incidents/AML.CS0031%20-%20Malicious%20Models%20on%20Hugging%20Face.md#step-s04)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s06)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s06)

## Mitigations

- [AML.M0011 - Restrict Library Loading](../../../../Mitigations/AML.M0011%20-%20Restrict%20Library%20Loading.md) — Restrict library loading by ML artifacts.
- [AML.M0013 - Code Signing](../../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Prevent execution of ML artifacts that are not properly signed.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify artifacts against protected approval records before deserialization, loading, or inference. Reject unauthorized changes before executable components are processed.
- [AML.M0016 - Vulnerability Scanning](../../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Vulnerability scanning can help identify malicious AI artifacts, such as models or data, and prevent user execution.
- [AML.M0018 - User Training](../../../../Mitigations/AML.M0018%20-%20User%20Training.md) — Train users to identify attempts of manipulation to prevent them from running unsafe code which when executed could develop unsafe artifacts. These artifacts may have a detrimental effect on the system.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0011.000)
