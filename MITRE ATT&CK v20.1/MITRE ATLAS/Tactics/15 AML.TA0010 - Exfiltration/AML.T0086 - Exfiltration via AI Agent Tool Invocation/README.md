# AML.T0086 - Exfiltration via AI Agent Tool Invocation

[MITRE ATLAS](../../../README.md) / [AML.TA0010 - Exfiltration](../README.md)

AI agent tools capable of performing write operations may be invoked to exfiltrate data to an adversary. Sensitive information can be encoded into the tool's input parameters and transmitted to an adversary-controlled location (such as an inbox, document, or server) as part of a seemingly legitimate action. Variants include sending emails, creating or modifying documents, updating CRM records, or even generating media such as images or videos.

The invoked tool itself may be legitimate but invoked by an adversary via [LLM Prompt Injection](../../06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md), or the tool may be malicious (See [AI Agent Tool Poisoning](../../07%20AML.TA0006%20-%20Persistence/AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/README.md)).

[AI Agent Tool Poisoning](../../07%20AML.TA0006%20-%20Persistence/AML.T0110%20-%20AI%20Agent%20Tool%20Poisoning/README.md) can also be used to manipulate the inputs and destination of a separate legitimate tool, invoked through normal usage by the victim.

**Tactics**  [AML.TA0010 - Exfiltration](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S13](../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s13)
- [AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md#step-s07)
- [AML.CS0045 - Data Exfiltration via an MCP Server used by Cursor](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md#step-s09)
- [AML.CS0053 - Poisoned Postmark MCP Server Email Exfiltration](../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0053%20-%20Poisoned%20Postmark%20MCP%20Server%20Email%20Exfiltration.md#step-s07)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s09)
- [AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md#step-s08)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S19](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s19)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S11](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s11)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s09)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S10](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s10)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect tool arguments, message bodies, uploaded content, and destinations before write operations or external requests. Block unauthorized transfers of sensitive information, including content embedded in URLs or other tool parameters.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Log AI agent tool invocations to detect malicious calls.
- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Withhold sending, uploading, and publishing permissions unless required by an approved workflow. Limit necessary outbound permissions to workflow-specific roles and destinations, where supported, to restrict exfiltration through the agent.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Withhold delegated sending, uploading, publishing, and other outbound capabilities unless required for the user's task. Limit grants to required destinations and resources where supported to restrict exfiltration through the agent.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Authorize outbound tool operations against permitted actions, resources, and destinations. Limit sending, uploading, publishing, and writing to recipients and locations required for the authorized task to restrict exfiltration through tools.
- [AML.M0029 - Human In-the-Loop for AI Agent Actions](../../../Mitigations/AML.M0029%20-%20Human%20In-the-Loop%20for%20AI%20Agent%20Actions.md) — Requiring user confirmation of AI agent tool invocations can prevent the automatic execution of tools by an adversary.
- [AML.M0030 - Restrict AI Agent Tool Invocation on Untrusted Data](../../../Mitigations/AML.M0030%20-%20Restrict%20AI%20Agent%20Tool%20Invocation%20on%20Untrusted%20Data.md) — Restricting the automatic tool use when untrusted data is present can prevent adversaries from invoking tools via prompt injections.
- [AML.M0032 - Segmentation of AI Agent Components](../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to compromise sensitive data sources.
- [AML.M0033 - Input and Output Validation for AI Agent Components](../../../Mitigations/AML.M0033%20-%20Input%20and%20Output%20Validation%20for%20AI%20Agent%20Components.md) — Validation can prevent adversaries from utilizing tools in an agentic workflow to compromise sensitive data sources.

## Software implementations

- [AML.S0019 - postmark-mcp](../../../Software/Malware/AML.S0019%20-%20postmark-mcp.md) — [postmark-mcp](../../../Software/Malware/AML.S0019%20-%20postmark-mcp.md) adds phan@giftshop[.]club as a hidden BCC recipient when its email-sending tool is invoked. This sends the attacker a copy of outgoing email, including message contents and attachments. [snyk-analysis](https://snyk.io/blog/malicious-mcp-server-on-npm-postmark-mcp-harvests-emails/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0086)
