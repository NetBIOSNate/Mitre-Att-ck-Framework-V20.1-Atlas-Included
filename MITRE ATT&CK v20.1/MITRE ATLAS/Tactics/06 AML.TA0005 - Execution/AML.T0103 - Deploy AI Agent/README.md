# AML.T0103 - Deploy AI Agent

[MITRE ATLAS](../../../README.md) / [AML.TA0005 - Execution](../README.md)

Adversaries may launch AI agents in the victim's environment to execute actions on their behalf. AI agents may have access to a wide range of tools and data sources, as well as permissions to access and interact with other services and systems in the victim's environment. The adversary may leverage these capabilities to carry out their operations.

Adversaries may configure the AI agent by providing an initial system prompt and granting access to tools, effectively defining their goals for the agent to achieve. They may deploy the agent with excessive trust permissions and disable any user interactions to ensure the agent's actions aren't blocked.

Launching an AI agent may provide for some autonomous behavior, allowing for the agent to make decisions and determine how to achieve the adversary's goals. This also represents a loss of control for the adversary.

**Tactics**  [AML.TA0005 - Execution](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0047 - Code to Deploy Destructive AI Agent Discovered in Amazon Q VS Code Extension](../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md#step-s04)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s06)

## Mitigations

- [AML.M0013 - Code Signing](../../../Mitigations/AML.M0013%20-%20Code%20Signing.md) — Allow only trusted signed agent applications to execute in the environment.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0103)
