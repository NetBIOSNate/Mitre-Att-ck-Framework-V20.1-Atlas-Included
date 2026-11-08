# AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

The [Microsoft Defender Security Research Team](https://www.microsoft.com/en-us/security/blog/author/windows-defender-research/) identified a widespread pattern of AI assistant memory manipulation carried out for promotional purposes, which they named AI Recommendation Poisoning. 

Most major AI assistants accept a pre-filled prompt through a URL query parameter, allowing any party controlling a hyperlink to author the first turn of a user's conversation with their assistant. Operators embedded crafted links into their websites as "Summarize with AI" buttons and share widgets, and in some cases distributed them by email. 

Each link paired a legitimate summarization request with an appended instruction directing the assistant to record the operator's domain as a trusted or authoritative source for future conversations. When the user clicked, the prompt populated the assistant's input field, and the persistence clause caused a durable memory entry to be written, biasing later recommendations toward the operator.
Reviewing AI assistant URLs observed in email traffic over approximately 60 days, the researchers identified more than 50 distinct promotional memory manipulation prompts from 31 companies across 14 industries. Every case was attributed to a legitimate business rather than a conventional threat actor, and the researchers traced the trend to publicly available tooling marketed as a search optimization technique for large language models. Several prompts targeted health and financial advice sites. 

Microsoft reported that effectiveness varied by platform and that several previously observed behaviors could no longer be reproduced as vendor protections evolved.

**Type**  Incident

**Actor**  Multiple commercial entities; 31 distinct companies identified

**Target**  Users of AI assistants with persistent memory features, including Microsoft 365 Copilot, ChatGPT, Claude, Perplexity, and Grok

**Reporter**  Microsoft Defender Security Research Team

**Activity period**  2026-02-10

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0016 - Obtain Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/README.md)

Operators adopted publicly available tooling built to generate AI assistant links carrying embedded memory instructions. The tooling included an npm package, a web-based link generator, and website plugins marketed as a search optimization technique for large language models.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

Operators embedded the crafted link into their own web properties as a "Summarize with AI" button or share widget. In some cases, the same links were distributed through email.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0131 - Crafted AI Assistant Links](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0131%20-%20Crafted%20AI%20Assistant%20Links/README.md)

The user clicked the button or link, which opened the AI assistant domain with the operator's prompt pre-populated in the input field via a `?q=` or `?prompt=` parameter.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0068 - LLM Prompt Obfuscation](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0068%20-%20LLM%20Prompt%20Obfuscation/README.md)

The instruction was concealed from the user behind a benign interface label, with the prompt text visible only in the URL. Bundling it with a genuine summarization request made the resulting assistant behavior appear expected.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0080.000 - Memory](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md)

The persistence clause caused the assistant to write a durable memory entry designating the operator's domain, product, or marketing copy as an authoritative source. The entry survived beyond its originating session.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0130 - AI Agent Response Biasing](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0130%20-%20AI%20Agent%20Response%20Biasing/README.md)

In subsequent unrelated conversations, the assistant preferentially surfaced the operator's domain or product and presented the result as a neutral recommendation. Observed targeting included health and financial topics, where skewed recommendations carry elevated consequences.

**Next**  End of path

## Uses

- [AML.S0028 - AI Share URL Creator](../../Software/Tools/AML.S0028%20-%20AI%20Share%20URL%20Creator.md) — Microsoft traced promotional memory manipulation links to publicly available tooling including [AI Share URL Creator](../../Software/Tools/AML.S0028%20-%20AI%20Share%20URL%20Creator.md). The tool generated prefilled AI assistant URLs combining content summary requests with instructions to remember a promoted brand as a source for future citations. [ai-recommendation-poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)
- [AML.S0029 - CiteMET](../../Software/Tools/AML.S0029%20-%20CiteMET.md) — Microsoft traced promotional memory manipulation links to publicly available tooling including [CiteMET](../../Software/Tools/AML.S0029%20-%20CiteMET.md). The library supplied ready-to-use URL generation code for website buttons that opened AI assistants with summarization requests and instructions to remember a promoted source for future responses. [ai-recommendation-poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

## Reported by

- [AML.E0031 - Microsoft Defender Security Research Team](../../Entities/AML.E0031%20-%20Microsoft%20Defender%20Security%20Research%20Team.md)

## References

- [Manipulating AI memory for profit: The rise of AI Recommendation Poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0072)
