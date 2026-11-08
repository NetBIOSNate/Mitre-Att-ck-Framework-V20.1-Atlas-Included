# AML.CS0045 - Data Exfiltration via an MCP Server used by Cursor

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The Backslash Security Research Team demonstrated that a Model Context Protocol (MCP) tool can be used as a vector for an indirect prompt injection attack on Cursor, potentially leading to the execution of malicious shell commands.

The Backslash Security Research Team created a proof-of-concept MCP server capable of scraping webpages. When a user asks Cursor to use the tool to scrape a site containing a malicious prompt, the prompt is injected into Cursor's context. The prompt instructs Cursor to execute a shell command to exfiltrate the victim's AI agent configuration files containing credentials. Cursor does prompt the user before executing the malicious command, potentially mitigating the attack.

**Type**  Exercise

**Target**  Cursor

**Activity period**  2025-06-24

## Procedure steps

### Step S00

[AML.TA0001 - AI Attack Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/README.md) / [AML.T0065 - LLM Prompt Crafting](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0065%20-%20LLM%20Prompt%20Crafting/README.md)

The researchers crafted a malicious prompt containing an instruction to execute the malicious shell command to exfiltrate the victim's AI agent credentials.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The researchers created a malicious web site containing the malicious prompt.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

The malicious prompt was hidden in the title tag of the webpage.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The researchers launched a web server to receive data exfiltrated from the victim.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0078 - Drive-by Compromise](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0078%20-%20Drive-by%20Compromise/README.md)

When a user asked Cursor to use an MCP tool to scrape the malicious website, the contents of the malicious prompt was retrieved and ingested into Cursor's context window.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.001 - Indirect](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md)

When the MCP server scraped the malicious web site, it returned the injected prompt to the MCP client and poisoned the context of the Cursor LLM. Cursor executed the malicious prompt embedded in the website scraped by the MCP tool.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0053 - AI Agent Tool Invocation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)

The prompt injection invoked Cursor's ability to call command line tools via the `run_terminal_cmd` tool.

Cursor prompted the user before executing a shell command, potentially mitigating this attack.

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

When the MCP server scraped the malicious web site, it returned the injected prompt to the MCP client and poisoned the context of the Cursor LLM. The shell command in the malicious prompt was obscured via base64 encoding, making it less clear to the user that something malicious may be executed.

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0083 - Credentials from AI Agent Configuration](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0083%20-%20Credentials%20from%20AI%20Agent%20Configuration/README.md)

The shell command located the `.openapi.apiKey` and `.cursor/mcp.json` credentials files that were part of the Cursor's configuration.

**Next**  [S09](#step-s09)

### Step S09

[AML.TA0010 - Exfiltration](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/README.md) / [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md)

The credentials files were exfiltrated to the researcher's server via a `curl` command invoked by Cursor's `run_terminal_cmd` tool.

**Next**  [S10](#step-s10)

### Step S10

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

A bad actor could use the stolen credentials to cause financial damage and could also steal other sensitive information from the victim user.

**Next**  End of path

## Attributed to

- [AML.E0019 - Backslash Security Research Team](../../Entities/AML.E0019%20-%20Backslash%20Security%20Research%20Team.md) (Security Evaluation)

## References

- [Simulating a Context-Poisoning Vulnerable MCP Server: A POC](https://www.backslash.security/blog/simulating-a-vulnerable-mcp-server-for-context-poisoning)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0045)
