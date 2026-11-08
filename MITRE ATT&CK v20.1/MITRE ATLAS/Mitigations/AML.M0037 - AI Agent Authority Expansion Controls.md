# AML.M0037 - AI Agent Authority Expansion Controls

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit an AI agent's ability to autonomously acquire additional authorities that expand its effective permissions during execution. The maximum authority available to the agent should be explicitly granted prior to runtime. Additional resources, identities, services, and targets discovered during execution should be treated as outside the authorized boundary unless they are independently validated and added to scope. All authority expansion controls should be implemented outside the AI agent and should not rely solely on system prompts, model alignment, or the agent recognizing that an action is out of scope. These controls do not apply to adversary-controlled AI systems over which the organization has no administrative control.

Authority expansion controls include placing restrictions on the number, scope, duration, and concurrent use of authentication and/or authorization tokens available during execution. Tokens may include API access tokens, OAuth tokens, cloud IAM session credentials, service account tokens, Git tokens, or other short-lived authentication artifacts. When policy limits are reached or exceeded, organizations may revoke access, prevent additional token acquisition, require human approval, or terminate the agent's execution.

Implementations of these controls may be achieved through enforcement mechanisms such as: 

- Policy engines
- Target allowlists
- Protocol and destination restrictions
- Approval gates
- Preventing the agent from using credentials that were not approved for the task
- Monitoring and auditing changes in the agent's effective authority over time

Propagate the original authority constraints to sub-agents and delegated tasks. A delegated agent may receive narrower restrictions but should not expand the parent agent's scope, authority, targets, or permitted actions.

Authority expansion controls should be implemented alongside permissions configurations for AI agents and tools (See [Manage AI Agent Service Access](AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md), [Manage User-Delegated AI Agent Access](AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md), and [Enforce Access Controls for AI Agent Tools](AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md)). Attempted changes in scope should be accompanied with [Human In-the-Loop for AI Agent Actions](AML.M0029%20-%20Human%20In-the-Loop%20for%20AI%20Agent%20Actions.md). Log new resource discovery, denials, exceptions, approvals, and scope changes using [AI Telemetry Logging and Monitoring](AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md).

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0116 - Autonomous Reconnaissance](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — Treat newly discovered resources as outside the authorized boundary to prevent expansion of the agent's permitted interactions without approval.
- [AML.T0117 - Autonomous Attack-Path Adaptation](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md) — Constrain actions that seek new authorities, identities, execution environments, tools, communication paths, or trust relationships.
- [AML.T0118 - Autonomous AI Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md) — Limit the ability of agents to autonomously acquire new credentials to prevent them from forming unwanted communications channels on external services.
- [AML.T0121 - AI Agent Environment Reconstruction](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md) — Limit the ability of agents to autonomously acquire new credentials to prevent them from reconstructing environments on external services.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Propagate the parent agent's authority constraints to sub-agents to prevent executors with a broader set of permitted interactions, or permitted actions, or authorities than the originating agent.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0037)
