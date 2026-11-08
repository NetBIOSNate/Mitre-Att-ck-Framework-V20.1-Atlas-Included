# AML.T0084.001 - Tool Definitions

[MITRE ATLAS](../../../../README.md) / [AML.TA0008 - Discovery](../../README.md) / [AML.T0084 - Discover AI Agent Configuration](../README.md)

Adversaries may discover the tools the AI agent has access to. By identifying which tools are available, the adversary can understand what actions may be executed through the agent and what additional resources it can reach. This knowledge may reveal access to external data sources such as OneDrive or SharePoint, or expose exfiltration paths like the ability to send emails, helping adversaries identify AI agents that provide the greatest value or opportunity for attack.

**Tactics**  [AML.TA0008 - Discovery](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s05), [S09](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s09)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s01)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Avoid publicly documenting sensitive agent tool definitions and capabilities.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0084.001)
