# AML.T0118 - Autonomous AI Agent Communication

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Autonomous AI agents may exchange operational information with other AI agents, sub-agents, or independent agent runs. Exchanged information may include discoveries, objectives, tasking, capabilities, credentials, constraints, operating rules, task state, targeting information, instructions, or results. Communication enables autonomous AI agents to coordinate activities, share discoveries, delegate work, request assistance, validate results, or revise future actions without requiring a human operator to direct each interaction. 

Autonomous AI agents may independently determine when communication is operationally beneficial, what information to exchange, and how to best utilize exchanged information to accomplish their task. The receiving AI agent may interpret the shared information and use it to continue prior activity, investigate a lead, perform a task, reuse a capability, validate a result, or revise subsequent attack activity.

Communication may occur directly through an agent interface (See [Direct Agent Communication](AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md)) or indirectly via writeable shared resources (See [Communication via Shared Artifacts](AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md)).

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0118.000 - Communication via Shared Artifacts](AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md)
- [AML.T0118.001 - Direct Agent Communication](AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md)

## Mitigations

- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit communication and shared-resource permissions to approved inter-agent workflows. Separate authority across unrelated agents and services and authorize workflow initiators to prevent communication from exercising unrelated service privileges.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated communication and shared-resource access to the user's task and current permissions to restrict unauthorized inter-agent information exchange or coordination. Remove access when delegation ends.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Enforce caller-specific authorization on tools for direct agent communication or shared-artifact exchange. Check each operation against its recipient or target resource and prevent shared tool privileges from expanding the caller's communication or resource access.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Implement effective boundaries and sandboxing between system resources or services and agentic tools to limit undesired communication between agents.
- [AML.M0037 - AI Agent Authority Expansion Controls](../../../Mitigations/AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) — Limit the ability of agents to autonomously acquire new credentials to prevent them from forming unwanted communications channels on external services.
- [AML.M0038 - AI Agent Scope Drift Detection](../../../Mitigations/AML.M0038%20-%20AI%20Agent%20Scope%20Drift%20Detection.md) — Identify when objectives, tasks, capabilities, or instructions received through autonomous agent communication cause an agent's planned or executed actions to deviate from its authorized scope.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0118)
