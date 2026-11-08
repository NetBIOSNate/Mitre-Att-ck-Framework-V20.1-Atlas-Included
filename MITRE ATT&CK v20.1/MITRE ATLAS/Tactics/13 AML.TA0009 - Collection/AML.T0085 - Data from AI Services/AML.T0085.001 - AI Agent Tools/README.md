# AML.T0085.001 - AI Agent Tools

[MITRE ATLAS](../../../../README.md) / [AML.TA0009 - Collection](../../README.md) / [AML.T0085 - Data from AI Services](../README.md)

Adversaries may collect sensitive information through tools available to an AI agent. These tools may provide access to local files, databases, email and messaging systems, business applications, cloud resources, or other services. The agent's tools may operate with credentials or permissions that allow access to information the adversary cannot obtain directly.

Adversaries may direct or manipulate the agent to invoke tools that read files, search records, query applications, or retrieve other sensitive content. Collection may occur through legitimate-looking requests, injected instructions, or sequences of tool calls that first identify available information and then retrieve selected records.

**Tactics**  [AML.TA0009 - Collection](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S12](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s12)
- [AML.CS0038 - Planting Instructions for Delayed Automatic AI Agent Tool Invocation](../../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md#step-s05)
- [AML.CS0039 - Living Off AI: Prompt Injection via Jira Service Management](../../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0039%20-%20Living%20Off%20AI%20-%20Prompt%20Injection%20via%20Jira%20Service%20Management.md#step-s06)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S18](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s18)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s07), [S11](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s11)

## Mitigations

- [AML.M0022 - Generative AI Model Alignment](../../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Train or fine-tune agents to keep information-retrieval tool calls within the authorized task and resist requests or injected instructions that induce collection of unrelated or restricted information.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Log requests to AI services to detect malicious queries for data.
- [AML.M0026 - Manage AI Agent Service Access](../../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Limit service roles and credentials to data sources and records required by approved workflows. Separate access across unrelated workflows or tenants and authorize retrieval initiators to prevent requests from exercising unrelated data-access privileges.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Limit delegated read, search, and query permissions to resources required for the user's task. Bind access to the authorizing user and separate users' credentials to prevent retrieval under another user's authority.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Enforce caller-specific authorization on tools that read files, search records, query applications, or retrieve other data. Preserve user and tenant restrictions when selecting downstream credentials and accessing backend systems to prevent broader tool privileges from expanding access.
- [AML.M0032 - Segmentation of AI Agent Components](../../../../Mitigations/AML.M0032%20-%20Segmentation%20of%20AI%20Agent%20Components.md) — Segmentation can prevent adversaries from utilizing tools in an agentic workflow to collect sensitive data.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0085.001)
