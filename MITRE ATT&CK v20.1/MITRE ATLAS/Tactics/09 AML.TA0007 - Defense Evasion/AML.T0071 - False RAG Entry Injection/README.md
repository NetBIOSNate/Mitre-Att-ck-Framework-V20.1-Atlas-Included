# AML.T0071 - False RAG Entry Injection

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may introduce false entries into a victim's retrieval augmented generation (RAG) database. Content designed to be interpreted as a document by the large language model (LLM) used in the RAG system is included in a data source being ingested into the RAG database. When a RAG entry containing the false document is retrieved, the LLM is tricked into treating part of the retrieved content as a false RAG result. 

By including a false RAG document inside of a regular RAG entry, it bypasses data monitoring tools. It also prevents the document from being deleted directly. 

The adversary may use discovered system keywords to learn how to instruct a particular LLM to treat content as a RAG entry. They may be able to manipulate the injected entry's metadata including document title, author, and creation date.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s09)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Check retrieved document bodies for embedded content that impersonates separate retrieval results, documents, or metadata. Preserve document structure and source metadata supplied by the retrieval system rather than accepting replacements asserted within document text.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0071)
