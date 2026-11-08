# AML.T0101 - Data Destruction via AI Agent Tool Invocation

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may invoke an AI agent's tool capable of performing mutative operations to perform Data Destruction. Adversaries may destroy data and files on specific systems or in large numbers on a network to interrupt availability to systems, services, and network resources.

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0046 - Data Destruction via Indirect Prompt Injection Targeting Claude Computer-Use](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md#step-s06)
- [AML.CS0047 - Code to Deploy Destructive AI Agent Discovered in Amazon Q VS Code Extension](../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md#step-s06)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S11](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s11)

## Mitigations

- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Log AI agent tool invocations to detect malicious calls.
- [AML.M0026 - Manage AI Agent Service Access](../../../Mitigations/AML.M0026%20-%20Manage%20AI%20Agent%20Service%20Access.md) — Separate deletion, overwrite, and other destructive permissions from routine service access. Limit them to required workflows and target resources, and authorize workflow initiators so that access to the agent does not confer destructive privileges.
- [AML.M0027 - Manage User-Delegated AI Agent Access](../../../Mitigations/AML.M0027%20-%20Manage%20User-Delegated%20AI%20Agent%20Access.md) — Use read-only delegation when modification is unnecessary. Limit deletion and other destructive permissions to explicitly authorized tasks and resources rather than automatically delegating permissions the user possesses.
- [AML.M0028 - Enforce Access Controls for AI Agent Tools](../../../Mitigations/AML.M0028%20-%20Enforce%20Access%20Controls%20for%20AI%20Agent%20Tools.md) — Separately authorize deletion, overwrite, and other destructive tool operations against specific target resources. Withhold destructive permissions from callers and tool execution identities that do not require them.
- [AML.M0029 - Human In-the-Loop for AI Agent Actions](../../../Mitigations/AML.M0029%20-%20Human%20In-the-Loop%20for%20AI%20Agent%20Actions.md) — Requiring user confirmation of AI agent tool invocations can prevent the automatic execution of tools by an adversary.
- [AML.M0030 - Restrict AI Agent Tool Invocation on Untrusted Data](../../../Mitigations/AML.M0030%20-%20Restrict%20AI%20Agent%20Tool%20Invocation%20on%20Untrusted%20Data.md) — Restricting the automatic tool use when untrusted data is present can prevent adversaries from invoking tools via prompt injections.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0101)
