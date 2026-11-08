# AML.T0054 - LLM Jailbreak

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may induce a large language model (LLM) to ignore, circumvent, or override its safety/alignment behaviors and/or guardrails to elicit outputs the model is intended to withhold. Once jailbroken, the LLM may be used in unintended ways by the adversary. Jailbreaks may be achieved via adversarial prompting, or by modifying model weights or safety mechanisms.

Adversaries may attempt a jailbreak for [Defense Evasion](../README.md) of the LLM's guidelines and guardrails itself to then reveal information (ex: [Data from AI Services](../../13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md), [Discover LLM System Information](../../11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/README.md)) or generate harmful content (ex: [Generate Malicious Commands](../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0102%20-%20Generate%20Malicious%20Commands/README.md), [Spearphishing via Social Engineering LLM](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/AML.T0052.000%20-%20Spearphishing%20via%20Social%20Engineering%20LLM/README.md)). They may also jailbreak a model for [Privilege Escalation](../../08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) to invoke tools or perform actions for their own purposes (ex: [AI Agent Tool Invocation](../../06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md)) or abuse the agent for a [Command and Control](../../14%20AML.TA0014%20-%20Command%20and%20Control/README.md) channel (ex: [AI Agent](../../14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0108%20-%20AI%20Agent/README.md)).

Adversaries use a variety of strategies to craft jailbreak prompts. Prompts may target specific models or model families and are iterated upon until successful. Model providers actively update their model guardrails to make them more resistant to jailbreak prompts as new prompts are developed. Common strategies  [jailbreak-guide](https://www.promptfoo.dev/blog/how-to-jailbreak-llms/) include but are not limited to:

- Instruction override: Use phrasing that attempts to supersede prior constraints (e.g. "ignore previous instructions").
- Roleplay / persona switching: Instruct the LLM to adopt an identity or mode that allows unrestricted answers (e.g. "as a security researcher").
- Fictionalization and hypotheticals: Instruct the LLM to include disallowed content as part of a story, screenplay, or educational scenario.
- Separate intent from content: request analysis, examples, templates, or edge cases, that implicitly contain disallowed content.
- Multi-turn escalation / Crescendo: Utilize a sequence of prompts that start benign, establish trust, then gradually cross policy boundaries with incremental prompts.
- Constrained output formats: Instruct the LLM to output to a strict schema or format (e.g. JSON, YAML, code, or tables).
- Data structure injection: Use structured prompts (e.g. YAML, JSON, XML, etc.) to steer the LLM to produce structured outputs such as tool schemas or workflow fragments. This can be used by the adversary to call tools, pass dangerous inputs into legitimate tools, or hijack workflows. [zenity-dsi](https://labs.zenity.io/p/data-structure-injection-dsi-in-ai-agents)
- Obfuscation and transformation: Use encoding, transformations, translation, or euphemisms, (e.g., base64 encoding, "describe it in another language").
- Create a high priority objective: Frame compliance as necessary to fulfill the user's main task (e.g. "to complete the evaluation," "to follow the spec," "to follow safety guidelines").
- Affirmation: Appending affirmations such as "sure" to the end of prompts can help bypass refusals to generate malicious or otherwise undesired content. [cybernews](https://cybersecuritynews.com/github-copilot-jailbreak-vulnerability)

Adversaries may also use algorithmic approaches to generating jailbreak prompts  [jailbreak-zoo](https://arxiv.org/abs/2407.01599)  [jailbreak-survey](https://arxiv.org/abs/2407.04295). Algorithmic jailbreak generation allows for automated methods that discover jailbreaks at scale. Some approaches automate manual strategies  [autodan](https://arxiv.org/abs/2310.04451)  [gptfuzzer](https://arxiv.org/abs/2309.10253)  [crescendo](https://arxiv.org/abs/2404.01833)  [echo-chamber](https://arxiv.org/abs/2601.05742) while others optimize a string of tokens directly  [universal](https://arxiv.org/abs/2307.15043) to produce nonsensical text. Both black-box (applicable to commercial models where the adversary has only query access to the model) and white-box (applicable in the open-source setting, where the adversary has full access to the model weights) optimization approaches are viable.

Adversaries may also directly manipulate a model's weights, or modify or remove parts of a model to create a jailbroken or "uncensored" variant of the target model. This is applicable to open-source models, or cases where the adversary gains full access to the target model. Approaches include fine-tuning to reduce refusals  [single-direction](https://arxiv.org/abs/2406.11717), targeted model editing  [rome](https://arxiv.org/abs/2202.05262), addition of adapters  [lora](https://arxiv.org/abs/2310.20624), and removing safety mechanisms such as guardrails.

Jailbreak prompts that are known to work on various classes of LLMs are often published in the open-source community  [dan](https://github.com/0xk1h0/ChatGPT_DAN). Jailbroken or uncensored LLMs that have been trained or fine-tuned to be jailbroken are shared in public model registries such as huggingface  [abliteration](https://huggingface.co/blog/mlabonne/abliteration).

**Tactics**  [AML.TA0012 - Privilege Escalation](../../08%20AML.TA0012%20-%20Privilege%20Escalation/README.md), [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s06)
- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s07)
- [AML.CS0046 - Data Destruction via Indirect Prompt Injection Targeting Claude Computer-Use](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md#step-s03)
- [AML.CS0051 - OpenClaw Command & Control via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md) · [S11](../../../Case%20Studies/Exercises/AML.CS0051%20-%20OpenClaw%20Command%20%26%20Control%20via%20Prompt%20Injection.md#step-s11)
- [AML.CS0052 - LLMSmith: RCE Vulnerabilities in LLM-Integrated Applications](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0052%20-%20LLMSmith%20-%20RCE%20Vulnerabilities%20in%20LLM-Integrated%20Applications.md#step-s06)
- [AML.CS0057 - Storm-2139 Azure OpenAI Guardrail Bypass](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0057%20-%20Storm-2139%20Azure%20OpenAI%20Guardrail%20Bypass.md#step-s05)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s08)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s08)
- [AML.CS0067 - Claude Code GitHub Action Secret Exposure](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0067%20-%20Claude%20Code%20GitHub%20Action%20Secret%20Exposure.md#step-s06)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s03)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S09](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s09)

## Mitigations

- [AML.M0008 - Validate AI Model](../../../Mitigations/AML.M0008%20-%20Validate%20AI%20Model.md) — Evaluate models against varied adversarial prompts and multi-turn interactions for violations of behavioral or security requirements. Repeat evaluation after fine-tuning or model updates to identify regressions.
- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Evaluate prompts and conversation history for attempts to circumvent behavioral restrictions, and independently check generated outputs and proposed actions against policy. Block prohibited results even when the model follows a jailbreak prompt.
- [AML.M0021 - Generative AI Guidelines](../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Model guidelines can instruct the model to refuse a response to unsafe inputs.
- [AML.M0022 - Generative AI Model Alignment](../../../Mitigations/AML.M0022%20-%20Generative%20AI%20Model%20Alignment.md) — Model alignment can improve the parametric safety of a model by guiding it away from unsafe prompts and responses.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Exercise manual and automated multi-turn, multilingual, encoded, transformed, and multimodal jailbreaks. Incorporate successful cases into guardrails, guidelines, alignment, monitoring, and regression evaluations.

## Software implementations

- [AML.S0020 - de3u](../../../Software/Tools/AML.S0020%20-%20de3u.md) — [de3u](../../../Software/Tools/AML.S0020%20-%20de3u.md) includes functionality designed to prevent Azure OpenAI Service from revising submitted image-generation prompts. Microsoft identified this functionality, together with content-policy rejection feedback, as supporting circumvention of the service's content safeguards. [microsoft-complaint](https://www.akingump.com/a/web/tA6v8pfayLrekvqFsLVwXT/microsoft-vs-storm-2139.pdf)
- [AML.S0024 - G0DM0D3](../../../Software/Tools/AML.S0024%20-%20G0DM0D3.md) — [G0DM0D3](../../../Software/Tools/AML.S0024%20-%20G0DM0D3.md) combines model-specific jailbreak prompts with input transformations intended to circumvent language-model safeguards. It can submit queries to multiple models in parallel and score their responses to select a preferred result. [canonical-source](https://github.com/elder-plinius/G0DM0D3)
- [AML.S0033 - L1B3RT4S](../../../Software/Tools/AML.S0033%20-%20L1B3RT4S.md) — [L1B3RT4S](../../../Software/Tools/AML.S0033%20-%20L1B3RT4S.md) supplies prompt templates that combine user requests with unrestricted persona roleplay, purported system instruction updates, and instructions to suppress refusals. Some templates transform instructions using stylized Unicode, character substitutions, or encoding to obscure their content while directing the model to produce otherwise restricted responses. [canonical-source](https://github.com/elder-plinius/L1B3RT4S)
- [AML.S0034 - DAN (Do Anything Now)](../../../Software/Tools/AML.S0034%20-%20DAN%20%28Do%20Anything%20Now%29.md) — [DAN (Do Anything Now)](../../../Software/Tools/AML.S0034%20-%20DAN%20%28Do%20Anything%20Now%29.md) attempts to bypass model safeguards by instructing the model to adopt a persona that must answer requests without refusals or content restrictions. Variants reinforce these instructions through paired standard and unrestricted responses, fictional penalties for refusing, and follow-up reminders to remain in character. [canonical-source](https://github.com/0xk1h0/ChatGPT_DAN)

## References

- [Uncensor any LLM with abliteration](https://huggingface.co/blog/mlabonne/abliteration)
- [AutoDAN: Generating Stealthy Jailbreak Prompts on Aligned Large Language Models](https://arxiv.org/abs/2310.04451)
- [Great, Now Write an Article About That: The Crescendo Multi-Turn LLM Jailbreak Attack](https://arxiv.org/abs/2404.01833)
- [ChatGPT DAN](https://github.com/0xk1h0/ChatGPT_DAN)
- [The Echo Chamber Multi-Turn LLM Jailbreak](https://arxiv.org/abs/2601.05742)
- [GPTFUZZER: Red Teaming Large Language Models with Auto-Generated Jailbreak Prompts](https://arxiv.org/abs/2309.10253)
- [Jailbreaking LLMs: A Comprehensive Guide (With Examples)](https://www.promptfoo.dev/blog/how-to-jailbreak-llms/)
- [Jailbreak Attacks and Defenses Against Large Language Models: A Survey](https://arxiv.org/abs/2407.04295)
- [JailbreakZoo: Survey, Landscapes, and Horizons in Jailbreaking Large Language and Vision-Language Models](https://arxiv.org/abs/2407.01599)
- [LoRA Fine-tuning Efficiently Undoes Safety Training in Llama 2-Chat 70B](https://arxiv.org/abs/2310.20624)
- [Locating and Editing Factual Associations in GPT](https://arxiv.org/abs/2202.05262)
- [Refusal in Language Models Is Mediated by a Single Direction](https://arxiv.org/abs/2406.11717)
- [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://arxiv.org/abs/2307.15043)
- [GitHub Copilot Jailbreak Vulnerability Let Attackers Train Malicious Models](https://cybersecuritynews.com/github-copilot-jailbreak-vulnerability)
- [Data-Structure Injection (DSI) in AI Agents](https://labs.zenity.io/p/data-structure-injection-dsi-in-ai-agents)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0054)
