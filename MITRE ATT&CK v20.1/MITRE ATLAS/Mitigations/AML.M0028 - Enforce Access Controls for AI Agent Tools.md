# AML.M0028 - Enforce Access Controls for AI Agent Tools

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit AI agent tool access to each caller's authorized, task-required operations and resources, including when tools are shared across agents, users, or tenants. Broader tool or backend privileges must not expand caller access. Enforce controls outside the model, in the tool implementation, MCP server, gateway, or underlying service.

Enforce access controls outside the model: in the tool implementation, MCP server, access gateway, or underlying service. Controls should include:

- Caller Authentication: Authenticate calling agents and derive identity, tenant, and delegation context from trusted authentication mechanisms, not model-generated arguments.
- Request Authorization: Authorize each action on its target resource, separately controlling read, modify, and delete permissions. Deny requests when authorization cannot be established.
- Delegated Access Enforcement: Enforce delegated permissions, trusted task restrictions, and tool policy through downstream calls. Use credentials scoped to each receiving service without expanding caller access.
- Access Isolation: Isolate users' credentials, sessions, and authorization context. Select downstream credentials using verified caller context and prevent shared tool state from exposing another caller's resources.

Tools that may help implement these controls include:

- Open Policy Agent (OPA): Evaluates tool requests against caller identity, operations, resources, and trusted context. Tool services or gateways enforce the resulting least-privilege and caller-specific access decisions. [opa](https://www.openpolicyagent.org/docs)
- Cedar: Provides an authorization policy language and engine for evaluating caller actions on resources in context. Supports role- and attribute-based restrictions on tool operations and resources. [cedar](https://docs.cedarpolicy.com/)

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Authenticate callers and authorize each tool invocation against the requested operation, target resource, and delegated permissions. Enforce checks outside the model and limit backend identity privileges to required operations and resources.
- [AML.T0085 - Data from AI Services](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md) — Enforce caller-specific authorization on data-access tools, limiting operations and returned resources to delegated permissions. Isolate user and tenant access contexts to prevent collection under another caller's authority.
- [AML.T0085.000 - RAG Databases](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md) — Enforce caller-specific authorization on tools that search or retrieve RAG data. Check access to underlying documents and records before returning results to prevent unauthorized information collection.
- [AML.T0085.001 - AI Agent Tools](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md) — Enforce caller-specific authorization on tools that read files, search records, query applications, or retrieve other data. Preserve user and tenant restrictions when selecting downstream credentials and accessing backend systems to prevent broader tool privileges from expanding access.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Authorize outbound tool operations against permitted actions, resources, and destinations. Limit sending, uploading, publishing, and writing to recipients and locations required for the authorized task to restrict exfiltration through tools.
- [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Separately authorize deletion, overwrite, and other destructive tool operations against specific target resources. Withhold destructive permissions from callers and tool execution identities that do not require them.
- [AML.T0118 - Autonomous AI Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md) — Enforce caller-specific authorization on tools for direct agent communication or shared-artifact exchange. Check each operation against its recipient or target resource and prevent shared tool privileges from expanding the caller's communication or resource access.
- [AML.T0118.000 - Communication via Shared Artifacts](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md) — Authenticate callers and authorize shared-artifact reads, creation, and modification against task-permitted repositories, storage locations, records, queues, and operations. Preserve restrictions through downstream services to prevent unauthorized information exchange through shared artifacts.
- [AML.T0118.001 - Direct Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md) — Authenticate calling agents and authorize tool-mediated messages, task submissions, and result retrieval against permitted recipients, operations, and workflows. Enforce checks at the receiving interface so that permission to contact an agent does not grant unrestricted use of its capabilities.
- [AML.T0121 - AI Agent Environment Reconstruction](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md) — Authorize tool requests to provision execution environments, recreate supporting resources, and retrieve stored operational state against task-permitted operations and resources. Preserve restrictions through downstream services to prevent broader tool privileges from enabling unauthorized environment reconstruction.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Enforce caller-specific authorization on tools that create sub-agents, assign work, and allocate resources. Check each operation against permitted executors, workflows, and targets to prevent unauthorized delegation.
- [AML.T0143 - LLM Prompt Propagation](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) — Authorize messaging, publishing, repository writes, shared-storage updates, and agent communication against task-permitted resources and destinations. Preserve restrictions through downstream services to prevent shared tool privileges from enabling propagation of malicious instructions beyond the caller's authorized scope.

## References

- [MCP Security Best Practices](https://modelcontextprotocol.io/specification/2025-11-25/basic/security_best_practices)
- [Open Policy Agent Documentation](https://www.openpolicyagent.org/docs)
- [Cedar Policy Language Reference Guide](https://docs.cedarpolicy.com/)
- [OWASP LLM06:2025 - Excessive Agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0028)
