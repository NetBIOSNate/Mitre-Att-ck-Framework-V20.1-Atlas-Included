# AML.S0025 - Hermes Agent

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Hermes Agent](AML.S0025%20-%20Hermes%20Agent.md) is an open source AI agent developed by Nous Research. It connects configurable language models to terminal execution, external tools, messaging channels, persistent memory, and reusable skills. It supports scheduled tasks, delegation to sub-agents, and Model Context Protocol (MCP) integrations, and can create and update skills from prior task experience. [canonical-source](https://github.com/NousResearch/hermes-agent)

**Software type**  Tool

**Software categories**  ai-agent, ai-agent-framework

## Used by

- [AML.CS0071 - Multi-Agent Framework Compromises Taiwanese Government Systems](../../Case%20Studies/Incidents/AML.CS0071%20-%20Multi-Agent%20Framework%20Compromises%20Taiwanese%20Government%20Systems.md) — The operator used a multi-agent framework built on [Hermes Agent](AML.S0025%20-%20Hermes%20Agent.md) and [OpenClaw](AML.S0026%20-%20OpenClaw.md) to coordinate parallel reconnaissance, credential attacks, API testing, and data collection against government systems. [dream-multi-agent-framework](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia)
- [AML.E0038 - knaithe](../../Entities/AML.E0038%20-%20knaithe.md) — [knaithe](../../Entities/AML.E0038%20-%20knaithe.md) configured [Hermes Agent](AML.S0025%20-%20Hermes%20Agent.md) with DeepSeek, Telegram-based control, custom red-teaming skills, and an MCP integration. They used it to autonomously enumerate targets, obtain public exploit code, assess exploitation prerequisites, and attempt attacks. After Langflow exploitation encountered configuration barriers, the agent independently researched alternatives and pivoted to n8n. The observed autonomous attempts did not achieve compromise. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

## Techniques implemented

- [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — In knaithe's configuration, [Hermes Agent](AML.S0025%20-%20Hermes%20Agent.md) used DeepSeek and connected tools to enumerate internet-facing systems through FOFA, research public vulnerabilities and exploit repositories, and assess candidate targets. The agent selected subsequent investigative actions without further operator input recovered in the session. [source-1](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)
- [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md) — After determining that Langflow targets lacked exploitation prerequisites, the DeepSeek-powered [Hermes Agent](AML.S0025%20-%20Hermes%20Agent.md) researched vulnerabilities across ten product families and selected n8n as an alternative. It obtained a public exploit chain, assessed target configurations, and attempted further exploitation. The observed autonomous attempts did not obtain access. [source-1](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

## References

- [Unit 42: Chinese-Speaking Threat Actor Harnesses AI Models for Autonomous Cyberattacks](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)
- [Inside a Multi-Agent AI Framework Used to Compromise Government Entities in Asia](https://www.dreamgroup.com/blog/inside-a-multi-agent-ai-framework-used-to-compromise-government-entities-in-asia)
- [Hermes Agent: canonical implementation source](https://github.com/NousResearch/hermes-agent)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0025)
