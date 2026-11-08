# AML.M0038 - AI Agent Scope Drift Detection

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Continuously evaluate whether an AI Agent's planned actions remain consistent with its current authorized objective throughout execution. As autonomous agents interact within a dynamic environment, they may discover or generate intermediate objectives or adapt their strategy based on environment feedback. While limited adaption may be necessary to complete legitimate tasks, substantial deviations from the original objective may indicate unintended behavior, excessive autonomy, or attempts to pursue objectives outside the authorized scope. This mitigation does not apply to adversary-controlled AI systems over which the organization has no administrative control.

Implementation of scope drift detection can vary through runtime policy engines, planning monitors, orchestration frameworks, or additional supervisory AI Agents. Indicators to monitor may include:

- Significant changes in planned objectives or task hierarchy.
- Generation of new long-term goals unrelated to the assigned objective.
- Tool usage inconsistent with the original mission.
- Attempts to access systems or resources outside the authorized scope.
- Repeated adaptation toward objectives requiring progressively broader authority.
- Planning sequences that introduce persistence, privilege escalation, or unrelated lateral movement.

When scope drift is detected, pause execution, restrict tool access, require external human approval, and return the agent to a known authorized plan or terminate the task.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Monitoring and Maintenance

## Techniques mitigated

- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Identify tool-use inconsistent with the assigned task as potential scope-drift indicator.
- [AML.T0116 - Autonomous Reconnaissance](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — Identify when an agent attempts to discover or probe resources in ways no longer consistent with the authorized objective.
- [AML.T0117 - Autonomous Attack-Path Adaptation](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md) — Evaluate whether dynamically generated intermediate actions are within the agent's task scope.
- [AML.T0118 - Autonomous AI Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/README.md) — Identify when objectives, tasks, capabilities, or instructions received through autonomous agent communication cause an agent's planned or executed actions to deviate from its authorized scope.
- [AML.T0118.000 - Communication via Shared Artifacts](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md) — Identify when objectives, tasks, capabilities, instructions, or other operational information received through shared artifacts cause an agent to pursue actions outside its authorized scope.
- [AML.T0118.001 - Direct Agent Communication](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md) — Identify when objectives, tasks, capabilities, instructions, or delegated work received through direct agent-to-agent communication cause an agent's behavior to diverge from its authorized scope.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Identify changes in task hierarchy, assignments, resource allocation, or newly initiated activities that may indicate an orchestrating agent is drifting from its authorized objective.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0038)
