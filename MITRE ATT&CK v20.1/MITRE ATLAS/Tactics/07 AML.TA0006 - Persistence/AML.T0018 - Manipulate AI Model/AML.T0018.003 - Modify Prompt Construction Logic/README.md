# AML.T0018.003 - Modify Prompt Construction Logic

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0018 - Manipulate AI Model](../README.md)

Adversaries may modify templates, role delimiters, embedded system instructions, tokenizer settings, tool-call formatting, or other artifact-bundled logic that constructs the context sent to an AI model. Model file formats such as GGUF can package this logic alongside model weights in a single distributable artifact. A compatible inference runtime may interpret the modified logic during future inference requests, enabling persistent covert instruction injection, altered instruction precedence, redirected tool use, or manipulated model output without changing model weights.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md), [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s02)

## Mitigations

- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate model artifacts in the intended inference runtime with their bundled prompt-construction configuration. Test for altered instruction precedence or behavior caused by modified templates, role delimiters, or related configuration.
- [AML.M0014 - Verify AI Artifacts](../../../../Mitigations/AML.M0014%20-%20Verify%20AI%20Artifacts.md) — Verify bundled prompt templates, tokenizer configuration, embedded instructions, and tool configurations against protected approval records before interpretation. Reject unauthorized changes.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0018.003)
