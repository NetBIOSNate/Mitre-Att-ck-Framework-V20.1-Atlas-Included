# AML.T0131 - Crafted AI Assistant Links

[MITRE ATLAS](../../../README.md) / [AML.TA0004 - Initial Access](../README.md)

Adversaries may craft links that open an AI assistant or agent with attacker-controlled input already supplied, so that opening the link initiates an interaction the adversary defines rather than one the target composed. Many AI assistants accept a prompt through URL parameters (for example `?q=` or `?prompt=`) that is automatically populated, and in some cases submitted, when the link is opened. By encoding a chosen prompt into such a link, an adversary can cause the target's assistant to act on supplied instructions as soon as the link is opened.

These links are frequently disguised as helpful actions, such as a "Summarize with AI" button or a share link, and distributed through web pages, emails, documents, or messages. Because the resulting interaction runs in the target's own assistant session, a crafted link can drive a range of downstream impacts depending on the supplied instructions, such as exfiltrating data the assistant can access or for [AI Agent Response Biasing](../../16%20AML.TA0011%20-%20Impact/AML.T0130%20-%20AI%20Agent%20Response%20Biasing/README.md).

Microsoft identified CiteMET and AI Share URL Creator as tools supporting this pattern in its investigation of AI Recommendation Poisoning. The generated links supply instructions to the receiving assistant; execution, memory retention, and downstream effects depend on the assistant's behavior and protections. [ai-recommendation-poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

**Tactics**  [AML.TA0004 - Initial Access](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md#step-s02)

## Software implementations

- [AML.S0028 - AI Share URL Creator](../../../Software/Tools/AML.S0028%20-%20AI%20Share%20URL%20Creator.md) — [AI Share URL Creator](../../../Software/Tools/AML.S0028%20-%20AI%20Share%20URL%20Creator.md) encodes customizable prompts into AI assistant URLs and generates HTML share buttons containing those links. Opening a generated link prepopulates the assistant's input with the publisher-supplied prompt, including any source promotion or memory instructions. [source-1](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)
- [AML.S0029 - CiteMET](../../../Software/Tools/AML.S0029%20-%20CiteMET.md) — [CiteMET](../../../Software/Tools/AML.S0029%20-%20CiteMET.md) substitutes a page URL and brand name into a prompt template and encodes the resulting text into AI assistant URLs. Websites and newsletters can embed these links in buttons that prepopulate an assistant's input with publisher-controlled instructions. [source-1](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

## References

- [Manipulating AI memory for profit: The rise of AI Recommendation Poisoning](https://www.microsoft.com/en-us/security/blog/2026/02/10/ai-recommendation-poisoning/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0131)
