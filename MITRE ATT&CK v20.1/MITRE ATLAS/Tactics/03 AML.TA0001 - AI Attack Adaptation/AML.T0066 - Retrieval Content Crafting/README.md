# AML.T0066 - Retrieval Content Crafting

[MITRE ATLAS](../../../README.md) / [AML.TA0001 - AI Attack Adaptation](../README.md)

Adversaries may write content designed to be retrieved by user queries and influence a user of the system in some way. This abuses the trust the user has in the system.

The crafted content can be combined with a prompt injection. It can also stand alone in a separate document or email. The adversary must get the crafted content into the victim\u0027s database, such as a vector database used in a retrieval augmented generation (RAG) system. This may be accomplished via cyber access, or by abusing the ingestion mechanisms common in RAG systems (see [RAG Poisoning](../../07%20AML.TA0006%20-%20Persistence/AML.T0070%20-%20RAG%20Poisoning/README.md)).

Large language models may be used as an assistant to aid an adversary in crafting content.

**Tactics**  [AML.TA0001 - AI Attack Adaptation](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s04)
- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md#step-s00)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s01)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0066)
