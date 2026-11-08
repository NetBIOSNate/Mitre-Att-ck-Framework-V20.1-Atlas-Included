# AML.T0051.001 - Indirect

[MITRE ATLAS](../../../../README.md) / [AML.TA0005 - Execution](../../README.md) / [AML.T0051 - LLM Prompt Injection](../README.md)

An adversary may inject prompts indirectly via a separate data channel that the LLM or AI agent ingests, such as text or multimedia pulled from documents, emails, databases or websites. These instructions originate from adversary-controlled content rather than the legitimate user, and are frequently hidden or obfuscated (See [LLM Prompt Obfuscation](../../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)) from the user, for example as invisible text.

Adversaries may use this to hijack an agent or LLM in order to gain a foothold in the target system or to act against an unwitting user of that system, inheriting whatever privileges the AI system holds. Adversaries may also stage the lure that causes the content to be reached (See [AI Agent Clickbait](../../AML.T0100%20-%20AI%20Agent%20Clickbait/README.md)), or use the resulting foothold to establish persistence (See [AI Agent Context Poisoning](../../../07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/README.md)).

Indirect prompt injections have been observed in the wild, with potential impact ranging from harmless pranks, to search engine optimization manipulation, data exfiltration, and destructive actions. [google-prompt-injections-web](https://blog.google/security/prompt-injections-web/)

**Tactics**  [AML.TA0005 - Execution](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0020 - Indirect Prompt Injection Threats: Bing Chat Data Pirate](../../../../Case%20Studies/Exercises/AML.CS0020%20-%20Indirect%20Prompt%20Injection%20Threats%20-%20Bing%20Chat%20Data%20Pirate.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0020%20-%20Indirect%20Prompt%20Injection%20Threats%20-%20Bing%20Chat%20Data%20Pirate.md#step-s02)
- [AML.CS0021 - ChatGPT Conversation Exfiltration](../../../../Case%20Studies/Exercises/AML.CS0021%20-%20ChatGPT%20Conversation%20Exfiltration.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0021%20-%20ChatGPT%20Conversation%20Exfiltration.md#step-s03)
- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S10](../../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s10)
- [AML.CS0029 - Google Bard Conversation Exfiltration](../../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md#step-s04)
- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md#step-s05)
- [AML.CS0038 - Planting Instructions for Delayed Automatic AI Agent Tool Invocation](../../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md#step-s02)
- [AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management](../../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md#step-s04)
- [AML.CS0040 - Hacking ChatGPT's Memories with Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md#step-s03)
- [AML.CS0045 - Data Exfiltration via an MCP Server used by Cursor](../../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md#step-s05)
- [AML.CS0046 - Data Destruction via Indirect Prompt Injection Targeting Claude Computer-Use](../../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md#step-s02)
- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s03)
- [AML.CS0049 - Supply Chain Compromise via Poisoned ClawdBot Skill](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md) · [S08](../../../../Case%20Studies/Exercises/AML.CS0049%20-%20Supply%20Chain%20Compromise%20via%20Poisoned%20ClawdBot%20Skill.md#step-s08)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S10](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s10)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s05)
- [AML.CS0055 - AI ClickFix: Hijacking Computer-Use Agents Using ClickFix](../../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md#step-s05)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s04)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s04)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s05)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S15](../../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s15)

## Mitigations

- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.M0033 - Input and Output Validation for AI Agent Components](../../../../Mitigations/AML.M0033%20-%20Input%20and%20Output%20Validation%20for%20AI%20Agent%20Components.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Place controlled malicious instructions in external or retrieved content processed by the system. Improve content trust boundaries, retrieval controls, instruction isolation, and restrictions on resulting actions.

## References

- [AI threats in the wild: The current state of prompt injections on the web](https://blog.google/security/prompt-injections-web/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0051.001)
