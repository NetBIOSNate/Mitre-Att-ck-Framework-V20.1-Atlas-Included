# AML.T0051.002 - Triggered

[MITRE ATLAS](../../../../README.md) / [AML.TA0005 - Execution](../../README.md) / [AML.T0051 - LLM Prompt Injection](../README.md)

An adversary may trigger a prompt injection via a user action or event that occurs within the victim's environment. Triggered prompt injections often target AI agents, which can be activated by means the adversary identifies during [Discovery](../../../11%20AML.TA0008%20-%20Discovery/README.md) (See [Activation Triggers](../../../11%20AML.TA0008%20-%20Discovery/AML.T0084%20-%20Discover%20AI%20Agent%20Configuration/AML.T0084.002%20-%20Activation%20Triggers/README.md)). These malicious prompts may be hidden or obfuscated from the user and may already exist somewhere in the victim's environment from the adversary performing [Prompt Infiltration via Public-Facing Application](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0093%20-%20Prompt%20Infiltration%20via%20Public-Facing%20Application/README.md). This type of injection may be used by the adversary to gain a foothold in the system or to target an unwitting user of the system.

**Tactics**  [AML.TA0005 - Execution](../../README.md)

**Platforms**  [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s05)
- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s03)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s06)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s07)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s07)

## Mitigations

- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.M0033 - Input and Output Validation for AI Agent Components](../../../../Mitigations/AML.M0033%20-%20Input%20and%20Output%20Validation%20for%20AI%20Agent%20Components.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Place controlled instructions in content or workflows where later user actions or system events activate them. Verify trigger authorization, context handling, action restrictions, and monitoring.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0051.002)
