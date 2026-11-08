# AML.M0021 - Generative AI Guidelines

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Guidelines are instructions, policies, and behavioral constraints provided to a generative AI model to direct it toward desired outputs and away from unsafe, unreliable, or policy-violating behavior. Guidelines can help reduce risks related to organization policy violations, brand damage, private data leakage, false or unsupported information, unsafe advice, and misuse of tools or external content.

Guidelines can be implemented as system prompts, prompt templates, policy text appended to user prompts, or task-specific instructions included during prompt construction. They can define the system's goals, role, tone, allowed and disallowed behavior, domain boundaries, citation requirements, data-handling expectations, escalation criteria, and safety or security rules.

Common prompt elements include:
- Instructions to cite sources or identify when an answer is not supported by available context.
- Instructions to treat external, retrieved, or user-provided content as untrusted data rather than authoritative sources.
- Instructions to avoid revealing system prompts, hidden policies, credentials, private data, or other sensitive information.
- Instructions to stay within the application's approved domain and refuse requests outside that scope.
- Instructions to follow organization-specific policies, brand requirements, and regulated-domain restrictions.
- Instructions to request human approval before proceeding with potentially unsafe, privileged, irreversible, or externally visible actions when untrusted content is in context (See [Human In-the-Loop for AI Agent Actions](AML.M0029%20-%20Human%20In-the-Loop%20for%20AI%20Agent%20Actions.md)).

Guidelines should be tested, red-teamed, and updated as observed failures, prompt injection techniques, policy requirements, and application capabilities evolve. Guidelines are most effective when paired with [Generative AI Guardrails](AML.M0020%20-%20Generative%20AI%20Guardrails.md) that validate inputs, outputs, retrieved context, and tool use.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  AI Model Engineering, AI Model Evaluation, Deployment

## Techniques mitigated

- [AML.T0051 - LLM Prompt Injection](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.T0054 - LLM Jailbreak](../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0054%20-%20LLM%20Jailbreak/README.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.T0061 - LLM Prompt Self-Replication](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0061%20-%20LLM%20Prompt%20Self-Replication/README.md) — Guidelines can help instruct the model to produce more secure output, preventing the model from generating self-replicating outputs.
- [AML.T0062 - Discover LLM Hallucinations](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0062%20-%20Discover%20LLM%20Hallucinations/README.md) — Guidelines can instruct the model to avoid producing hallucinated content.
- [AML.T0085.002 - Conversation Context and Memory](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.002%20-%20Conversation%20Context%20and%20Memory/README.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.T0085.003 - System Instructions](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.003%20-%20System%20Instructions/README.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.T0100 - AI Agent Clickbait](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0100%20-%20AI%20Agent%20Clickbait/README.md) — Instruct agents to treat webpage instructions as untrusted and request approval for consequential actions.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0021)
