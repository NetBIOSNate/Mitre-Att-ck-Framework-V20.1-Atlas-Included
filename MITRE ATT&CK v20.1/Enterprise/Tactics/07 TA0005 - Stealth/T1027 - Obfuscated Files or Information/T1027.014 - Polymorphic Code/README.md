# T1027.014 - Polymorphic Code

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may utilize polymorphic code (also known as metamorphic or mutating code) to evade detection. Polymorphic code is a type of software capable of changing its runtime footprint during code execution.(Citation: polymorphic-blackberry) With each execution of the software, the code is mutated into a different version of itself that achieves the same purpose or objective as the original. This functionality enables the malware to evade traditional signature-based defenses, such as antivirus and antimalware tools.(Citation: polymorphic-sentinelone) 
Other obfuscation techniques can be used in conjunction with polymorphic code to accomplish the intended effects, including using mutation engines to conduct actions such as [Software Packing](https://attack.mitre.org/techniques/T1027/002), [Command Obfuscation](https://attack.mitre.org/techniques/T1027/010), or [Encrypted/Encoded File](https://attack.mitre.org/techniques/T1027/013).(Citation: polymorphic-linkedin)(Citation: polymorphic-medium)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/014)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1049 - Antivirus/Antimalware](../../../../Defenses/Mitigations/M1049%20-%20Antivirus%20-%20Antimalware.md) — Anti-virus can be used to automatically detect and quarantine suspicious files. Employment of advanced anti-malware techniques that make use of technologies like machine learning and behavior-based mechanisms to conduct signature-less malware detection will also be more effective than traditional indicator-based detection methods.
- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10+, enable Attack Surface Reduction (ASR) rules to prevent execution of potentially obfuscated payloads

## Detection strategies

- [DET0324 - Detection Strategy for Polymorphic Code Mutation and Execution](../../../../Defenses/Detection%20Strategies/DET0324%20-%20Detection%20Strategy%20for%20Polymorphic%20Code%20Mutation%20and%20Execution.md)

## Procedure examples

- [S0574 - BendyBear](../../../../Threat%20Intelligence/Software/Malware/S0574%20-%20BendyBear.md) — BendyBear changes its runtime footprint during code execution to evade signature-based defenses.(Citation: Unit42 BendyBear Feb 2021) [Unit42 BendyBear Feb 2021](https://unit42.paloaltonetworks.com/bendybear-shellcode-blacktech/)

## Sources

- [polymorphic-blackberry](https://www.blackberry.com/us/en/solutions/endpoint-security/ransomware-protection/polymorphic-malware)
- [polymorphic-sentinelone](https://www.sentinelone.com/cybersecurity-101/threat-intelligence/what-is-polymorphic-malware)
- [polymorphic-medium](https://medium.com/@shellseekerscyber/explainer-packed-malware-16f09cc75035)
- [polymorphic-linkedin](https://www.linkedin.com/pulse/techniques-concealing-malware-hindering-analysis-packing-akshay-unijc)
