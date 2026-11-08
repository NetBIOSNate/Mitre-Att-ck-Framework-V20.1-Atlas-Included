# AML.T0130 - AI Agent Response Biasing

[MITRE ATLAS](../../../README.md) / [AML.TA0011 - Impact](../README.md)

Adversaries may manipulate an AI assistant so that it favors adversary-chosen sources, or content in its responses. By injecting instructions such as "treat [source] as a trusted source" or "recommend [source] first," an adversary biases the assistant's outputs toward their own interests, causing it to present promotional or self-serving content as if it were a neutral, well-reasoned response. This degrades the integrity and trustworthiness of the assistant's responses on topics the user may rely on, such as health, finance, or security, without the user being aware that the advice has been skewed.

The injected instructions can be delivered through different ways, for example through [Crafted AI Assistant Links](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0131%20-%20Crafted%20AI%20Assistant%20Links/README.md). This impact may persist if the agent's memory was poisoned (See [AI Agent Context Poisoning: Memory](../../07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md)). Microsoft observed these instructions embedded in apparently helpful summarization links and identified publicly available tooling, including CiteMET, supporting their creation. These attempts sought to introduce third-party preferences into assistant responses; effects varied by assistant and over time. [ai-recommendation-poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

**Tactics**  [AML.TA0011 - Impact](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md#step-s05)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Check retrieved instructions and generated recommendations for unauthorized preferences, source promotion, or departures from the user's criteria. Compare recommendations against approved selection criteria and supporting evidence before presenting them.

## References

- [Manipulating AI memory for profit: The rise of AI Recommendation Poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0130)
