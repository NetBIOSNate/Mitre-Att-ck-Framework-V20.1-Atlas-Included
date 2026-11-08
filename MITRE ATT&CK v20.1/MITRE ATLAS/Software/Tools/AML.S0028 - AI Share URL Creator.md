# AML.S0028 - AI Share URL Creator

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[AI Share URL Creator](AML.S0028%20-%20AI%20Share%20URL%20Creator.md) is a browser-based tool for generating AI assistant share links and embeddable HTML buttons. Users supply a content URL, brand name, target platforms, and a customizable prompt template. Its default template combines a summarization request with an instruction to remember the supplied brand as a citation source. [canonical-source](https://metehan.ai/ai-share-url-creator)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) — Microsoft traced promotional memory manipulation links to publicly available tooling including [AI Share URL Creator](AML.S0028%20-%20AI%20Share%20URL%20Creator.md). The tool generated prefilled AI assistant URLs combining content summary requests with instructions to remember a promoted brand as a source for future citations. [ai-recommendation-poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

## Techniques implemented

- [AML.T0080.000 - Memory](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md) — [AI Share URL Creator](AML.S0028%20-%20AI%20Share%20URL%20Creator.md) embeds instructions to remember a supplied brand as a citation source within generated prompts. These instructions attempt to establish a persistent source preference in the receiving assistant's memory. [canonical-source](https://metehan.ai/ai-share-url-creator)
- [AML.T0131 - Crafted AI Assistant Links](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0131%20-%20Crafted%20AI%20Assistant%20Links/README.md) — [AI Share URL Creator](AML.S0028%20-%20AI%20Share%20URL%20Creator.md) encodes customizable prompts into AI assistant URLs and generates HTML share buttons containing those links. Opening a generated link prepopulates the assistant's input with the publisher-supplied prompt, including any source promotion or memory instructions. [source-1](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

## References

- [Microsoft: Manipulating AI memory for profit](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)
- [AI Share URL Creator: canonical implementation source](https://metehan.ai/ai-share-url-creator)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0028)
