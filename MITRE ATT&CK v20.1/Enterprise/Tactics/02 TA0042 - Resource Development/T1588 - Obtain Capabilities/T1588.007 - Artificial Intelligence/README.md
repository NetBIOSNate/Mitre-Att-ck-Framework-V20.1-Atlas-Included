# T1588.007 - Artificial Intelligence

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1588 - Obtain Capabilities](../README.md)

Adversaries may obtain access to generative artificial intelligence (AI) tools, such as large language models (LLMs), to aid various techniques during targeting. These tools may be used to inform, bolster, and enable a variety of malicious tasks, including creating scripts, assisting social engineering, developing payloads, and to [Query Public AI Services](https://attack.mitre.org/techniques/T1682) in support of [Reconnaissance](https://attack.mitre.org/tactics/TA0043).(Citation: MSFT-AI) 

For example, by utilizing a publicly available LLM an adversary is essentially outsourcing or automating certain tasks to the tool. Using AI, the adversary may draft and [Generate Content](https://attack.mitre.org/techniques/T1683) in a variety of written languages to be used in [Phishing](https://attack.mitre.org/techniques/T1566)/[Phishing for Information](https://attack.mitre.org/techniques/T1598) campaigns. The same publicly available tool may further enable vulnerability or other offensive research supporting [Develop Capabilities](https://attack.mitre.org/techniques/T1587). AI tools may also automate technical tasks by generating, refining, or otherwise enhancing (e.g., [Obfuscated Files or Information](https://attack.mitre.org/techniques/T1027)) malicious scripts and payloads.(Citation: OpenAI-CTI) Finally, AI-generated text, images, audio, and video may be used for fraud, [Impersonation](https://attack.mitre.org/techniques/T1684/001), and other malicious activities.(Citation: Google-Vishing24)(Citation: IC3-AI24)(Citation: WSJ-Vishing-AI24)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1588/007)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries generated custom script with an LLM.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary obtained access to Claude Code and OpenAI GPT-4.1 AI in order to facilitate attacks against the victim.(Citation: AI-Mexico-Govt-Breach)(Citation: AI-Mexico-Govt-Compromise) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf) · [AI-Mexico-Govt-Compromise](https://5943619.hs-sites.com/hubfs/116-Whitepapers/dragos-2026-ai-mexico-water-attack-intel-brief.pdf)
- [C0062 - Anthropic AI-orchestrated Campaign](../../../../Threat%20Intelligence/Campaigns/C0062%20-%20Anthropic%20AI-orchestrated%20Campaign.md) — During the [Anthropic AI-orchestrated Campaign](https://attack.mitre.org/campaigns/C0062), the adversary obtained access to Claude Code to support cyber intrusion operations.(Citation: Anthropic AI Orchestrated Campaign NOV 2025) [Anthropic AI Orchestrated Campaign NOV 2025](https://assets.anthropic.com/m/ec212e6566a0d47/original/Disrupting-the-first-reported-AI-orchestrated-cyber-espionage-campaign.pdf)
- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has deployed [LAMEHUG](https://attack.mitre.org/software/S9035) which can can query an LLM to generate and return commands for post compromise activity on targeted systems.(Citation: Nov AI Threat Tracker) [Nov AI Threat Tracker](https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools)
- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has appeared to have used AI to generate images and content to facilitate their campaigns.(Citation: Recorded Future Contagious Inteview BeaverTail InvisibleFerret OtterCookie February 2025) [Recorded Future Contagious Inteview BeaverTail InvisibleFerret OtterCookie February 2025](https://www.recordedfuture.com/research/inside-the-scam-north-koreas-it-worker-threat)
- [S9039 - LazyWiper](../../../../Threat%20Intelligence/Software/Malware/S9039%20-%20LazyWiper.md) — [LazyWiper](https://attack.mitre.org/software/S9039) is believed to have been generated by a large language model (LLM) due to the non-sensical comments in the code.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has appeared to have leveraged AI to assist in malware generation due to coding patterns and modular code organization.(Citation: CheckPoint_NimbusManticore_May2026) [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has used Bland AI to create conversational pathways tailored to specific scenarios during voice phishing attacks.(Citation: ElecticIQ Buyukkaya_ShinyHunters_Sept2025) [ElecticIQ Buyukkaya_ShinyHunters_Sept2025](https://blog.eclecticiq.com/shinyhunters-calling-financially-motivated-data-extortion-group-targeting-enterprise-cloud-applications)

## Detection strategies

- [DET0842 - Detection of Artificial Intelligence](../../../../Defenses/Detection%20Strategies/DET0842%20-%20Detection%20of%20Artificial%20Intelligence.md)

## Sources

- [WSJ-Vishing-AI24](https://www.wsj.com/articles/fraudsters-use-ai-to-mimic-ceos-voice-in-unusual-cybercrime-case-11567157402)
- [Google-Vishing24](https://cloud.google.com/blog/topics/threat-intelligence/ai-powered-voice-spoofing-vishing-attacks)
- [IC3-AI24](https://www.ic3.gov/PSA/2024/PSA241203)
- [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)
- [OpenAI-CTI](https://openai.com/index/disrupting-malicious-uses-of-ai-by-state-affiliated-threat-actors/)
