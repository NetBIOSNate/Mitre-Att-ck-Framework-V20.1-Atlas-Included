# AML.T0064 - Gather RAG-Indexed Targets

[MITRE ATLAS](../../../README.md) / [AML.TA0002 - Reconnaissance](../README.md)

Adversaries may identify data sources used in retrieval augmented generation (RAG) systems for targeting purposes. By pinpointing these sources, attackers can focus on poisoning or otherwise manipulating the external data repositories the AI relies on.

RAG-indexed data may be identified in public documentation about the system, or by interacting with the system directly and observing any indications of or references to external data sources.

**Tactics**  [AML.TA0002 - Reconnaissance](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s00)

## Mitigations

- [AML.M0000 - Limit Public Release of Information](../../../Mitigations/AML.M0000%20-%20Limit%20Public%20Release%20of%20Information.md) — Withhold public documentation that identifies RAG data sources, indexes, and retrieval architecture.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0064)
