# AML.T0070 - RAG Poisoning

[MITRE ATLAS](../../../README.md) / [AML.TA0006 - Persistence](../README.md)

Adversaries may inject malicious content into data indexed by a retrieval augmented generation (RAG) system to contaminate a future thread through RAG-based search results. This may be accomplished by placing manipulated documents in a location the RAG indexes (see [Gather RAG-Indexed Targets](../../01%20AML.TA0002%20-%20Reconnaissance/AML.T0064%20-%20Gather%20RAG-Indexed%20Targets/README.md)).

The content may be targeted such that it would always surface as a search result for a specific user query. The adversary's content may include false or misleading information. It may also include prompt injections with malicious instructions, or false RAG entries.

**Tactics**  [AML.TA0006 - Persistence](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0024 - Morris II Worm: RAG-Based Attack](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0024%20-%20Morris%20II%20Worm%20-%20RAG-Based%20Attack.md#step-s04)
- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s08)
- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md#step-s04)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s05)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Screen content at ingestion and retrieval for malicious instructions, deceptive claims, and violations of source policies. Quarantine suspicious entries before indexing or exclude them from model context when retrieved.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Seed controlled malicious or misleading content into representative ingestion sources. Improve source authorization, provenance, content validation, indexing controls, and retrieval-time filtering.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0070)
