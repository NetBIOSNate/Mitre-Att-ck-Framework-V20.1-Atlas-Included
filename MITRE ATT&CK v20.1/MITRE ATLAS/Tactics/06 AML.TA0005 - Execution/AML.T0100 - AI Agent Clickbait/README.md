# AML.T0100 - AI Agent Clickbait

[MITRE ATLAS](../../../README.md) / [AML.TA0005 - Execution](../README.md)

Adversaries may craft deceptive content designed to bait computer-using AI agents or AI web browsers and tools into taking unintended actions, such as clicking buttons, copying code, or navigating to specific web pages. These attacks exploit the agent's interpretation of UI content, visual cues, and natural language embedded in processed artifacts, such as a website or a document, and aim at the agent's decision process rather than a human reader's. 

When successful, AI Agent Clickbait can lead the victim's agent to inadvertently copy and execute malicious code on the user's operating system or perform data exfiltration. The AI Agent Clickbait may also include a [LLM Prompt Injection: Indirect](../AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md), which can influence or manipulate the victim's agent in adversary-controlled ways.

**Tactics**  [AML.TA0005 - Execution](../README.md)

**Platforms**  [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0055 - AI ClickFix: Hijacking Computer-Use Agents Using ClickFix](../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0055%20-%20AI%20ClickFix%20-%20Hijacking%20Computer-Use%20Agents%20Using%20ClickFix.md#step-s04)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Evaluate model-visible interface content and proposed computer-use actions against the authorized task. Block deceptive instructions that induce unrelated navigation, command execution, credential entry, or data transfer, and validate destinations before acting.
- [AML.M0021 - Generative AI Guidelines](../../../Mitigations/AML.M0021%20-%20Generative%20AI%20Guidelines.md) — Instruct agents to treat webpage instructions as untrusted and request approval for consequential actions.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0100)
