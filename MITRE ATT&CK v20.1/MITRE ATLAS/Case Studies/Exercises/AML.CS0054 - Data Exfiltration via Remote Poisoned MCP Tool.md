# AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers at Invariant Labs demonstrated that AI agents configured with remote Model Context Protocol (MCP) Tools can be vulnerable to model poisoning attacks. They show that an MCP Tool can contain malicious prompts in its docstring description, which is ingested into the AI agent's context, modifying its behavior.

They demonstrate this attack with a proof-of-concept MCP Tool that instructs the agent to perform additional actions before using the tool. The agent is instructed to read files containing credentials from the victim's machine and store their contents in one of the input variables to the tool. When the tool runs, the victim's credentials are exfiltrated to the poisoned MCP server.

**Type**  Exercise

**Target**  Model Context Protocol

**Activity period**  2025-04-01

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted a prompt that instructs an AI agent to discover and read user credentials files and store them in an input parameter of an MCP tool.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0115.002 - AI Agent Tools](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0115%20-%20Publish%20Poisoned%20AI%20Artifacts/AML.T0115.002%20-%20AI%20Agent%20Tools/README.md)

The researchers hosted a poisoned MCP server that contains the malicious instructions hidden in the docstring of one of the provided tools.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.005 - AI Agent Tool](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.005%20-%20AI%20Agent%20Tool/README.md)

The victim configured their AI agent to connect to the adversary-controlled remote MCP server, introducing the poisoned tool definition into the agent's available tool set.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0110.000 - Definition and Instructions](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/AML.T0110.000%20-%20Definition%20and%20Instructions/README.md)

The MCP tool's model-visible docstring contained malicious instructions directing the agent to read credential files, conceal the additional actions from the user, and place the credential contents in an otherwise unnecessary tool parameter.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.002 - Poisoned AI Agent Tool](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.002%20-%20Poisoned%20AI%20Agent%20Tool/README.md)

When the user made a request that represented the poisoned tool's functionality, the agent invoked the poisoned MCP tool and acted on the malicious instructions contained in its definition.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

The agent ingested and followed malicious instructions supplied through the remote tool's model-visible definition rather than directly through an adversary-authored user message.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The prompt invoked an agent tool capable of reading files from the victim's filesystem.

**Next**  [S07](#step-s07), [S08](#step-s08)

### Step S07

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0055 - Unsecured Credentials](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0055%20-%20Unsecured%20Credentials/README.md)

The prompt instructed the AI agent to read the user's SSH keys at `~/.ssh/id_rsa`.

**Next**  [S09](#step-s09)

### Step S08

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0098 - AI Agent Tool Credential Harvesting](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0098%20-%20AI%20Agent%20Tool%20Credential%20Harvesting/README.md)

The prompt instructed the AI agent to read `mcp.json`, which often contains credentials for other MCP servers.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The prompt instructed the AI agent to store the credentials files in an extraneous MCP tool parameter to exfiltrate them via the MCP connection.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The user's private data was exposed to remote MCP server.

**Next**  End of path

## Attributed to

- [AML.E0023 - Snyk](../../Entities/AML.E0023%20-%20Snyk.md) (Security Evaluation)

## References

- [MCP Security Notification: Tool Poisoning Attacks](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0054)
