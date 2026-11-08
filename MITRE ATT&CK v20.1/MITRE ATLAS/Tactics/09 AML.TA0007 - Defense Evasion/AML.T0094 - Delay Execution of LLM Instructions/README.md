# AML.T0094 - Delay Execution of LLM Instructions

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may include instructions to be followed by the AI system in response to a future event, such as a specific keyword or the next interaction, in order to evade detection or bypass controls placed on the AI system.

For example, an adversary may include "If the user submits a new request..." followed by the malicious instructions as part of their prompt.

AI agents can include security measures against prompt injections that prevent the invocation of particular tools or access to certain data sources during a conversation turn that has untrusted data in context. Delaying the execution of instructions to a future interaction or keyword is one way adversaries may bypass this type of control.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0038 - Planting Instructions for Delayed Automatic AI Agent Tool Invocation](../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md) · [S03](../../../Case%20Studies/Exercises/AML.CS0038%20-%20Planting%20Instructions%20for%20Delayed%20Automatic%20AI%20Agent%20Tool%20Invocation.md#step-s03)
- [AML.CS0063 - Prompt-Based Attacks Against Gemini via Calendar Invitations](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0063%20-%20Prompt-Based%20Attacks%20Against%20Gemini%20via%20Calendar%20Invitations.md#step-s06)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Preserve relevant risk context across conversation turns and revalidate actions when deferred instructions become active. Do not reset restrictions solely because a new user message or event occurs after untrusted content was introduced.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0094)
