# AML.T0037 - Data from Local System

[MITRE ATLAS](../../../README.md) / [AML.TA0009 - Collection](../README.md)

Adversaries may search local system sources, such as file systems and configuration files or local databases, to find files of interest and sensitive data prior to Exfiltration.

This can include basic fingerprinting information and sensitive data such as ssh keys.

**Tactics**  [AML.TA0009 - Collection](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1005](../../../../Enterprise/Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md) · [MITRE ATT&CK T1005](https://attack.mitre.org/techniques/T1005/)

## Case studies

- [AML.CS0015 - Compromised PyTorch Dependency Chain](../../../Case%20Studies/Incidents/AML.CS0015%20-%20Compromised%20PyTorch%20Dependency%20Chain.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0015%20-%20Compromised%20PyTorch%20Dependency%20Chain.md#step-s01)
- [AML.CS0043 - Malware Prototype with Embedded Prompt Injection](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md#step-s06)
- [AML.CS0044 - LAMEHUG: Malware Leveraging Dynamic AI-Generated Commands](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md) · [S06](../../../Case%20Studies/Incidents/AML.CS0044%20-%20LAMEHUG%20-%20Malware%20Leveraging%20Dynamic%20AI-Generated%20Commands.md#step-s06)
- [AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md#step-s06)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S20](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s20)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S18](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s18)

## Software implementations

- [AML.S0004 - torchtriton](../../../Software/Malware/AML.S0004%20-%20torchtriton.md) — [torchtriton](../../../Software/Malware/AML.S0004%20-%20torchtriton.md) collected the hostname, username, working directory, nameserver configuration, and environment variables. It also read system files, Git configuration, SSH files, and up to 1,000 files from the user's home directory, with file collection limited to files smaller than 99,999 bytes. [source-1](https://pytorch.org/blog/compromised-nightly-dependency/)
- [AML.S0015 - LAMEHUG](../../../Software/Malware/AML.S0015%20-%20LAMEHUG.md) — [LAMEHUG](../../../Software/Malware/AML.S0015%20-%20LAMEHUG.md) uses generated commands to collect system information into info.txt and recursively search the Documents, Desktop, and Downloads directories for documents. [source-1](https://www.bleepingcomputer.com/news/security/lamehug-malware-uses-ai-llm-to-craft-windows-data-theft-commands-in-real-time/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0037)
