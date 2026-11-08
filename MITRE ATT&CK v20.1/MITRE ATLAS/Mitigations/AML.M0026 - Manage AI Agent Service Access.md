# AML.M0026 - Manage AI Agent Service Access

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit service AI agents--agents using independently assigned service or workload permissions--to explicitly authorized workflows. Agents may serve multiple users or act on requests, events, or schedules. Examples include service desk agents fulfilling support requests, operations agents restarting services after monitoring alerts, and reporting agents reading organizational data and publishing scheduled summaries. Apply least privilege to identities, roles, credentials, tools, and resources; permission to invoke an agent must not confer all its authority.

Controls should include:

- Dedicated Agent Identity: Use identifiable service or workload identities scoped to agent functions. Avoid unrestricted administrator accounts and broadly privileged identities shared across unrelated workflows.
- Scoped Roles and Permissions: Use role-based or attribute-based controls to limit workflows to required operations and resources. Separate routine access from permission changes, credential management, security configuration, and deletion.
- Workflow Initiation Authorization: Use trusted identity and authorization context to verify that requesters or triggers may initiate the specific workflow and affect its target resources.
- Privilege Separation: Separate materially different workflows through distinct roles, credentials, or execution contexts. Prevent cross-workflow reuse of credentials or authorization state without explicit authorization.
- Service Access Lifecycle Management: Limit elevated-access duration where supported, review grants as responsibilities change, and revoke unnecessary credentials or roles. Prevent unauthorized users and the agent itself from modifying permission configurations.

An agent may perform operations unavailable directly to its requester, such as fulfilling an approved administrative request, but the requester must be authorized to initiate that workflow. Limit execution authority to the operations and resources needed to fulfill it.

Use [Enforce Access Controls for AI Agent Tools](AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) to enforce these restrictions when tools execute requests, and [AI Agent Authority Expansion Controls](AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) to govern attempts to obtain additional authority during execution. Record the initiating user, application, service, event, or schedule, agent execution identity, authorization decision, and resulting activity through [AI Telemetry Logging and Monitoring](AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md).

Tools that may help implement these controls include:

- Microsoft Entra ID: Provides service principals, managed identities, and application permissions for workloads. Workload identity federation supports authentication without stored application secrets where supported; Entra Agent ID provides agent-specific identities with directly assigned access. [entra-workload-identities](https://learn.microsoft.com/en-us/entra/workload-id/workload-identities-overview) [entra-agent-identities](https://learn.microsoft.com/en-us/entra/agent-id/)
- Amazon Web Services IAM: Provides workload roles and temporary credentials scoped to required actions, resources, and conditions. IAM Access Analyzer supports permission review, policy validation, and policy generation from observed access. [aws-iam-best-practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Assign dedicated service identities with tool and resource permissions limited to approved workflows. Authorize workflow initiators and separate roles with materially different privileges to prevent requests from exercising unrelated agent capabilities.
- [AML.T0082 - RAG Credential Harvesting](../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0082%20-%20RAG%20Credential%20Harvesting/README.md) — Limit retrieval identities to repositories, collections, and documents required by approved workflows, and separate roles across user groups or tenants. These restrictions reduce the sources from which an adversary can retrieve credentials through the agent.
- [AML.T0085 - Data from AI Services](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md) — Limit service identities to data required by approved workflows and authorize who may initiate them. Separate identities with different access requirements and remove obsolete grants to reduce the information an adversary can collect through the agent.
- [AML.T0085.000 - RAG Databases](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md) — Limit retrieval identities to repositories, collections, and documents required by approved workflows, and separate roles across user groups or tenants. These restrictions reduce the information an adversary can retrieve through the agent.
- [AML.T0085.001 - AI Agent Tools](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md) — Limit service roles and credentials to data sources and records required by approved workflows. Separate access across unrelated workflows or tenants and authorize retrieval initiators to prevent requests from exercising unrelated data-access privileges.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Withhold sending, uploading, and publishing permissions unless required by an approved workflow. Limit necessary outbound permissions to workflow-specific roles and destinations, where supported, to restrict exfiltration through the agent.
- [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Separate deletion, overwrite, and other destructive permissions from routine service access. Limit them to required workflows and target resources, and authorize workflow initiators so that access to the agent does not confer destructive privileges.
- [AML.T0118 - Autonomous AI Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md) — Limit communication and shared-resource permissions to approved inter-agent workflows. Separate authority across unrelated agents and services and authorize workflow initiators to prevent communication from exercising unrelated service privileges.
- [AML.T0118.000 - Communication via Shared Artifacts](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md) — Limit service identities to shared resources required by approved workflows. Separate identities and resource permissions across unrelated workflows or agent runs, and avoid shared credentials to restrict unauthorized information exchange through shared artifacts.
- [AML.T0118.001 - Direct Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md) — Assign distinct service identities and narrowly scoped permissions to agent-to-agent and orchestrator interfaces. Authorize which agents or services may send messages, submit tasks, or retrieve results to restrict unauthorized inter-agent communication and task initiation.
- [AML.T0121 - AI Agent Environment Reconstruction](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md) — Limit service permissions to provision execution environments, recreate supporting resources, and retrieve stored operational state to approved workflows. Separate identities and resource permissions across unrelated workflows or agent runs to restrict unauthorized environment reconstruction.
- [AML.T0143 - LLM Prompt Propagation](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0143%20-%20LLM%20Prompt%20Propagation/README.md) — Limit messaging, publishing, and shared-resource write permissions to approved workflows and destinations. Separate distribution capabilities from unrelated service access to restrict where an adversary can propagate malicious instructions through the agent.

## References

- [OWASP LLM06:2025 - Excessive Agency](https://genai.owasp.org/llmrisk/llm062025-excessive-agency/)
- [Microsoft Entra Agent ID](https://learn.microsoft.com/en-us/entra/agent-id/)
- [Microsoft Entra Workflow Identities](https://learn.microsoft.com/en-us/entra/workload-id/workload-identities-overview)
- [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0026)
