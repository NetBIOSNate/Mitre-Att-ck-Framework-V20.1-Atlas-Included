# T1608.007 - AI Result Poisoning

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1608 - Stage Capabilities](../README.md)

Adversaries may manipulate publicly accessible web content to influence generative AI systems or AI-powered search engines into retrieving, citing, or recommending attacker-controlled information.(Citation: Digiday AI Result Poisoning)(Citation: Netcraft AI Summaries)

Unlike traditional [SEO Poisoning](https://attack.mitre.org/techniques/T1608/006), which primarily attempts to influence the ordering of conventional search results, AI Result Poisoning targets systems that synthesize information from multiple sources and provide a direct answer to the user. Adversaries may create malicious or misleading websites, publish fabricated claims, generate supporting articles, or establish multiple apparently independent sources that reinforce the same information. These sources may then be retrieved by AI systems using web search or retrieval-augmented generation and incorporated into generated responses. 

Adversaries may use this technique to recommend or link to phishing sites, fraudulent online stores, malicious downloads, impersonation pages, or other attacker-controlled infrastructure.(Citation: dev.to Abusing AI Chatbot Recommendations)(Citation: darkreading geo poisoning)(Citation: darkreading ai result poisoning) It can also be used to promote misinformation or fabricated claims without requiring access to the underlying AI model, system prompt, or application infrastructure.(Citation: Lasso Security AI Engine Poisoning) Because the malicious content can resemble ordinary marketing, editorial, or informational material, traditional prompt injection and malware-focused detections may not identify the activity.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1608/007)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0922 - Detection of AI Result Poisoning](../../../../Defenses/Detection%20Strategies/DET0922%20-%20Detection%20of%20AI%20Result%20Poisoning.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [darkreading geo poisoning](https://www.darkreading.com/vulnerabilities-threats/clickfix-style-attack-grok-chatgpt-malware)
- [dev.to Abusing AI Chatbot Recommendations](https://dev.to/denniskim/cryptojacking-abusing-ai-chatbot-recommendations-a-new-delivery-vector-beyond-search-poisoning-1cmb)
- [Lasso Security AI Engine Poisoning](https://www.lasso.security/blog/exploiting-geo-to-push-harmful-claims-into-ai-generated-answers)
- [Netcraft AI Summaries](https://www.netcraft.com/blog/threat-actors-are-finding-their-way-into-your-ai-summaries)
- [Digiday AI Result Poisoning](https://digiday.com/marketing/wtf-is-ai-poisoning/)
