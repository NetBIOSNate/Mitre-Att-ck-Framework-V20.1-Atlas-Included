# T1132 - Data Encoding

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries may encode data to make the content of command and control traffic more difficult to detect. Command and control (C2) information can be encoded using a standard data encoding system. Use of data encoding may adhere to existing protocol specifications and includes use of ASCII, Unicode, Base64, MIME, or other binary-to-text and character encoding systems.(Citation: Wikipedia Binary-to-text Encoding)(Citation: Wikipedia Character Encoding) Some data encoding systems may also result in data compression, such as gzip.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1132)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1132.002 - Non-Standard Encoding](T1132.002%20-%20Non-Standard%20Encoding/README.md)
- [T1132.001 - Standard Encoding](T1132.001%20-%20Standard%20Encoding/README.md)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that use network signatures to identify traffic for specific adversary malware can be used to mitigate activity at the network level. Signatures are often for unique indicators within protocols and may be based on the specific obfuscation technique used by a particular adversary or tool, and will likely be different across various malware families and versions. Adversaries will likely change tool C2 signatures over time or construct protocols in such a way as to avoid detection by common defensive tools. (Citation: University of Birmingham C2) [University of Birmingham C2](https://arxiv.org/pdf/1408.1136)

## Procedure examples

- [S0128 - BADNEWS](../../../Threat%20Intelligence/Software/Malware/S0128%20-%20BADNEWS.md) — After encrypting C2 data, [BADNEWS](https://attack.mitre.org/software/S0128) converts it into a hexadecimal representation and then encodes it into base64.(Citation: Forcepoint Monsoon) [Forcepoint Monsoon](https://www.forcepoint.com/sites/default/files/resources/files/forcepoint-security-labs-monsoon-analysis-report.pdf)
- [S9003 - evilginx2](../../../Threat%20Intelligence/Software/Tools/S9003%20-%20evilginx2.md) — [evilginx2](https://attack.mitre.org/software/S9003) can randomly generate and Base64 encode parameters in phishing links to defeat static detection.(Citation: Breakdev Evilginx 2.4 SEP 2020) [Breakdev Evilginx 2.4 SEP 2020](https://breakdev.org/evilginx-2-4-gone-phishing/)
- [S0132 - H1N1](../../../Threat%20Intelligence/Software/Malware/S0132%20-%20H1N1.md) — [H1N1](https://attack.mitre.org/software/S0132) obfuscates C2 traffic with an altered version of base64.(Citation: Cisco H1N1 Part 2) [Cisco H1N1 Part 2](https://web.archive.org/web/20231210122239/https://blogs.cisco.com/security/h1n1-technical-analysis-reveals-new-capabilities-part-2)
- [S9035 - LAMEHUG](../../../Threat%20Intelligence/Software/Malware/S9035%20-%20LAMEHUG.md) — [LAMEHUG](https://attack.mitre.org/software/S9035) can encode queries sent to LLMs.(Citation: Splunk LAMEHUG SEP 2025) [Splunk LAMEHUG SEP 2025](https://www.splunk.com/en_us/blog/security/lamehug-ai-driven-malware-llm-cyber-intrusion-analysis.html)
- [S0362 - Linux Rabbit](../../../Threat%20Intelligence/Software/Malware/S0362%20-%20Linux%20Rabbit.md) — [Linux Rabbit](https://attack.mitre.org/software/S0362) sends the payload from the C2 server as an encoded URL parameter. (Citation: Anomali Linux Rabbit 2018) [Anomali Linux Rabbit 2018](https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat)
- [S0699 - Mythic](../../../Threat%20Intelligence/Software/Tools/S0699%20-%20Mythic.md) — [Mythic](https://attack.mitre.org/software/S0699) provides various transform functions to encode and/or randomize C2 data.(Citation: Mythc Documentation) [Mythc Documentation](https://docs.mythic-c2.net/)
- [S0386 - Ursnif](../../../Threat%20Intelligence/Software/Malware/S0386%20-%20Ursnif.md) — [Ursnif](https://attack.mitre.org/software/S0386) has used encoded data in HTTP URLs for C2.(Citation: ProofPoint Ursnif Aug 2016) [ProofPoint Ursnif Aug 2016](https://www.proofpoint.com/us/threat-insight/post/ursnif-variant-dreambot-adds-tor-functionality)
- [G1047 - Velvet Ant](../../../Threat%20Intelligence/Groups/G1047%20-%20Velvet%20Ant.md) — [Velvet Ant](https://attack.mitre.org/groups/G1047) sent commands to compromised F5 BIG-IP devices in an encoded format requiring a passkey before interpretation and execution.(Citation: Sygnia VelvetAnt 2024A) [Sygnia VelvetAnt 2024A](https://www.sygnia.co/blog/china-nexus-threat-group-velvet-ant/)

## Detection strategies

- [DET0108 - Detection Strategy for Data Encoding in C2 Channels](../../../Defenses/Detection%20Strategies/DET0108%20-%20Detection%20Strategy%20for%20Data%20Encoding%20in%20C2%20Channels.md)

## Sources

- [Wikipedia Binary-to-text Encoding](https://en.wikipedia.org/wiki/Binary-to-text_encoding)
- [Wikipedia Character Encoding](https://en.wikipedia.org/wiki/Character_encoding)
