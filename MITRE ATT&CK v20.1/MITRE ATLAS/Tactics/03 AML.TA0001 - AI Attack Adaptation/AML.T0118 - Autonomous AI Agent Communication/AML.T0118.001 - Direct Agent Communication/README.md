# AML.T0118.001 - Direct Agent Communication

[MITRE ATLAS](../../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../../README.md) / [AML.T0118 - Autonomous AI Agent Communication](../README.md)

Autonomous AI agents may communicate directly through agent-to-agent, sub-agent, or orchestrator interfaces. An agent may provide another agent with operational context, discoveries, objectives, tasking, capabilities, credentials, or constraints, and may receive status, findings, or completed work in response.

Direct communication may include delegation when the sending agent formulates or selects an objective or subtask and the recipient retains meaningful discretion over how to perform it. Direct exchanges may also report discoveries, request independent validation, synchronize activity, transfer capabilities, or return findings without delegating a new task.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S03](../../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s03)

## Mitigations

- [AML.M0026 - Manage AI Agent Service Access](../../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Assign distinct service identities and narrowly scoped permissions to agent-to-agent and orchestrator interfaces. Authorize which agents or services may send messages, submit tasks, or retrieve results to restrict unauthorized inter-agent communication and task initiation.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated access to agent-to-agent and orchestrator interfaces to the user's task, with recipient and operation restrictions where supported. Permission to contact another agent must not imply permission to exercise all of its capabilities.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Authenticate calling agents and authorize tool-mediated messages, task submissions, and result retrieval against permitted recipients, operations, and workflows. Enforce checks at the receiving interface so that permission to contact an agent does not grant unrestricted use of its capabilities.
- [AML.M0032 - Segmentation of AI Agent Components](../../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Implement effective boundaries and sandboxing between system resources or services and agentic tools to limit undesired communication between agents.
- [AML.M0038 - AI Agent Scope Drift Detection](../../../../Mitigations/AML.M0038%20-%20AI%20Agent%20Scope%20Drift%20Detection.md) — Identify when objectives, tasks, capabilities, instructions, or delegated work received through direct agent-to-agent communication cause an agent's behavior to diverge from its authorized scope.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0118.001)
