# T1682 - Query Public AI Services

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may query publicly accessible artificial intelligence (AI) services, such as large language models (LLMs), to support targeting and operations. In addition to searching websites or databases directly (i.e., [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), adversaries may use AI services to synthesize, aggregate, and analyze publicly available information at scale. This may include identifying individuals or organizations to target, researching organizational structures and personnel, identifying technologies used by target organizations, researching business relationships to develop plausible pretexts for [Social Engineering](https://attack.mitre.org/techniques/T1684) approaches, identifying contact information for use in [Phishing](https://attack.mitre.org/techniques/T1566) or [Phishing for Information](https://attack.mitre.org/techniques/T1598), or gathering derogatory or sensitive information about individuals that may be used for extortion or coercion.(Citation: MSFT-AI)(Citation: GTIG AI Threat Tracker)

Information gathered through AI services may be leveraged for other behaviors, such as establishing operational resources (i.e., [Generate Content](https://attack.mitre.org/techniques/T1683) or [Establish Accounts](https://attack.mitre.org/techniques/T1585)). For obtaining access to AI tools and services, see [Artificial Intelligence](https://attack.mitre.org/techniques/T1588/007).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1682)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on designing defenses that are not reliant on atomic indicators.

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary used Anthropic’s Claude Code and OpenAI’s GPT-4.1 AI to conduct operations.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G1044 - APT42](../../../Threat%20Intelligence/Groups/G1044%20-%20APT42.md) — APT42 has leveraged LLMs to search for official emails to build target lists, and conduct reconnaissance on potential business partners.(Citation: GTIG AI Threat Tracker) [GTIG AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used LLMs to identify think tanks, government organizations, and experts to inform targeting for spearphishing campaigns.(Citation: MSFT-AI) [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)

## Detection strategies

- [DET0919 - Detection of Query Public AI Services](../../../Defenses/Detection%20Strategies/DET0919%20-%20Detection%20of%20Query%20Public%20AI%20Services.md)

## Sources

- [GTIG AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/distillation-experimentation-integration-ai-adversarial-use)
- [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)
