# AML.T0115.002 - AI Agent Tools

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0115 - Publish Poisoned AI Artifacts](../README.md)

Adversaries may create and publish poisoned AI agent tools. Poisoned tools may contain malicious model-visible definitions or instructions, hidden executable behavior, or runtime responses designed to manipulate an AI agent. Tools may be published through source code repositories, package registries, agent tool or skill registries, or adversary-controlled remote services. The tool may be newly created or a modified variant of a legitimate tool and may produce malicious behavior when selected, installed, or invoked by a victim's AI agent.

Adversaries may distribute poisoned tools through open-source version control repositories (e.g. GitHub, GitLab), package registries (e.g. npm), or to repositories specifically designed for sharing tools (e.g. OpenClaw Hub). These registries may be largely unregulated and may contain many poisoned tools  [opensourcemalware](https://opensourcemalware.com/blog/clawdbot-skills-ganked-your-crypto). Tools may also be published as remotely hosted servers  [mcpservers](https://mcpservers.org/remote-mcp-servers).

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md#step-s03)
- [AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration](../../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md#step-s02)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s01)

## Mitigations

- [AML.M0016 - Vulnerability Scanning](../../../../Mitigations/AML.M0016%20-%20Vulnerability%20Scanning.md) — Tool registries scan uploaded tool packages and dependencies for malicious code and vulnerabilities before listing.
- [AML.M0042 - Threat Intelligence Program](../../../../Mitigations/AML.M0042%20-%20Threat%20Intelligence%20Program.md) — Collect, analyze, and share intelligence on published poisoned AI agent tools, including package or service identifiers, versions, distribution locations, and evidence of malicious content or behavior. Use this intelligence to block installation or connection to identified tools, investigate agents that have used them, and support reporting to distribution platforms or service providers for removal.

## References

- [Remote MCP Servers | Awesome MCP Servers](https://mcpservers.org/remote-mcp-servers)
- [ClawdBot Skills Just Ganked Your Crypto | OpenSourceMalware](https://opensourcemalware.com/blog/clawdbot-skills-ganked-your-crypto)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0115.002)
