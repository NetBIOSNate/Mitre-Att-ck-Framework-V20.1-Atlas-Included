# AML.M0029 - Human In-the-Loop for AI Agent Actions

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Systems should require the user or another human stakeholder to approve AI agent actions before the agent takes them. The human approver may be technical staff or business unit SMEs depending on the use case. Separate tools, such as dedicated audit agents, may assist human approval, but final adjudication should be conducted by a human decision-maker. 

The security benefits from Human In-the-Loop policies may be at odds with operational overhead costs of additional approvals. To ease this, Human In-the-Loop policies should follow the degree of consequence of the task at hand. Minor, repetitive tasks performed by agents accessing basic tools may only require minimal human oversight, while agents employed in systems with significant consequences may necessitate approval from multiple stakeholders diversified across multiple organizations.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Requiring user confirmation of AI agent tool invocations can prevent the automatic execution of tools by an adversary.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Requiring user confirmation of AI agent tool invocations can prevent the automatic execution of tools by an adversary.
- [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Requiring user confirmation of AI agent tool invocations can prevent the automatic execution of tools by an adversary.
- [AML.T0124 - Autonomous Attack Orchestration](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0124%20-%20Autonomous%20Attack%20Orchestration/README.md) — Requiring authorized human approval for sub-agent creation, work assignments, and resource allocation can prevent unauthorized delegation and expansion of an orchestrated workflow.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0029)
