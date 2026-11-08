# AML.E0018 - APT28

[MITRE ATLAS](../README.md) / [Entities](README.md)

[APT28](AML.E0018%20-%20APT28.md) is a Russian state-linked threat group attributed to the GRU's military unit 26165. Active since at least 2004, they have targeted government, military, political, and other organizations for espionage. Their access methods include spearphishing, credential harvesting, password spraying, and exploitation of internet-facing applications. They use both custom malware and publicly available tools.

After obtaining access, they collect credentials, emails, and documents, use compromised accounts to access additional resources, and stage data for exfiltration. Their documented techniques include payload obfuscation, persistence mechanisms, and command-and-control communications over web and email protocols.[[group-profile]]

In July 2025, CERT-UA reported malicious emails distributing [LAMEHUG](../Software/Malware/AML.S0015%20-%20LAMEHUG.md) to Ukrainian government bodies and attributed the activity to APT28 with medium confidence. The malware queried Qwen2.5-Coder-32B-Instruct through the Hugging Face API to generate commands for system reconnaissance and document collection, and supported exfiltration through SFTP or HTTP POST. This incorporated language-model-generated commands into the malware's execution workflow. [lamehug-report](https://www.bleepingcomputer.com/news/security/lamehug-malware-uses-ai-llm-to-craft-windows-data-theft-commands-in-real-time/)

**ATT&CK mapping**  [Local ATT&CK G0007](../../Enterprise/Threat%20Intelligence/Groups/G0007%20-%20APT28.md) · [MITRE ATT&CK G0007](https://attack.mitre.org/groups/G0007/)

**Entity type**  Activity Cluster

## Associated entities

- Fancy Bear — CrowdStrike's designation for the Russian state-linked threat actor also tracked as APT28. [crowdstrike-profile](https://www.crowdstrike.com/blog/who-is-fancy-bear/)
- Forest Blizzard — Microsoft's designation, previously STRONTIUM, for activity overlapping with APT28 and Fancy Bear. [microsoft-profile](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)
- UAC-0001 —  [cert-ua](https://cert.gov.ua/article/6284730)

## Uses

- [AML.S0015 - LAMEHUG](../Software/Malware/AML.S0015%20-%20LAMEHUG.md) — [APT28](AML.E0018%20-%20APT28.md) deployed [LAMEHUG](../Software/Malware/AML.S0015%20-%20LAMEHUG.md) to generate commands through a language model for system reconnaissance and document collection, with functionality to exfiltrate collected data using SFTP or HTTP POST. [lamehug-report](https://www.bleepingcomputer.com/news/security/lamehug-malware-uses-ai-llm-to-craft-windows-data-theft-commands-in-real-time/)

## Attributed case studies

- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) (Adversarial Operation)

## References

- [LAMEHUG uses an LLM to generate data-theft commands](https://www.bleepingcomputer.com/news/security/lamehug-malware-uses-ai-llm-to-craft-windows-data-theft-commands-in-real-time/)
- [CERT-UA: UAC-0001 activity using LAMEHUG](https://cert.gov.ua/article/6284730)
- [Who Is FANCY BEAR?](https://www.crowdstrike.com/blog/who-is-fancy-bear/)
- [Staying ahead of threat actors in the age of AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/)

[Official ATLAS record](https://atlas.mitre.org/entities/AML.E0018)
