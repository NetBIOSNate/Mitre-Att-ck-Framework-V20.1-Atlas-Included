# AML.T0093 - Prompt Infiltration via Public-Facing Application

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

An adversary may introduce malicious prompts into the victim's system via a public-facing application with the intention of it being ingested by an AI at some point in the future and ultimately having a downstream effect. This may occur when a data source is indexed by a retrieval augmented generation (RAG) system, when a rule triggers an action by an AI agent, or when a user utilizes a large language model (LLM) to interact with the malicious content. The malicious prompts may persist on the victim system for an extended period and could affect multiple users and various AI tools within the victim organization.

Any public-facing application that accepts text input could be a target. This includes email, shared document systems like OneDrive or Google Drive, and service desks or ticketing systems like Jira. This also includes OCR-mediated infiltration where malicious instructions are embedded in images, screenshots, and invoices that are ingested into the system.

Adversaries may perform [Reconnaissance](../../01%20AML.TA0002%20-%20Reconnaissance/README.md) to identify public facing applications that are likely monitored by an AI agent or are likely to be indexed by a RAG. They may perform [Discover AI Agent Configuration](../../11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/README.md) to refine their targeting.

**Tactics**  [AML.TA0004 - Initial Access](../../04%20AML.TA0004%20-%20Initial%20Access/README.md), [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0016 - Achieving Code Execution in MathGPT via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md#step-s04)
- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s03)
- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s06)
- [AML.CS0029 - Google Bard Conversation Exfiltration](../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md#step-s03)
- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s02)
- [AML.CS0038 - Planting Instructions for Delayed Automatic AI Agent Tool Invocation](../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md#step-s01)
- [AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md#step-s03)
- [AML.CS0040 - Hacking ChatGPT's Memories with Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md#step-s02), [S05](../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md#step-s05)
- [AML.CS0046 - Data Destruction via Indirect Prompt Injection Targeting Claude Computer-Use](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md#step-s01)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s03)
- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s03)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s03)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s03)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s04)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S14](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s14)

## Mitigations

- [AML.M0039 - AI Honeypots](../../../Mitigations/AML.M0039%20-%20AI%20Honeypots.md) — Since honeypots capture real input, they can provide visibility into attacks and prompt payloads that are target-specific.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0093)
