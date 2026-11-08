# AML.T0133 - Discover AI Agent Runtime Capabilities

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may interact with an AI agent at runtime to reveal the capabilities available to it, without requiring access to its underlying configuration. Direct interaction with the agent can surface its registered tools and their accepted parameters, the actions it can take, the resources it can reach, and the identity and permission scope it acts under. Capabilities can also be inferred indirectly by issuing varied requests and observing which succeeded, failed, or refused.

AI agents are often interconnected with enterprise resources, tools and databases, or embedded within SaaS platforms and have permissions to act on behalf of users in order to facilitate functionality. Once adversaries identify a functional agent that they have access to, they could map the attack surface within that agent, by testing its functionality, enumerating tools, capabilities, knowledge, and embedded credentials and permissions.

This mapping process often reveals the AI agent's full toolset and configuration details and exposes additional exploitation, as enabled by [AI Agent Tool Invocation](../../06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md). The resulting intelligence facilitates follow-on exploitation, including [Initial Access](../../04%20AML.TA0004%20-%20Initial%20Access/README.md), [Persistence](../../07%20AML.TA0006%20-%20Persistence/README.md), [Privilege Escalation](../../08%20AML.TA0012%20-%20Privilege%20Escalation/README.md), and [Exfiltration](../../15%20AML.TA0010%20-%20Exfiltration/README.md).

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Feasible

## Mitigations

- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Interactive agentic decoys can present a plausible but fake toolset and capabilities. When an adversary enumerates the agent's capabilities at runtime, the honeypot can capture which tools and privileges they probe for and how they attempt to exploit it, while planted decoy credentials can also be used as canary tokens.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0133)
