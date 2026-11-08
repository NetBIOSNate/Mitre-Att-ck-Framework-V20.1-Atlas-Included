# AML.T0099 - AI Agent Tool Data Poisoning

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may manipulate data in a victim-controlled, trusted, or connected data source that is accessible through an AI agent tool. Poisoned data may be placed in document repositories, databases, source-code repositories, knowledge bases, search indexes, enterprise applications, or third-party data services used by the agent.

The content may be crafted to appear in common tool queries or retrieval operations. It may contain false or misleading information or malicious instructions intended to produce an [LLM Prompt Injection: Indirect](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md) when retrieved.

This technique concerns manipulation of a data source that an agent tool treats as a source of information. When the adversary introduces the content through a victim-controlled public-facing application, the activity may also constitute [Prompt Infiltration via Public-Facing Application](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md). Content retrieved directly from an adversary-controlled website may instead constitute [Drive-by Compromise](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0078%20-%20Drive-by%20Compromise/README.md). A malicious or compromised tool that deliberately alters its own runtime result constitutes [AI Agent Tool Poisoning: Runtime Response](../AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/AML.T0110.002%20-%20Runtime%20Response/README.md).

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect content returned from connected data sources for malicious instructions and deceptive information before adding it to model context. Apply source, relevance, and task-consistency checks, and block resulting actions that violate policy.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0099)
