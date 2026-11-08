# AML.T0006.003 - Probe AI Agent Trigger Channels

[MITRE ATLAS](../../../../README.md) / [AML.TA0002 - Reconnaissance](../../README.md) / [AML.T0006 - Active Scanning](../README.md)

Adversaries may send crafted inputs to potential public triggers, such as email addresses, webhooks, or messaging channels, to elicit a response that indicates an invocation of agentic activity. The nature of the response and its content can often reveal agent-managed accounts and expose the additional agentic attack surface. Identified triggers can be used to directly attack the agent.

**Tactics**  [AML.TA0002 - Reconnaissance](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md), [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s00)

## Mitigations

- [AML.M0039 - AI Honeypots](../../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — By capturing adversarial fingerprinting behavior, honeypots can help provide early warning of sweeping activity meant to discover exposed AI targets and attack surfaces being explored by adversaries.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0006.003)
