# AML.T0067 - LLM Trusted Output Components Manipulation

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may utilize prompts to a large language model (LLM) which manipulate various components of its response in order to make it appear trustworthy to the user. This helps the adversary continue to operate in the victim's environment and evade detection by the users it interacts with.

The LLM may be instructed to tailor its language to appear more trustworthy to the user or attempt to manipulate the user to take certain actions. Other response components that could be manipulated include links, recommended follow-up actions, retrieved document metadata, and [Citations](AML.T0067.000%20-%20Citations/README.md).

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Sub-techniques

- [AML.T0067.000 - Citations](AML.T0067.000%20-%20Citations/README.md)

## Case studies

- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s08)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s08)
- [AML.CS0064 - Poisoned GGUF Templates: Inference-Time Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0064%20-%20Poisoned%20GGUF%20Templates%20-%20Inference-Time%20Supply%20Chain%20Attack.md#step-s09)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Validate generated citations, links, source metadata, and recommended actions against trusted source records and the authorized task before presenting responses to users. Detect and block fabricated attribution, misleading references, or instructions that use apparent authority to induce unauthorized actions.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0067)
