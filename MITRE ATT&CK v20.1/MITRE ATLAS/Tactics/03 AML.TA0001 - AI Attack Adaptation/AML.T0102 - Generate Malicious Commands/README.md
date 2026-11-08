# AML.T0102 - Generate Malicious Commands

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries may use large language models (LLMs) to dynamically generate malicious commands from natural language. Dynamically generated commands may be harder to detect as the attack signature is constantly changing. AI-generated commands may also allow adversaries to more rapidly adapt to different environments and adjust their tactics.

Adversaries may utilize LLMs present in the victim's environment or call out to externally hosted services. [APT28](https://attack.mitre.org/groups/G0007) utilized a model hosted on HuggingFace in a campaign with their LAMEHUG malware  [logpoint](https://logpoint.com/en/blog/apt28s-new-arsenal-lamehug-the-first-ai-powered-malware). In either case prompts to generate malicious code can blend in with normal traffic.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s05)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S07](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s07)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s06)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s06), [S28](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s28)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect requests and generated commands for prohibited behavior using the task context and service policy. Block malicious command generation or release through the protected service, and independently validate commands before execution when an execution interface is present.
- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Align generative AI models with safety objectives to reduce the likelihood that they will generate malicious commands or harmful instructions.

## Software implementations

- [AML.S0015 - LAMEHUG](../../../Software/Malware/AML.S0015%20-%20LAMEHUG.md) — [LAMEHUG](../../../Software/Malware/AML.S0015%20-%20LAMEHUG.md) sends natural-language prompts to Qwen2.5-Coder-32B-Instruct through the Hugging Face API to generate Windows commands for system reconnaissance and document collection, then executes the returned commands locally. [source-1](https://www.bleepingcomputer.com/news/security/lamehug-malware-uses-ai-llm-to-craft-windows-data-theft-commands-in-real-time/)
- [AML.S0017 - HONESTCUE](../../../Software/Malware/AML.S0017%20-%20HONESTCUE.md) — [HONESTCUE](../../../Software/Malware/AML.S0017%20-%20HONESTCUE.md) sends hard-coded prompts to the Gemini API requesting C# source code that downloads and executes a subsequent payload. It compiles the generated code with CSharpCodeProvider and executes it, including variants that load the downloaded payload directly into memory. [source-1](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use)
- [AML.S0018 - Xanthorox](../../../Software/Tools/AML.S0018%20-%20Xanthorox.md) — [Xanthorox](../../../Software/Tools/AML.S0018%20-%20Xanthorox.md) was marketed as providing autonomous malware code generation. [source-1](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use)

## References

- [LAMEHUG: APT28's First AI-Powered Malware Explained | Guardsix](https://logpoint.com/en/blog/apt28s-new-arsenal-lamehug-the-first-ai-powered-malware)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0102)
