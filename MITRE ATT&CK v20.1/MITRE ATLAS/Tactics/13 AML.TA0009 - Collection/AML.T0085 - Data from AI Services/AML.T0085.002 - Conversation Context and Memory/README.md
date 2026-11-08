# AML.T0085.002 - Conversation Context and Memory

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0085 - Data from AI Services](../README.md)

Adversaries may collect sensitive information from an AI service's current or stored interactions and memory. This may include user messages, model responses, conversation summaries, and retained user facts and preferences.

Adversaries may induce the service to reveal information available in its current context or retrieve information retained across sessions. Collection may also occur through interfaces that expose conversation histories or memory records. The information may reveal private user activity, organizational information, or details useful for subsequent adversarial operations.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S09](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s09)

## Mitigations

- [AML.M0008 - Validate AI Model](../../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models for disclosure of sensitive conversation or memory content supplied in context, using adversarial requests, controlled test records, and the intended context-handling configuration. Use confirmed disclosures to guide remediation or deployment restrictions.
- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect proposed disclosures of conversation history, summaries, and memory content against the requesting user's authorization and the current task. Block or redact sensitive information before it is returned or transferred to another component.
- [AML.M0021 - Generative AI Guidelines](../../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.M0022 - Generative AI Model Alignment](../../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Train or fine-tune models to resist requests to disclose sensitive conversation content or retained memory outside the authorized scope.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Place synthetic secrets or canary records in representative data sources and attempt extraction through prompts, retrieval, tools, and rendered output. Improve authorization boundaries, filtering, tenant isolation, and exfiltration detection.

## References

- [LLM02:2025 Sensitive Information Disclosure](https://genai.owasp.org/llmrisk/llm022025-sensitive-information-disclosure/)
- [Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations](https://csrc.nist.gov/pubs/ai/100/2/e2025/final)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0085.002)
