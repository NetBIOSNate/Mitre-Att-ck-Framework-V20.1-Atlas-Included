# T1027.008 - Stripped Payloads

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may attempt to make a payload difficult to analyze by removing symbols, strings, and other human readable information. Scripts and executables may contain variable names and other strings that help developers document code functionality. Symbols are often created by an operating system’s `linker` when executable payloads are compiled. Reverse engineers use these symbols and strings to analyze code and to identify functionality in payloads.(Citation: Mandiant golang stripped binaries explanation)(Citation: intezer stripped binaries elf files 2018)

Adversaries may use stripped payloads in order to make malware analysis more difficult. For example, compilers and other tools may provide features to remove or obfuscate strings and symbols. Adversaries have also used stripped payload formats, such as run-only AppleScripts, a compiled and stripped version of [AppleScript](https://attack.mitre.org/techniques/T1059/002), to evade detection and analysis. The lack of human-readable information may directly hinder detection and analysis of payloads.(Citation: SentinelLabs reversing run-only applescripts 2021)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/008)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1153 - Cuckoo Stealer](../../../../Threat%20Intelligence/Software/Malware/S1153%20-%20Cuckoo%20Stealer.md) — [Cuckoo Stealer](https://attack.mitre.org/software/S1153) is a stripped binary payload.(Citation: Kandji Cuckoo April 2024) (Citation: SentinelOne Cuckoo Stealer May 2024) [Kandji Cuckoo April 2024](https://www.kandji.io/blog/malware-cuckoo-infostealer-spyware) · [SentinelOne Cuckoo Stealer May 2024](https://www.sentinelone.com/blog/macos-cuckoo-stealer-ensuring-detection-and-defense-as-new-samples-rapidly-emerge/)
- [S1048 - macOS.OSAMiner](../../../../Threat%20Intelligence/Software/Malware/S1048%20-%20macOS.OSAMiner.md) — [macOS.OSAMiner](https://attack.mitre.org/software/S1048) has used run-only Applescripts, a compiled and stripped version of [AppleScript](https://attack.mitre.org/techniques/T1059/002), to remove human readable indicators to evade detection.(Citation: SentinelLabs reversing run-only applescripts 2021) [SentinelLabs reversing run-only applescripts 2021](https://www.sentinelone.com/labs/fade-dead-adventures-in-reversing-malicious-run-only-applescripts/)

## Detection strategies

- [DET0019 - Detection Strategy for Stripped Payloads Across Platforms](../../../../Defenses/Detection%20Strategies/DET0019%20-%20Detection%20Strategy%20for%20Stripped%20Payloads%20Across%20Platforms.md)

## Sources

- [intezer stripped binaries elf files 2018](https://www.intezer.com/blog/malware-analysis/executable-linkable-format-101-part-2-symbols/)
- [SentinelLabs reversing run-only applescripts 2021](https://www.sentinelone.com/labs/fade-dead-adventures-in-reversing-malicious-run-only-applescripts/)
- [Mandiant golang stripped binaries explanation](https://www.mandiant.com/resources/blog/golang-internals-symbol-recovery)
