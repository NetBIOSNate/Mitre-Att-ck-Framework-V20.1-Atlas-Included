# AML.T0085.003 - System Instructions

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0085 - Data from AI Services](../README.md)

Adversaries may collect non-public instructions used to configure the behavior of an AI model or agent. These may include system prompts or application-specific rules governing tasks, tool use, response formatting, and handling of sensitive information.

Adversaries may request that the service reproduce, summarize, or transform its instructions, or use [LLM Prompt Injection](../../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) or [LLM Jailbreak](../../../08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0054%20-%20LLM%20Jailbreak/README.md) to induce disclosure. Collection may reveal complete instructions or selected portions across multiple responses.

Collected instructions may expose proprietary application logic, internal workflows, tool descriptions, or sensitive information embedded in the instructions. This information may support replication of application behavior or help adversaries tailor subsequent attacks.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models for disclosure of confidential system-instruction content using adversarial prompts. Use confirmed disclosures to guide prompt-content changes, model selection, or additional controls before deployment.
- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect model responses for unauthorized reproduction or disclosure of protected system instructions. Block or redact matching content before response.
- [AML.M0021 - Generative AI Guidelines](../../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.M0022 - Generative AI Model Alignment](../../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Train or fine-tune models to resist requests to reproduce, summarize, or transform protected system instructions in ways that disclose their contents.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Probe model and application interfaces for disclosure of system instructions, policies, tool definitions, or hidden context. Remove embedded secrets and improve configuration isolation and output controls.

## References

- [LLM07:2025 System Prompt Leakage](https://genai.owasp.org/llmrisk/llm072025-system-prompt-leakage)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0085.003)
