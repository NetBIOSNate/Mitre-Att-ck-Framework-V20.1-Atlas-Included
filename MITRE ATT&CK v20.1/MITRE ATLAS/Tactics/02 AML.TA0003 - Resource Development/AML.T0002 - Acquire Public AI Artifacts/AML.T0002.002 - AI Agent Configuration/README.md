# AML.T0002.002 - AI Agent Configuration

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0002 - Acquire Public AI Artifacts](../README.md)

Adversaries may acquire publicly accessible AI agent configuration files to understand agent capabilities, gain unauthorized access to tools and data sources, or identify credentials for further attacks. Configuration files define what tools an agent can use, credentials for external services, system prompts, and behavioral settings, making them valuable resources for adversaries targeting AI agent deployments.

Once configuration files are acquired, adversaries may perform [Discover AI Agent Configuration](../../../11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/README.md) to gain additional insights they can use in their operation or [Credentials from AI Agent Configuration](../../../10%20AML.TA0013%20-%20Credential%20Access/AML.T0083%20-%20Credentials%20from%20AI%20Agent%20Configuration/README.md) to harvest secrets.

AI agent configuration files come in multiple forms depending on the platform and agent framework. Agent configuration files adversaries may target include:
- System prompts: Files containing agent instructions, behavioral guidelines, and internal logic.
- Tool configuration: Files defining tools the agent can utilize, including Model Context Protocol (MCP) configs (e.g., `mcp.json`, `claude_desktop_config.json`), IDE-specific configs (e.g., `.claude/settings.json`, `.vscode/tasks.json`), and framework-specific settings that define external tool and data source integrations.
- Skills and workflows: Files defining agent capabilities, behaviors, or workflows. Often a combination of instructions, scripts, and resources.
- Environment and deployment configs: Files that control agent deployment and runtime behavior, often environment variables or framework-specific configs.

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s01)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0002.002)
