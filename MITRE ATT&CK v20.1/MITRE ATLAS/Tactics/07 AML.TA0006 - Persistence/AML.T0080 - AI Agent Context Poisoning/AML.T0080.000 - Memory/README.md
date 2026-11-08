# AML.T0080.000 - Memory

[MITRE ATLAS](../../../../README.md) / [AML.TA0006 - Persistence](../../README.md) / [AML.T0080 - AI Agent Context Poisoning](../README.md)

Adversaries may manipulate the memory of a large language model (LLM) in order to persist changes to the LLM across future chat sessions. 

Memory is a common feature in LLMs that allows them to remember information across chat sessions by utilizing a user-specific database. Because the memory is controlled via normal conversations with the user (e.g. "remember my preference for ...") an adversary can inject memories via Direct or Indirect Prompt Injection. Memories may contain malicious instructions (e.g. instructions that leak private conversations) or may promote the adversary's hidden agenda (e.g. manipulating the user).

**Tactics**  [AML.TA0006 - Persistence](../../README.md)

**Platforms**  [Generative AI](../../../../Platforms/Generative%20AI.md), [Agentic AI](../../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S07](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s07)
- [AML.CS0040 - Hacking ChatGPT's Memories with Prompt Injection](../../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md) · [S04](../../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md#step-s04)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S05](../../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s05)
- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) · [S04](../../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md#step-s04)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect proposed memory writes and retrieved memories for malicious instructions, unauthorized preferences, or changes inconsistent with the user's task. Block or quarantine suspicious content before storage or reuse. Pair content checks with [Memory Hardening](../../../../Mitigations/AML.M0031%20-%20Memory%20Hardening.md).
- [AML.M0031 - Memory Hardening](../../../../Mitigations/AML.M0031%20-%20Memory%20Hardening.md) — Memory hardening reduces persistent context poisoning by controlling what an agent may save as memory, preventing saved data from becoming higher-authority instructions, and enabling poisoned records to be identified, quarantined, and rolled back.
- [AML.M0035 - AI Red Team](../../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Attempt to store controlled malicious instructions or preferences in persistent agent memory. Verify authorization, user visibility, integrity validation, expiration, and memory-remediation controls.

## Software implementations

- [AML.S0028 - AI Share URL Creator](../../../../Software/Tools/AML.S0028%20-%20AI%20Share%20URL%20Creator.md) — [AI Share URL Creator](../../../../Software/Tools/AML.S0028%20-%20AI%20Share%20URL%20Creator.md) embeds instructions to remember a supplied brand as a citation source within generated prompts. These instructions attempt to establish a persistent source preference in the receiving assistant's memory. [canonical-source](https://metehan.ai/ai-share-url-creator)
- [AML.S0029 - CiteMET](../../../../Software/Tools/AML.S0029%20-%20CiteMET.md) — [CiteMET](../../../../Software/Tools/AML.S0029%20-%20CiteMET.md) generates prompts that ask an assistant to remember a supplied brand or website as a trusted source for future answers. It combines these persistence instructions with ordinary summarization or analysis requests to attempt to influence the assistant's retained source preferences.[[canonical-source]]

## References

- [Manipulating AI memory for profit: The rise of AI Recommendation Poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0080.000)
