# AML.T0069.002 - System Prompt

[MITRE ATLAS](../../../../README.md) / [AML.TA0008 - Discovery](../../README.md) / [AML.T0069 - Discover LLM System Information](../README.md)

Adversaries may discover a large language model's system instructions provided by the AI system builder to learn about the system's capabilities and circumvent its guardrails.

**Tactics**  [AML.TA0008 - Discovery](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s04)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Restrict access to stored system prompts and prompt templates.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Authenticate and monitor access to production models and prompt configuration.
- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Detect and block unauthorized disclosure of system instructions in model responses, including partial or transformed disclosures where detectable.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0069.002)
