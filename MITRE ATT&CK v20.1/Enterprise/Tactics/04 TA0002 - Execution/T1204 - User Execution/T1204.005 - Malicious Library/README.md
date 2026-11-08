# T1204.005 - Malicious Library

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1204 - User Execution](../README.md)

Adversaries may rely on a user installing a malicious library to facilitate execution. Threat actors may [Upload Malware](https://attack.mitre.org/techniques/T1608/001) to package managers such as NPM and PyPi, as well as to public code repositories such as GitHub. Users may install libraries without realizing they are malicious, thus bypassing techniques that specifically achieve Initial Access. This can lead to the execution of malicious code, such as code that establishes persistence, steals data, or mines cryptocurrency.(Citation: Datadog Security Labs Malicious PyPi Packages 2024)(Citation: Fortinet Malicious NPM Packages 2023)

In some cases, threat actors may compromise and backdoor existing popular libraries (i.e., [Compromise Software Dependencies and Development Tools](https://attack.mitre.org/techniques/T1195/001)). Alternatively, they may create entirely new packages and leverage behaviors such as typosquatting to encourage users to install them.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1204/005)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has relied on users to install a malicious library from a code repository to infect the victim's device and has led to additional payload distribution and theft of sensitive data.(Citation: Sentinel One Contagious Interview ClickFix September 2025)(Citation: Validin Contagious Interview North Korea ClickFix January 2025)(Citation: Esentire ContagiousInterview BeaverTail InvisibleFerret November 2024)(Citation: Socket Contagious Interview NPM April 2025)(Citation: Socket BeaverTail XORIndex HexEval Contagious Interview July 2025)(Citation: Socket HexEval BeaverTail Contagious Interview June 2025)(Citation: ESET Contagious Interview BeaverTail InvisibleFerret February 2025)(Citation: Securonix Contagious Interview DEVPOPPER April 2024)(Citation: Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024)(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023) [Sentinel One Contagious Interview ClickFix September 2025](https://www.sentinelone.com/labs/contagious-interview-threat-actors-scout-cyber-intel-platforms-reveal-plans-and-ops/) · [Validin Contagious Interview North Korea ClickFix January 2025](https://www.validin.com/blog/inoculating_contagious_interview_with_validin/) · [Esentire ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.esentire.com/blog/bored-beavertail-invisibleferret-yacht-club-a-lazarus-lure-pt-2) · [Socket Contagious Interview NPM April 2025](https://socket.dev/blog/lazarus-expands-malicious-npm-campaign-11-new-packages-add-malware-loaders-and-bitbucket) · [Socket BeaverTail XORIndex HexEval Contagious Interview July 2025](https://socket.dev/blog/contagious-interview-campaign-escalates-67-malicious-npm-packages) · [Socket HexEval BeaverTail Contagious Interview June 2025](https://socket.dev/blog/north-korean-contagious-interview-campaign-drops-35-new-malicious-npm-packages) · [ESET Contagious Interview BeaverTail InvisibleFerret February 2025](https://www.welivesecurity.com/en/eset-research/deceptivedevelopment-targets-freelance-developers/) · [Securonix Contagious Interview DEVPOPPER April 2024](https://www.securonix.com/blog/analysis-of-devpopper-new-attack-campaign-targeting-software-developers-likely-associated-with-north-korean-threat-actors/) · [Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.zscaler.com/blogs/security-research/pyongyang-your-payroll-rise-north-korean-remote-workers-west) · [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/)

## Mitigations

- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Where possible, consider requiring developers to pull from internal repositories containing verified and approved packages rather than from external ones.
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network prevention intrusion systems and systems designed to scan and remove malicious downloads can be used to block activity.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train developers to be aware of the existence of malicious libraries and how to avoid installing them.

## Detection strategies

- [DET0252 - User-Initiated Malicious Library Installation via Package Manager (T1204.005)](../../../../Defenses/Detection%20Strategies/DET0252%20-%20User-Initiated%20Malicious%20Library%20Installation%20via%20Package%20Manager%20%28T1204.005%29.md)

## Sources

- [Datadog Security Labs Malicious PyPi Packages 2024](https://securitylabs.datadoghq.com/articles/malicious-pypi-package-targeting-highly-specific-macos-machines/)
- [Fortinet Malicious NPM Packages 2023](https://www.fortinet.com/blog/threat-research/malicious-packages-hiddin-in-npm)
