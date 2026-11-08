# T1631 - Process Injection

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may inject code into processes in order to evade process-based defenses or even elevate privileges. Process injection is a method of executing arbitrary code in the address space of a separate live process. Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via process injection may also evade detection from security products since the execution is masked under a legitimate process. 

Both Android and iOS have no legitimate way to achieve process injection. The only way this is possible is by abusing existing root access or exploiting a vulnerability.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1631)

**Tactics**  [Privilege Escalation](../../04%20TA0029%20-%20Privilege%20Escalation/README.md), [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1631.001 - Ptrace System Calls](T1631.001%20-%20Ptrace%20System%20Calls/README.md)

## Procedure examples

- [S1208 - FjordPhantom](../../../Threat%20Intelligence/Software/Malware/S1208%20-%20FjordPhantom.md) — [FjordPhantom](https://attack.mitre.org/software/S1208) has injected malicious code and a hooking framework through a virtualization solution, i.e. [Virtualization Solution](https://attack.mitre.org/techniques/T1670), into the process of the hosted application.(Citation: Promon FjordPhantom Oct2024) [Promon FjordPhantom Oct2024](https://promon.io/security-news/fjordphantom-android-malware)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) injects libcynject.dylib into the SpringBoard process to enable audio/video recording.(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/)

## Detection strategies

- [DET0632 - Detection of Process Injection](../../../Defenses/Detection%20Strategies/DET0632%20-%20Detection%20of%20Process%20Injection.md)
