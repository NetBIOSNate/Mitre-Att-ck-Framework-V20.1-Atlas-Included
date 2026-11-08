# AML.T0085 - Data from AI Services

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may use their access to victim AI-enabled services to collect proprietary or otherwise sensitive information available to the system. As organizations adopt generative and agentic AI in centralized services for accessing an organization's data they become increasingly valuable targets for adversaries.

Adversaries may prompt a large language model or AI agent to retrieve internal documents from [RAG Databases](AML.T0085.000%20-%20RAG%20Databases/README.md) or obtain records from organizational systems through [AI Agent Tools](AML.T0085.001%20-%20AI%20Agent%20Tools/README.md). They may also elicit protected information from users' [Conversation Context and Memory](AML.T0085.002%20-%20Conversation%20Context%20and%20Memory/README.md) or recover hidden [System Instructions](AML.T0085.003%20-%20System%20Instructions/README.md). The information available to the AI system may exceed what the adversary can access directly, including data belonging to other users or resources accessible through the service's permissions.

Adversaries may request information directly, supply contextual cues, or construct multi-turn interactions that encourage disclosure. Ordinary-looking requests may succeed where authorization, context isolation, or disclosure controls are inadequate, while [LLM Jailbreak]( /techniques/AML.T0054) may allow the adversary to overcome restrictions or model guardrails. Collected information may be returned through an [Exfiltration via AI Inference API](../../15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md) or [Exfiltration via AI User Interface](../../15%20AML.TA0010%20-%20Exfiltration/AML.T0136%20-%20Exfiltration%20via%20AI%20User%20Interface/README.md), or transmitted elsewhere through [Exfiltration via AI Agent Tool Invocation](../../15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md).

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Sub-techniques

- [AML.T0085.001 - AI Agent Tools](AML.T0085.001%20-%20AI%20Agent%20Tools/README.md)
- [AML.T0085.002 - Conversation Context and Memory](AML.T0085.002%20-%20Conversation%20Context%20and%20Memory/README.md)
- [AML.T0085.000 - RAG Databases](AML.T0085.000%20-%20RAG%20Databases/README.md)
- [AML.T0085.003 - System Instructions](AML.T0085.003%20-%20System%20Instructions/README.md)

## Mitigations

- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Train or fine-tune models and agents to resist requests or injected instructions that induce collection or disclosure of sensitive information outside the authorized scope.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Log requests to AI services to detect malicious queries for data.
- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit service identities to data required by approved workflows and authorize who may initiate them. Separate identities with different access requirements and remove obsolete grants to reduce the information an adversary can collect through the agent.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit access to AI-connected data sources to an explicitly delegated subset of the user's permissions to restrict information collection through the agent. Separate user-specific access contexts and expire or revoke delegated access when delegation ends.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Enforce caller-specific authorization on data-access tools, limiting operations and returned resources to delegated permissions. Isolate user and tenant access contexts to prevent collection under another caller's authority.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to collect sensitive data from AI services.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0085)
