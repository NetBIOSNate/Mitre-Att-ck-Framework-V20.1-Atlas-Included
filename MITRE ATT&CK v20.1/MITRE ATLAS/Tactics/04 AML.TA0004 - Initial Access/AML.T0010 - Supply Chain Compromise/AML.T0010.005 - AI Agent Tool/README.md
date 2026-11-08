# AML.T0010.005 - AI Agent Tool

[MITRE ATLAS](../../../../README.md) / [AML.TA0004 - Initial Access](../../README.md) / [AML.T0010 - Supply Chain Compromise](../README.md)

Adversaries may target AI agent tools as a means to compromise a victim's AI supply chain. Tools add capabilities to AI agents, allowing them to interact with other services, connect to data sources, access internet resources, run system tools, and execute code. They are an attractive target for adversaries because compromising an AI agent can provide them with broad access and permissions on the victim's system via the agent's other tools.

Poisoned AI agent tools may contain malicious definitions or instructions, hidden executable logic, or deliberately poisoned runtime responses (See [AI Agent Tool Poisoning](../../../07%20AML.TA0006%20-%20Persistence/AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/README.md)). These changes may manipulate the agent's behavior, modify how other tools are invoked, introduce hidden side effects, or provide unauthorized access to data and services. Adversaries have successfully used a poisoned MCP server to exfiltrate private user data  [koi](https://www.koi.ai/blog/postmark-mcp-npm-malicious-backdoor-email-theft).

Agent tools have exploded in popularity, with thousands of MCP servers available publicly  [glama](https://glama.ai/mcp/servers). They are often released on open-source software repositories such as GitHub, indexed on hubs specific to MCP servers  [mcp-hub](https://www.mcphub.ai/) [mcp-server-hub](https://mcpserverhub.com/), and published to package registries such as NPM. AI agents can also be connected to remotely-hosted tools  [remote-mcp](https://mcpservers.org/remote-mcp-servers). This creates an environment where malicious tools can proliferate rapidly and safeguards are often not in place.

**Tactics**  [AML.TA0004 - Initial Access](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md#step-s05)
- [AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration](../../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md) · [S04](../../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md#step-s04)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s02)

## Mitigations

- [AML.M0023 - Maintain an AI Bill of Materials](../../../../Mitigations/AML.M0023%20-%20Maintain%20an%20AI%20Bill%20of%20Materials.md) — Record agent tool packages and remote integrations, including providers, available versions, endpoints, and consuming agents. Use these records to identify agents exposed to compromised tools and guide disabling, replacement, or reconnection to a safe version.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Introduce a controlled untrusted agent tool or tool definition. Verify source authorization, integrity, review, permission boundaries, and safe activation.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on compromised AI agent tool dependencies, including affected packages, versions, and remote services. Use this intelligence to identify affected integrations, prevent adoption of compromised tools, and prioritize disabling affected integrations and investigating prior tool activity.

## References

- [Glama](https://glama.ai/mcp/servers)
- [First Malicious MCP in the Wild: The Postmark Backdoor That's Stealing Your Emails](https://www.koi.ai/blog/postmark-mcp-npm-malicious-backdoor-email-theft)
- [MCP Hub](https://www.mcphub.ai/)
- [MCP Server Hub](https://mcpserverhub.com/)
- [Remote MCP Servers](https://mcpservers.org/remote-mcp-servers)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0010.005)
