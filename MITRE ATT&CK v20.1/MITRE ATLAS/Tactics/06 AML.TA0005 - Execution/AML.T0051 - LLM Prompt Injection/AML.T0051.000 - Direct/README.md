# AML.T0051.000 - Direct

[MITRE ATLAS](../../../../README.md) / [AML.TA0005 - Execution](../../README.md) / [AML.T0051 - LLM Prompt Injection](../README.md)

An adversary may inject prompts directly as a user of the LLM. This type of injection may be used by the adversary to gain a foothold in the system or to misuse the LLM itself, as for example to generate harmful content.

**Tactics**  [AML.TA0005 - Execution](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0016 - Achieving Code Execution in MathGPT via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md#step-s02)
- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s05)
- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S06](../../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s06)
- [AML.CS0043 - Malware Prototype with Embedded Prompt Injection](../../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md#step-s02)
- [AML.CS0047 - Code to Deploy Destructive AI Agent Discovered in Amazon Q VS Code Extension](../../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md) · [S05](../../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md#step-s05)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S14](../../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s14)
- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s05)
- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s04)
- [AML.CS0062 - RCE Vulnerability in Semantic Kernel Search Plugin](../../../../Case%20Studies/Exercises/AML.CS0062%20-%20RCE%20Vulnerability%20in%20Semantic%20Kernel%20Search%20Plugin.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0062%20-%20RCE%20Vulnerability%20in%20Semantic%20Kernel%20Search%20Plugin.md#step-s02)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S02](../../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s02)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S08](../../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s08)

## Mitigations

- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.M0033 - Input and Output Validation for AI Agent Components](../../../../Mitigations/AML.M0033%20-%20Input%20and%20Output%20Validation%20for%20AI%20Agent%20Components.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Submit controlled malicious instructions directly through user-facing model and application interfaces. Improve instruction enforcement, input controls, authorization, and monitoring.

## Software implementations

- [AML.S0035 - FRUITSHELL](../../../../Software/Malware/AML.S0035%20-%20FRUITSHELL.md) — [FRUITSHELL](../../../../Software/Malware/AML.S0035%20-%20FRUITSHELL.md) contains hard-coded prompts intended to influence an LLM-powered security system analyzing the code and bypass its detection or analysis. [gtig](https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0051.000)
