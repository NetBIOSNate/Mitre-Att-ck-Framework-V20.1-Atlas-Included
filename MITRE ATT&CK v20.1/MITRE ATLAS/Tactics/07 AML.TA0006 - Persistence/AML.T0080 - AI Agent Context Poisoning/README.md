# AML.T0080 - AI Agent Context Poisoning

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may attempt to manipulate the context used by an AI agent's large language model (LLM) to influence the responses it generates or actions it takes. This allows an adversary to persistently change the behavior of the target agent and further their goals.

Context poisoning can be accomplished by prompting the LLM to add instructions or preferences to memory (See [Memory](AML.T0080.000%20-%20Memory/README.md)) or by simply prompting an LLM that uses prior messages in a thread as part of its context (See [Thread](AML.T0080.001%20-%20Thread/README.md)).

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Sub-techniques

- [AML.T0080.000 - Memory](AML.T0080.000%20-%20Memory/README.md)
- [AML.T0080.001 - Thread](AML.T0080.001%20-%20Thread/README.md)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect content entering or reentering an agent's context, including conversation history, summaries, and retrieved memories, for malicious instructions or unauthorized behavioral changes. Block or quarantine suspicious content before incorporation, and independently validate resulting outputs and actions across subsequent interactions.
- [AML.M0031 - Memory Hardening](../../../Mitigations/AML.M0031%20-%20Memory%20Hardening.md) — Memory hardening reduces persistent context poisoning by controlling what an agent may save as memory, preventing saved data from becoming higher-authority instructions, and enabling poisoned records to be identified, quarantined, and rolled back.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Attempt to persist malicious instructions in agent memory and long-lived threads. Verify authorization for context changes, integrity checks, trust labeling, expiration, user visibility, and remediation.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0080)
