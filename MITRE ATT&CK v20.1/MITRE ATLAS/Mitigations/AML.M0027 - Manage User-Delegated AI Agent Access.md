# AML.M0027 - Manage User-Delegated AI Agent Access

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit user-delegated AI agents to explicitly authorized tasks and permissions. Apply the principle of least privilege so that the agent receives only the access required for its designated tasks. The user's permissions establish an upper bound; the agent should not automatically receive every permission available to that user.

Controls should include:

- Agent Identity and User Association: Bind an identifiable agent or application identity to the authorizing user. Distinguish both identities in access decisions and activity records.
- Scoped Delegation: Limit operations, resources, and services to the required subset of user permissions, using read-only access where sufficient. Derive scope from trusted configuration or authorization mechanisms, not the agent's interpretation of requests.
- Credential and Session Management: Use scoped, short-lived credentials where supported. Keep credentials outside model-visible context, isolate them across users' agents and sessions, and avoid broadly privileged shared accounts.
- Access Lifecycle Management: Review delegation when tasks or user permissions change, and reflect removed user permissions in effective agent access. Expire or revoke credentials and sessions when delegation ends, the agent is decommissioned, or compromise is suspected.

Enforce delegated permissions through the systems that provide access to tools and resources. Use [Enforce Access Controls for AI Agent Tools](AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) to ensure that tool calls remain within the user's delegation, including when tools invoke downstream services. Use [AI Agent Authority Expansion Controls](AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) to prevent the agent from autonomously obtaining additional authority outside its approved scope.

Tools that may help implement these controls include:

- Microsoft Entra ID: Supports user-delegated permissions, user and administrator consent, and token acquisition on behalf of users. Entra Agent ID provides agent-specific identities with delegated access bounded by granted permissions and the user's authorized access. [entra-permissions-consent](https://learn.microsoft.com/en-us/entra/identity-platform/permissions-consent-overview) [entra-agent-identities](https://learn.microsoft.com/en-us/entra/agent-id/)
- Amazon Bedrock AgentCore Identity: Provides agent workload identities and centralized credential management for AWS and third-party services. User-authorized OAuth integrations support access on behalf of users. [agentcode-identity](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/identity.html)

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Limit delegated tool operations and resource access to the agent's tasks, bounded by the authorizing user's current permissions. Do not automatically grant all access available to the user.
- [AML.T0082 - RAG Credential Harvesting](../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0082%20-%20RAG%20Credential%20Harvesting/README.md) — Limit delegated retrieval access to repositories, collections, and documents required for the user's task to reduce potential credential sources. Avoid broadly privileged shared credentials and update effective access when the user's permissions change.
- [AML.T0085 - Data from AI Services](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md) — Limit access to AI-connected data sources to an explicitly delegated subset of the user's permissions to restrict information collection through the agent. Separate user-specific access contexts and expire or revoke delegated access when delegation ends.
- [AML.T0085.000 - RAG Databases](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md) — Limit delegated retrieval access to repositories, collections, and documents required for the user's task to restrict information collection through the agent. Avoid broadly privileged shared credentials and update effective access when the user's permissions change.
- [AML.T0085.001 - AI Agent Tools](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md) — Limit delegated read, search, and query permissions to resources required for the user's task. Bind access to the authorizing user and separate users' credentials to prevent retrieval under another user's authority.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Withhold delegated sending, uploading, publishing, and other outbound capabilities unless required for the user's task. Limit grants to required destinations and resources where supported to restrict exfiltration through the agent.
- [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Use read-only delegation when modification is unnecessary. Limit deletion and other destructive permissions to explicitly authorized tasks and resources rather than automatically delegating permissions the user possesses.
- [AML.T0118 - Autonomous AI Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md) — Limit delegated communication and shared-resource access to the user's task and current permissions to restrict unauthorized inter-agent information exchange or coordination. Remove access when delegation ends.
- [AML.T0118.000 - Communication via Shared Artifacts](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md) — Limit delegated access to shared repositories, files, databases, queues, and other persistent resources required for the user's task. Scope read and write permissions separately to restrict information exchange through shared artifacts, and expire or revoke access when delegation ends.
- [AML.T0118.001 - Direct Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md) — Limit delegated access to agent-to-agent and orchestrator interfaces to the user's task, with recipient and operation restrictions where supported. Permission to contact another agent must not imply permission to exercise all of its capabilities.
- [AML.T0121 - AI Agent Environment Reconstruction](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md) — Limit delegated permissions to provision execution environments, recreate supporting resources, and retrieve stored operational state to those required for the user's task. Expire or revoke access when delegation ends to restrict unauthorized environment reconstruction.
- [AML.T0143 - LLM Prompt Propagation](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) — Limit delegated messaging, publishing, and shared-resource write permissions to destinations and resources required for the user's task. Withhold unnecessary distribution capabilities to restrict propagation of malicious instructions through the agent.

## References

- [OWASP LLM06:2025 - Excessive Agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/)
- [Microsoft Identity Platform - Permissions and Consent Overview](https://learn.microsoft.com/en-us/entra/identity-platform/permissions-consent-overview)
- [Amazon Bedrock AgentCore Identity](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/identity.html)
- [Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0027)
