# AML.T0069.001 - System Instruction Keywords

[MITRE ATLAS](../../../../README.md) / [AML.TA0008 - Discovery](../../README.md) / [AML.T0069 - Discover LLM System Information](../README.md)

Adversaries may discover keywords that have special meaning to the large language model (LLM), such as function names or object names. These can later be exploited to confuse or manipulate the LLM into misbehaving and to make calls to plugins the LLM has access to.

**Tactics**  [AML.TA0008 - Discovery](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s03)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s03)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict access to stored system instructions and tool definitions containing privileged keywords.
- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Restrict disclosure of internal function names, routing keywords, and tool identifiers that the requesting user is not authorized to receive.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0069.001)
