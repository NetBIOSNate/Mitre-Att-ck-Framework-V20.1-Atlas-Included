# AML.T0069.000 - Special Character Sets

[MITRE ATLAS](../../../../README.md) / [AML.TA0008 - Discovery](../../README.md) / [AML.T0069 - Discover LLM System Information](../README.md)

Adversaries may discover delimiters and special characters sets used by the large language model. For example, delimiters used in retrieval augmented generation applications to differentiate between context and user prompts. These can later be exploited to confuse or manipulate the large language model into misbehaving.

**Tactics**  [AML.TA0008 - Discovery](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s02)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s02)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict access to stored prompt templates and configurations containing internal delimiters.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Authenticate and monitor access to production models and prompt configuration.
- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Detect and restrict responses that expose nonpublic prompt delimiters or internal formatting conventions designated as sensitive.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0069.000)
