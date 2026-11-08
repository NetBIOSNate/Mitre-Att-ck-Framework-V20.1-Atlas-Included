# AML.E0038 - knaithe

[MITRE ATLAS](../README.md) / [Entities](README.md)

[knaithe](AML.E0038%20-%20knaithe.md), also known as KnYuan, is a Chinese-speaking operator assessed to be based in Zhuhai, China. They combine AI-powered reconnaissance and exploitation attempts with conventional manual attacks and maintain a vulnerability intelligence pipeline that uses DeepSeek to assess exploitability and distributes alerts through Telegram. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

They use a DeepSeek-powered [Hermes Agent](../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) with custom red-teaming skills and integrated reconnaissance tools to investigate targets and adapt exploitation attempts. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

**Entity type**  Individual

## Associated entities

- KnYuan — [[group-profile]]

## Uses

- [AML.S0022 - Claude Code](../Software/Tools/AML.S0022%20-%20Claude%20Code.md) — [knaithe](AML.E0038%20-%20knaithe.md) used [Claude Code](../Software/Tools/AML.S0022%20-%20Claude%20Code.md) for connectivity testing and proxy validation through a third-party proxy service. Recovered session history contained model checks, connectivity tests, and an npm installation request. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)
- [AML.S0025 - Hermes Agent](../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) — [knaithe](AML.E0038%20-%20knaithe.md) configured [Hermes Agent](../Software/Tools/AML.S0025%20-%20Hermes%20Agent.md) with DeepSeek, Telegram-based control, custom red-teaming skills, and an MCP integration. They used it to autonomously enumerate targets, obtain public exploit code, assess exploitation prerequisites, and attempt attacks. After Langflow exploitation encountered configuration barriers, the agent independently researched alternatives and pivoted to n8n. The observed autonomous attempts did not achieve compromise. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)
- [AML.S0031 - FOFA](../Software/Tools/AML.S0031%20-%20FOFA.md) — [knaithe](AML.E0038%20-%20knaithe.md) used [FOFA](../Software/Tools/AML.S0031%20-%20FOFA.md) through scripts and an MCP integration to identify internet-exposed services. Their autonomous agent enumerated Langflow instances, compared deployment counts across alternative product families, and narrowed searches to Chinese n8n instances for version checks and exploitation attempts. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

## Attributed case studies

- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) (Adversarial Operation)

## References

- [Unit 42: Chinese-Speaking Threat Actor Harnesses AI Models for Autonomous Cyberattacks](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

[Official ATLAS record](https://atlas.mitre.org/entities/AML.E0038)
