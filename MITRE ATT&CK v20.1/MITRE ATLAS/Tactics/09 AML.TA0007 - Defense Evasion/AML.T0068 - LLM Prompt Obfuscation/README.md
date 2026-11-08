# AML.T0068 - LLM Prompt Obfuscation

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may hide or otherwise obfuscate prompt injections or retrieval content to avoid detection from humans, large language model (LLM) guardrails, or other detection mechanisms.

Text inputs may be obfuscated by modifying how the instructions are rendered, such as small font, text colored the same as the background, or hidden HTML elements. Similarly, approaches for other modalities include low-contrast or tiny text placed inside an image, text overlaid on a busy or camouflaging background, instructions spoken faintly or sped up in audio, or text shown briefly in a single video frame.

Inputs can also be obscured via an encoding scheme such as base64 or rot13. This may bypass LLM guardrails that identify malicious content and may not be as easily identifiable as malicious to a human in the loop.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0020 - Indirect Prompt Injection Threats: Bing Chat Data Pirate](../../../Case%20Studies/Exercises/AML.CS0020%20-%20Indirect%20Prompt%20Injection%20Threats%20-%20Bing%20Chat%20Data%20Pirate.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0020%20-%20Indirect%20Prompt%20Injection%20Threats%20-%20Bing%20Chat%20Data%20Pirate.md#step-s01)
- [AML.CS0026 - Financial Transaction Hijacking with M365 Copilot as an Insider](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0026%20-%20Financial%20Transaction%20Hijacking%20with%20M365%20Copilot%20as%20an%20Insider.md#step-s07)
- [AML.CS0040 - Hacking ChatGPT's Memories with Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0040%20-%20Hacking%20ChatGPT's%20Memories%20with%20Prompt%20Injection.md#step-s01)
- [AML.CS0041 - Rules File Backdoor: Supply Chain Attack on AI Coding Assistants](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0041%20-%20Rules%20File%20Backdoor%20-%20Supply%20Chain%20Attack%20on%20AI%20Coding%20Assistants.md#step-s02)
- [AML.CS0045 - Data Exfiltration via an MCP Server used by Cursor](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md#step-s02), [S07](../../../Case%20Studies/Exercises/AML.CS0045%20-%20Data%20Exfiltration%20via%20an%20MCP%20Server%20used%20by%20Cursor.md#step-s07)
- [AML.CS0046 - Data Destruction via Indirect Prompt Injection Targeting Claude Computer-Use](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0046%20-%20Data%20Destruction%20via%20Indirect%20Prompt%20Injection%20Targeting%20Claude%20Computer-Use.md#step-s04)
- [AML.CS0059 - EchoLeak: Zero-Click Prompt Injection Targeting M365 Copilot for Data Exfiltration](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md) · [S04](../../../Case%20Studies/Exercises/AML.CS0059%20-%20EchoLeak%20-%20Zero-Click%20Prompt%20Injection%20Targeting%20M365%20Copilot%20for%20Data%20Exfil.md#step-s04)
- [AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md#step-s05)
- [AML.CS0066 - ZombieAgent: Data Exfiltration Attack on ChatGPT](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md) · [S02](../../../Case%20Studies/Exercises/AML.CS0066%20-%20ZombieAgent%20-%20Data%20Exfiltration%20Attack%20on%20ChatGPT.md#step-s02)
- [AML.CS0072 - AI Recommendation Poisoning via Crafted AI Assistant Links](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0072%20-%20AI%20Recommendation%20Poisoning%20via%20Crafted%20AI%20Assistant%20Links.md#step-s03)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S13](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s13)

## Mitigations

- [AML.M0020 - Generative AI Guardrails](../../../Mitigations/AML.M0020%20-%20Generative%20AI%20Guardrails.md) — Inspect model-visible content for concealed instructions, including encoded text, hidden formatting, and Unicode manipulation. Normalize or decode supported representations in an isolated inspection process and evaluate both original and transformed content before processing.
- [AML.M0035 - AI Red Team](../../../Mitigations/AML.M0035%20-%20AI%20Red%20Team.md) — Test encoded, transformed, visually hidden, multilingual, and multimodal instructions. Use successful bypasses to improve normalization, decoding, content inspection, and detection controls.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0068)
