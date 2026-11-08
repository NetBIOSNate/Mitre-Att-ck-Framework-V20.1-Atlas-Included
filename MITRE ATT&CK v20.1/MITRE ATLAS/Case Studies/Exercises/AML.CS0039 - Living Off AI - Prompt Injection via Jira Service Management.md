# AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers from Cato Networks demonstrated how adversaries can exploit AI-powered systems embedded in enterprise workflows to execute malicious actions with elevated privileges. This is achieved by crafting malicious inputs from external users such as support tickets that are later processed by internal users or automated systems using AI agents. These AI agents, operating with internal context and trust, may interpret and execute the malicious instructions, leading to unauthorized actions such as data exfiltration, privilege escalation, or system manipulation.

**Type**  Exercise

**Target**  Atlassian MCP, Jira Service Management

**Activity period**  2025-06-19

## Procedure steps

### Step S00

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0003 - Search Victim-Owned Websites](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0003%20-%20Search%20Victim-Owned%20Websites/README.md)

The researchers performed reconnaissance to learn about Atlassian's Model Context Protocol (MCP) server and its integration into the Jira Service Management (JSM) platform. Atlassian offers an MCP server, which embeds AI into enterprise workflows. Their MCP enables a range of AI-driven actions, such as ticket summarization, auto-replies, classification, and smart recommendations across JSM and Confluence. It allows support engineers and internal users to interact with AI directly from their native interfaces.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0002 - Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/README.md) / [AML.T0095 - Search Open Websites/Domains](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0095%20-%20Search%20Open%20Websites%20-%20Domains/README.md)

The researchers used a search query, "site:atlassian.net/servicedesk inurl:portal",  to reveal organizations using Atlassian service portals as potential targets.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted a malicious prompt that requests data from all other support tickets be posted as a reply to the current ticket.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0093 - Prompt Infiltration via Public-Facing Application](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md)

The researchers created a new service ticket containing the malicious prompt on the public Jira Service Management (JSM) portal of the victim identified during reconnaissance.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

As part of their standard workflow, a support engineer at the victim organization used Claude Sonnet (which can interact with Jira via the Atlassian MCP server) to help them resolve the malicious ticket, causing the injection to be unknowingly executed.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious prompt requested information accessible to the AI agent via Atlassian MCP tools, causing those tools to be invoked via MCP, granting the researchers increased privileges on the victim's JSM instance.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0009 - Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/README.md) / [AML.T0085.001 - AI Agent Tools](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md)

The malicious prompt instructed that all details of other issues be collected. This invoked an Atlassian MCP tool that could access the Jira tickets and collect them.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The malicious prompt instructed that the collected ticket details be posted in a reply to the ticket. This invoked an Atlassian MCP Tool which performed the requested action, exfiltrating the data where it was accessible to the researchers on the JSM portal.

**Next**  End of path

## Attributed to

- [AML.E0016 - Cato Networks](../../Entities/AML.E0016%20-%20Cato%20Networks.md) (Security Evaluation)

## References

- [Cato CTRL Threat Research: PoC Attack Targeting Atlassian's Model Context Protocol (MCP) Introduces New "Living Off AI" Risk](https://www.catonetworks.com/blog/cato-ctrl-poc-attack-targeting-atlassians-mcp/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0039)
