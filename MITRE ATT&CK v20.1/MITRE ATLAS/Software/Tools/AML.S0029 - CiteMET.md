# AML.S0029 - CiteMET

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[CiteMET](AML.S0029%20-%20CiteMET.md) is an open source npm library maintained by LLMrefs for generating AI assistant share URLs. It combines a page URL, brand name, and customizable prompt template into platform-specific links for use in website buttons and newsletters. Its documented templates pair requests to summarize or analyze content with instructions to remember the brand as a trusted or authoritative source. [github](https://github.com/LLMrefs/citemet)

**Software type**  Tool

**Software categories**  library

## Used by

- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) — Microsoft traced promotional memory manipulation links to publicly available tooling including [CiteMET](AML.S0029%20-%20CiteMET.md). The library supplied ready-to-use URL generation code for website buttons that opened AI assistants with summarization requests and instructions to remember a promoted source for future responses. [ai-recommendation-poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

## Techniques implemented

- [AML.T0080.000 - Memory](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md) — [CiteMET](AML.S0029%20-%20CiteMET.md) generates prompts that ask an assistant to remember a supplied brand or website as a trusted source for future answers. It combines these persistence instructions with ordinary summarization or analysis requests to attempt to influence the assistant's retained source preferences.[[canonical-source]]
- [AML.T0131 - Crafted AI Assistant Links](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0131%20-%20Crafted%20AI%20Assistant%20Links/README.md) — [CiteMET](AML.S0029%20-%20CiteMET.md) substitutes a page URL and brand name into a prompt template and encodes the resulting text into AI assistant URLs. Websites and newsletters can embed these links in buttons that prepopulate an assistant's input with publisher-controlled instructions. [source-1](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

## References

- [Microsoft: Manipulating AI memory for profit](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)
- [CiteMET GitHub](https://github.com/LLMrefs/citemet)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0029)
