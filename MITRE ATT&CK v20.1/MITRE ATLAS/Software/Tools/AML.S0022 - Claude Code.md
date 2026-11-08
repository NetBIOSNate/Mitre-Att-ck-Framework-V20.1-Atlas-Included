# AML.S0022 - Claude Code

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Claude Code](AML.S0022%20-%20Claude%20Code.md) is Anthropic's agentic coding tool for reading codebases, editing files, executing commands, and automating software-development tasks. It operates through terminal, IDE, desktop, and browser interfaces and can connect to external tools and data sources through Model Context Protocol (MCP) servers. [canonical-source](https://code.claude.com/docs/en/overview)

**Software type**  Tool

**Software categories**  ai-agent

## Used by

- [AML.E0037 - GTG-1002](../../Entities/AML.E0037%20-%20GTG-1002.md) — [GTG-1002](../../Entities/AML.E0037%20-%20GTG-1002.md) integrated [Claude Code](AML.S0022%20-%20Claude%20Code.md) into an intrusion framework connected to reconnaissance, remote command execution, browser automation, code analysis, and vulnerability testing tools through MCP servers. They used it to inspect target infrastructure, develop and validate exploits, harvest and test credentials, move laterally, create persistent access, and exfiltrate data. [anthropic-report](https://www-cdn.anthropic.com/d7dd50dd1185f59be051b307150d877f2b82bd2c.pdf)
- [AML.E0038 - knaithe](../../Entities/AML.E0038%20-%20knaithe.md) — [knaithe](../../Entities/AML.E0038%20-%20knaithe.md) used [Claude Code](AML.S0022%20-%20Claude%20Code.md) for connectivity testing and proxy validation through a third-party proxy service. Recovered session history contained model checks, connectivity tests, and an npm installation request. [unit42](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

## Techniques implemented

- [AML.T0116 - Autonomous Reconnaissance](../../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0116%20-%20Autonomous%20Reconnaissance/README.md) — Within GTG-1002's intrusion framework, [Claude Code](AML.S0022%20-%20Claude%20Code.md) autonomously inspected target systems and infrastructure, identified valuable databases, and reported its findings to human operators.[[source-1]]
- [AML.T0117 - Autonomous Attack-Path Adaptation](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0117%20-%20Autonomous%20Attack-Path%20Adaptation/README.md) — Within GTG-1002's intrusion framework, [Claude Code](AML.S0022%20-%20Claude%20Code.md) selected and revised intermediate attack actions based on observed results, progressing through vulnerability testing, exploitation, and credential-based access while human operators retained critical decisions. [anthropic-report](https://www.anthropic.com/news/disrupting-AI-espionage)
- [AML.T0126 - Automated Collection](../../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0126%20-%20Automated%20Collection/README.md) — Within GTG-1002's intrusion framework, [Claude Code](AML.S0022%20-%20Claude%20Code.md) automated the extraction of private data from compromised systems and categorized the collected information by intelligence value. [anthropic-report](https://www.anthropic.com/news/disrupting-AI-espionage)

## References

- [Anthropic: Disrupting an AI-orchestrated cyber espionage campaign](https://www.anthropic.com/news/disrupting-AI-espionage)
- [Claude Code: canonical implementation source](https://code.claude.com/docs/en/overview)
- [Unit 42: Chinese-Speaking Threat Actor Harnesses AI Models for Autonomous Cyberattacks](https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0022)
