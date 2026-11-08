# AML.T0124 - Autonomous Attack Orchestration

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries may use autonomous AI systems as an operational control layer to manage multiple distinct autonomous agents or sub-agents toward a common adversary-defined objective. The orchestrating system may create assignments, select executors, allocate tools or resources, establish dependencies, schedule or synchronize activities, and track progress without a human directing each assignment.

The autonomous system exhibits centralized control over distributed execution including which agent performs which work, when it performs it, and how its output affects other assigned work. The system may aggregate findings and status from participating agents, request independent validation, reconcile conflicting results, prevent or resolve duplicated effort, and determine when an output satisfies a prerequisite for another activity. It may reassign stalled work, increase or reduce resources allocated to a branch, terminate low-value work, or initiate additional research or testing.

Orchestration may use direct agent interfaces (See [Autonomous AI Agent Communication: Direct Agent Communication](../AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.001%20-%20Direct%20Agent%20Communication/README.md)) to transmit assignments, status, and results.

Human involvement does not preclude autonomous attack orchestration. A human operator may define campaign objectives, select targets, provide infrastructure, establish constraints, or retain approval over consequential transitions.

[Autonomous Attack-Path Adaptation](../AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md) and [Autonomous Attack Orchestration](README.md) may occur together but describe different control functions. Attack-path adaptation captures how evidence changes the selected path. Attack orchestration captures how work is allocated, coordinated, validated, and redirected across agents.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md#step-s01)

## Mitigations

- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Enforce caller-specific authorization on tools that create sub-agents, assign work, and allocate resources. Check each operation against permitted executors, workflows, and targets to prevent unauthorized delegation.
- [AML.M0029 - Human In-the-Loop for AI Agent Actions](../../../Mitigations/AML.M0029%20-%20Human%20In-the-Loop%20for%20AI%20Agent%20Actions.md) — Requiring authorized human approval for sub-agent creation, work assignments, and resource allocation can prevent unauthorized delegation and expansion of an orchestrated workflow.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Isolate agent identities, messaging, state, and execution environments. Restrict cross-agent assignment and coordination to explicitly authorized communication paths.
- [AML.M0036 - Limit AI Workload Resource Consumption](../../../Mitigations/AML.M0036%20-%20Limit%20AI%20Workload%20Resource%20Consumption.md) — Limit concurrent agents, parallel assignments, delegation depth, runtime, and aggregate resource consumption to constrain the scale and duration of orchestrated workflows.
- [AML.M0037 - AI Agent Authority Expansion Controls](../../../Mitigations/AML.M0037%20-%20AI%20Agent%20Authority%20Expansion%20Controls.md) — Propagate the parent agent's authority constraints to sub-agents to prevent executors with a broader set of permitted interactions, or permitted actions, or authorities than the originating agent.
- [AML.M0038 - AI Agent Scope Drift Detection](../../../Mitigations/AML.M0038%20-%20AI%20Agent%20Scope%20Drift%20Detection.md) — Identify changes in task hierarchy, assignments, resource allocation, or newly initiated activities that may indicate an orchestrating agent is drifting from its authorized objective.
- [AML.M0042 - Threat Intelligence Program](../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on autonomously orchestrated campaigns, including infrastructure, task allocation, and coordination among agents. Use this intelligence to correlate distributed activity as part of a common operation, identify coordination dependencies, and coordinate containment across affected systems.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0124)
