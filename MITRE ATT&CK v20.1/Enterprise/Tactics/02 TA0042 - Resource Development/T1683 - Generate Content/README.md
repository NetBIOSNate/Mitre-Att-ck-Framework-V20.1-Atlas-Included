# T1683 - Generate Content

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may create or generate content to support targeting and operations. This content may be used to establish personas, impersonate known individuals or organizations, and support [Social Engineering](https://attack.mitre.org/techniques/T1684), fraud, or influence activities. Written materials, audio, images, video, or other media may be developed and tailored to the target and objective.(Citation: IBM AI-Generated Content)

Content development may occur prior to or during an operation. Adversaries may develop or generate content in-house, source it through third parties, or produce it using AI-assisted tools. Adversaries may use AI to research targets, develop pretexts, and better understand the organizations and individuals they intend to target or deceive prior to generating content (i.e., [Query Public AI Services](https://attack.mitre.org/techniques/T1682)); for obtaining access to AI tools used in content generation, see [Artificial Intelligence](https://attack.mitre.org/techniques/T1588/007). 

Content may be leveraged in support of techniques such as [Phishing](https://attack.mitre.org/techniques/T1566), [Phishing for Information](https://attack.mitre.org/techniques/T1598), [Social Engineering](https://attack.mitre.org/techniques/T1684), [Financial Theft](https://attack.mitre.org/techniques/T1657), or [Establish Accounts](https://attack.mitre.org/techniques/T1585). Generated or developed content does not include malicious code or scripts (i.e., [Develop Capabilities](https://attack.mitre.org/techniques/T1587) and [Artificial Intelligence](https://attack.mitre.org/techniques/T1588/007)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1683)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1683.002 - Audio-Visual Content](T1683.002%20-%20Audio-Visual%20Content/README.md)
- [T1683.001 - Written Content](T1683.001%20-%20Written%20Content/README.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on designing defenses that are not reliant on atomic indicators.

## Detection strategies

- [DET0916 - Detection of Generate Content](../../../Defenses/Detection%20Strategies/DET0916%20-%20Detection%20of%20Generate%20Content.md)

## Procedure examples

- [C0062 - Anthropic AI-orchestrated Campaign](../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary utilized Claude Code to automatically generate comprehensive documentation throughout the phases of the attack, including discovered services, harvested credentials, sensitive data, exploitation techniques, and complete attack progression.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
- [S9045 - BACKUPOSINT v9.0 APEX PREDATOR](../../../Threat%20Intelligence/Software/Malware/S9045%20-%20BACKUPOSINT%20v9.0%20APEX%20PREDATOR.md) — [BACKUPOSINT v9.0 APEX PREDATOR](https://attack.mitre.org/software/S9045) has created a skills file titled `AI LATERAL_SUGGESTIONS.md` that included tables mapped with harvested credentials with potential victim internal servers.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)

## Sources

- [IBM AI-Generated Content](https://www.ibm.com/think/insights/ai-generated-content)
