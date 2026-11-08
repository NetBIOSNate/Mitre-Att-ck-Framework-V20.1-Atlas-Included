# AML.T0095.000 - Code Repositories

[MITRE ATLAS](../../../../README.md) / [AML.TA0002 - Reconnaissance](../../README.md) / [AML.T0095 - Search Open Websites/Domains](../README.md)

Adversaries may search public code repositories for information about a victim or victim system that can be used during targeting. Victims may store code or artifacts related to their AI systems in repositories on various third-party websites such as GitHub, GitLab, SourceForge, and BitBucket. Adversaries may search code repositories of common AI tools, frameworks, models, or agentic systems that are used--but not owned--by the victim.

Public code repositories can often be a source of various information about victims, such as commonly used AI frameworks, libraries, models, datasets, agents, and agent tools, as well as the names of employees. Adversaries may also identify more sensitive data, including accidentally leaked credentials or API keys (ex: [Credentials from AI Agent Configuration](../../../10%20AML.TA0013%20-%20Credential%20Access/AML.T0083%20-%20Credentials%20from%20AI%20Agent%20Configuration/README.md)). Information from these sources may reveal opportunities for other forms of [Reconnaissance](../../README.md) (ex: [Gather RAG-Indexed Targets](../../AML.T0064%20-%20Gather%20RAG-Indexed%20Targets/README.md)), establishing operational resources (ex: [Acquire Public AI Artifacts](../../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0002%20-%20Acquire%20Public%20AI%20Artifacts/README.md)), [Discovery](../../../11%20AML.TA0008%20-%20Discovery/README.md) (ex: [Discover AI Agent Configuration](../../../11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/README.md)) and/or [Initial Access](../../../04%20AML.TA0004%20-%20Initial%20Access/README.md) (ex: [Valid Accounts](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md) or [Phishing](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md)).

**Tactics**  [AML.TA0002 - Reconnaissance](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1593.003](../../../../../Enterprise/Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/T1593.003%20-%20Code%20Repositories/README.md) · [MITRE ATT&CK T1593.003](https://attack.mitre.org/techniques/T1593/003/)

## Case studies

- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s00)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s00)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S13](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s13)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s02)

## Mitigations

- [AML.M0039 - AI Honeypots](../../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Decoy assets, such as honeypots, can act as a first contact for adversarial activity and reveal discovery channels that attackers are using to find web AI assets for targeting.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0095.000)
