# AML.T0084 - Discover AI Agent Configuration

[MITRE ATLAS](../../../README.md) / [AML.TA0008 - Discovery](../README.md)

Adversaries may attempt to discover configuration information for AI agents present on the victim's system. Agent configurations can include tools or services they have access to.

Adversaries may directly access agent configuring dashboards or configuration files. They may also obtain configuration details by prompting the agent with questions such as "What tools do you have access to?"

Adversaries can use the information they discover about AI agents to help with targeting.

**Tactics**  [AML.TA0008 - Discovery](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Sub-techniques

- [AML.T0084.002 - Activation Triggers](AML.T0084.002%20-%20Activation%20Triggers/README.md)
- [AML.T0084.003 - Call Chains](AML.T0084.003%20-%20Call%20Chains/README.md)
- [AML.T0084.000 - Embedded Knowledge](AML.T0084.000%20-%20Embedded%20Knowledge/README.md)
- [AML.T0084.001 - Tool Definitions](AML.T0084.001%20-%20Tool%20Definitions/README.md)

## Case studies

- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s01)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Limit public disclosure of agent tools, services, configuration, and workflows.
- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Honeypots can surface which agent configuration and related assets adversaries hunt for, exposing the reconnaissance that precedes agent-targeted attacks, and acting as both canary tokens and decoy.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0084)
