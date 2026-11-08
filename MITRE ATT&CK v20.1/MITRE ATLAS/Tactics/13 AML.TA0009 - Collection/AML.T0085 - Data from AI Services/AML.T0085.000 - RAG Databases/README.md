# AML.T0085.000 - RAG Databases

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0085 - Data from AI Services](../README.md)

Adversaries may collect sensitive information from data sources that an AI service accesses to retrieve context for its responses. These sources may include document repositories, enterprise search indexes, vector stores, knowledge bases, or other collections used for retrieval-augmented generation (RAG). Retrieved information may expose internal documents, personal information, internal communications, or other records available to the service.

Adversaries may craft requests or inject instructions that cause the service to retrieve and disclose information beyond the user's intended task or authorized scope. Collection may involve targeted requests for particular records, repeated queries that reveal different portions of a source, or requests for quotations, citations, and supporting passages. The AI service may disclose source documents directly or incorporate sensitive details into summaries and other generated responses.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S08](../../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s08)
- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S11](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s11)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s07)

## Mitigations

- [AML.M0022 - Generative AI Model Alignment](../../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Train or fine-tune models to resist requests and injected instructions that induce disclosure of sensitive retrieved information outside the authorized scope.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Log requests to AI services to detect malicious queries for data.
- [AML.M0026 - Manage AI Agent Service Access](../../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit retrieval identities to repositories, collections, and documents required by approved workflows, and separate roles across user groups or tenants. These restrictions reduce the information an adversary can retrieve through the agent.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated retrieval access to repositories, collections, and documents required for the user's task to restrict information collection through the agent. Avoid broadly privileged shared credentials and update effective access when the user's permissions change.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Enforce caller-specific authorization on tools that search or retrieve RAG data. Check access to underlying documents and records before returning results to prevent unauthorized information collection.
- [AML.M0032 - Segmentation of AI Agent Components](../../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to collect sensitive data from RAG databases.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0085.000)
