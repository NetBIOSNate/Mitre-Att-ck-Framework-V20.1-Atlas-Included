# T1633 - Virtualization/Sandbox Evasion

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may employ various means to detect and avoid virtualization and analysis environments. This may include changing behaviors after checking for the presence of artifacts indicative of a virtual machine environment (VME) or sandbox. If the adversary detects a VME, they may alter their malware’s behavior to disengage from the victim or conceal the core functions of the payload. They may also search for VME artifacts before dropping further payloads. Adversaries may use the information learned from [Virtualization/Sandbox Evasion](https://attack.mitre.org/techniques/T1633) during automated discovery to shape follow-on behaviors. 

Adversaries may use several methods to accomplish [Virtualization/Sandbox Evasion](https://attack.mitre.org/techniques/T1633) such as checking for system artifacts associated with analysis or virtualization. Adversaries may also check for legitimate user activity to help determine if it is in an analysis environment.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1633)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1633.001 - System Checks](T1633.001%20-%20System%20Checks/README.md)

## Detection strategies

- [DET0616 - Detection of Virtualization/Sandbox Evasion](../../../Defenses/Detection%20Strategies/DET0616%20-%20Detection%20of%20Virtualization%20-%20Sandbox%20Evasion.md)

## Procedure examples

- [S1061 - AbstractEmu](../../../Threat%20Intelligence/Software/Malware/S1061%20-%20AbstractEmu.md) — [AbstractEmu](https://attack.mitre.org/software/S1061) has used code abstraction and anti-emulation checks to potentially avoid running while under analysis.(Citation: lookout_abstractemu_1021) [lookout_abstractemu_1021](https://www.lookout.com/blog/lookout-discovers-global-rooting-malware-campaign)
- [S9048 - KoSpy](../../../Threat%20Intelligence/Software/Malware/S9048%20-%20KoSpy.md) — [KoSpy](https://attack.mitre.org/software/S9048) has checked if the device is not an emulator and if the current date is past the hardcoded activation date.(Citation: Lookout_KoSpy_March2025) [Lookout_KoSpy_March2025](https://security.lookout.com/threat-intelligence/article/lookout-discovers-new-spyware-by-north-korean-apt37)
- [S1195 - SpyC23](../../../Threat%20Intelligence/Software/Malware/S1195%20-%20SpyC23.md) — [SpyC23](https://attack.mitre.org/software/S1195) has obfuscated code and anti-virtualization techniques to hinder analysis.(Citation: SentinelLabs AridViper 2023) [SentinelLabs AridViper 2023](https://www.sentinelone.com/labs/arid-viper-apts-nest-of-spyc23-malware-continues-to-target-android-devices/)
