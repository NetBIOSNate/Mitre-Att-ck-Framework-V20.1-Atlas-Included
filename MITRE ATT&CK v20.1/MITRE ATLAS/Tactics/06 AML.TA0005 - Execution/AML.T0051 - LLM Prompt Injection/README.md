# AML.T0051 - LLM Prompt Injection

[MITRE ATLAS](../../../README.md) / [AML.TA0005 - Execution](../README.md)

An adversary may craft malicious prompts as inputs to an LLM that cause the LLM to act in unintended ways.
These "prompt injections" are often designed to cause the model to ignore aspects of its original instructions and follow the adversary's instructions instead.

Prompt Injections can be an initial access vector to the LLM that provides the adversary with a foothold to carry out other steps in their operation.
They may be designed to bypass defenses in the LLM, or allow the adversary to issue privileged commands.
The effects of a prompt injection can persist throughout an interactive session with an LLM.

Malicious prompts may be injected directly by the adversary ([Direct](AML.T0051.000%20-%20Direct/README.md)) either to leverage the LLM to generate harmful content or to gain a foothold on the system and lead to further effects.
Prompts may also be injected indirectly when the LLM, as part of its normal operation, ingests the malicious prompt from another data source ([Indirect](AML.T0051.001%20-%20Indirect/README.md)). This type of injection can be used by the adversary to gain a foothold on the system or to target the user of the LLM.
Malicious prompts may also be [Triggered](AML.T0051.002%20-%20Triggered/README.md) by user actions or system events.

**Tactics**  [AML.TA0005 - Execution](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0051.000 - Direct](AML.T0051.000%20-%20Direct/README.md)
- [AML.T0051.001 - Indirect](AML.T0051.001%20-%20Indirect/README.md)
- [AML.T0051.002 - Triggered](AML.T0051.002%20-%20Triggered/README.md)

## Case studies

- [AML.CS0037 - Data Exfiltration via Agent Tools in Copilot Studio](../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0037%20-%20Data%20Exfiltration%20via%20Agent%20Tools%20in%20Copilot%20Studio.md#step-s07)

## Used by

- [AML.E0026 - MiniMax](../../../Entities/AML.E0026%20-%20MiniMax.md) (Adversarial Operation) — [MiniMax](../../../Entities/AML.E0026%20-%20MiniMax.md) attempted prompt injections against [Claude Code](../../../Software/Tools/AML.S0022%20-%20Claude%20Code.md) intended to make it identify itself as a MiniMax product. [cisa](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)

## Mitigations

- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models for task redirection by malicious instructions in user inputs, retrieved material, or other model-visible content. Test instruction and data boundaries in the intended deployment configuration and use failures to guide remediation or deployment restrictions.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Use access controls in production to prevent adversaries from injecting malicious prompts.
- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Screen user inputs, retrieved content, and tool responses for instructions that attempt to override authorized behavior. Apply independent checks to resulting outputs and proposed actions, blocking or routing suspicious activity for review before it reaches users or downstream systems.
- [AML.M0021 - Generative AI Guidelines](../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Model alignment can improve the parametric safety of a model by guiding it away from unsafe prompts and responses.
- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.M0033 - Input and Output Validation for AI Agent Components](../../../Mitigations/AML.M0033%20-%20Input%20and%20Output%20Validation%20for%20AI%20Agent%20Components.md) — Validation can prevent adversaries from executing prompt injections that could affect agentic workflows.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Test direct, indirect, and triggered instructions through user input, retrieved data, documents, messages, websites, images, metadata, and tool output. Remediate trust-boundary, instruction-handling, permission, and monitoring failures.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0051)
