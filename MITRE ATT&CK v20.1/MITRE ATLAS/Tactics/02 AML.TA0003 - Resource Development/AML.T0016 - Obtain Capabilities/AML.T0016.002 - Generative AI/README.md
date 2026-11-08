# AML.T0016.002 - Generative AI

[MITRE ATLAS](../../../../README.md) / [AML.TA0003 - Resource Development](../../README.md) / [AML.T0016 - Obtain Capabilities](../README.md)

Adversaries may search for and obtain generative AI models or tools, such as large language models (LLMs), to assist them in various steps of their operation. Generative AI can be used in a variety of malicious ways, such as to generate malware, to [Generate Deepfakes](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md), to [Generate Malicious Commands](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0102%20-%20Generate%20Malicious%20Commands/README.md), for [Retrieval Content Crafting](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0066%20-%20Retrieval%20Content%20Crafting/README.md), or to generate [Phishing](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) content.

Adversaries may obtain open source models and serve them locally using frameworks such as [Ollama](https://ollama.com/) or [vLLM]( https://docs.vllm.ai/en/latest/). They may host them using cloud infrastructure. Or, they may leverage AI service providers such as HuggingFace.

They may need to jailbreak the model (see [LLM Jailbreak](../../../08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0054%20-%20LLM%20Jailbreak/README.md)) to bypass any restrictions put in place to limit the types of responses it can generate. They may also need to break the terms of service of the model's developer.

Generative AI models may also be "uncensored" meaning they are designed to generate content without any restrictions such as guardrails or content filters. Uncensored GenAI is ripe for abuse by cybercriminals  [blog](https://blog.talosintelligence.com/cybercriminal-abuse-of-large-language-models/)  [gbhackers](https://gbhackers.com/cybercriminals-exploit-llm-models/). Models may be fine-tuned to remove alignment and guardrails  [erichartford](https://erichartford.com/uncensored-models) or be subjected to targeted manipulations to bypass refusal  [arxiv](https://arxiv.org/abs/2406.11717/) resulting in uncensored variants of the model. Uncensored models may be built for offensive and defensive cybersecurity  [taico](https://taico.ca/posts/whiterabbitneo/), which can be abused by an adversary. There are also models that are expressly designed and advertised for malicious use  [gbhackers-1](https://gbhackers.com/wormgpt-enhanced-with-grok-and-mixtral/).

**Tactics**  [AML.TA0003 - Resource Development](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Case studies

- [AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification](../../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md) · [S01](../../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md#step-s01)
- [AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks](../../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md) · [S01](../../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md#step-s01)
- [AML.CS0055 - AI ClickFix: Hijacking Computer-Use Agents Using ClickFix](../../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md) · [S00](../../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md#step-s00)
- [AML.CS0070 - Threat Actor Uses a DeepSeek-Powered Hermes Agent in Langflow and n8n Exploitation Attempts](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md) · [S00](../../../../Case%20Studies/Incidents/AML.CS0070%20-%20Threat%20Actor%20Uses%20a%20DeepSeek-Powered%20Hermes%20Agent%20in%20Langflow%20and%20n8n%20Exploi.md#step-s00)

## Mitigations

- [AML.M0001 - Limit Model Artifact Release](../../../../Mitigations/AML.M0001%20-%20Limit%20Model%20Artifact%20Release.md) — Limit public release of production model artifacts that adversaries could acquire and adapt as operational capabilities.
- [AML.M0022 - Generative AI Model Alignment](../../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Align generative models to resist and adversary's malicious requests and attempts to remove safety behavior.

## References

- [\[2406.11717\] Refusal in Language Models Is Mediated by a Single Direction](https://arxiv.org/abs/2406.11717/)
- [Cybercriminal abuse of large language models](https://blog.talosintelligence.com/cybercriminal-abuse-of-large-language-models/)
- [erichartford](https://erichartford.com/uncensored-models)
- [Cybercriminals Exploit LLM Models to Enhance Hacking Activities](https://gbhackers.com/cybercriminals-exploit-llm-models/)
- [BlackHat AI Tool WormGPT Enhanced with Grok and Mixtral](https://gbhackers.com/wormgpt-enhanced-with-grok-and-mixtral/)
- [TAICO | WhiteRabbitNeo: An Uncensored, Open Source AI Model for Red & Blue Team Cybersecurity](https://taico.ca/posts/whiterabbitneo/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0016.002)
