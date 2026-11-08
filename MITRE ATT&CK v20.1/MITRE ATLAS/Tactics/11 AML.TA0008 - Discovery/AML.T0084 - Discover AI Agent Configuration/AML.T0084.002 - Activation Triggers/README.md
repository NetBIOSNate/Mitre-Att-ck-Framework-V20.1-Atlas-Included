# AML.T0084.002 - Activation Triggers

[MITRE ATLAS](../../../../README.md) / [AML.TA0008 - Discovery](../../README.md) / [AML.T0084 - Discover AI Agent Configuration](../README.md)

Adversaries may discover keywords or other triggers (such as incoming emails, documents being added, incoming message, or other workflows) that activate an agent and may cause it to run additional actions.

Understanding these triggers can reveal how the AI agent is activated and controlled. This may also expose additional paths for compromise, as an adversary could attempt to trigger the agent from outside its environment and drive it to perform unintended or malicious actions.

**Tactics**  [AML.TA0008 - Discovery](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s04)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s02)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Avoid publicly disclosing agent activation keywords, events, and workflows.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0084.002)
