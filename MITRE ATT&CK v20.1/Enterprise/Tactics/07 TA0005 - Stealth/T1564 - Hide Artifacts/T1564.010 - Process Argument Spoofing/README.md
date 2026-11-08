# T1564.010 - Process Argument Spoofing

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may attempt to hide process command-line arguments by overwriting process memory. Process command-line arguments are stored in the process environment block (PEB), a data structure used by Windows to store various information about/used by a process. The PEB includes the process command-line arguments that are referenced when executing the process. When a process is created, defensive tools/sensors that monitor process creations may retrieve the process arguments from the PEB.(Citation: Microsoft PEB 2021)(Citation: Xpn Argue Like Cobalt 2019)

Adversaries may manipulate a process PEB to evade defenses. For example, [Process Hollowing](https://attack.mitre.org/techniques/T1055/012) can be abused to spawn a process in a suspended state with benign arguments. After the process is spawned and the PEB is initialized (and process information is potentially logged by tools/sensors), adversaries may override the PEB to modify the command-line arguments (ex: using the [Native API](https://attack.mitre.org/techniques/T1106) <code>WriteProcessMemory()</code> function) then resume process execution with malicious arguments.(Citation: Cobalt Strike Arguments 2019)(Citation: Xpn Argue Like Cobalt 2019)(Citation: Nviso Spoof Command Line 2020)

Adversaries may also execute a process with malicious command-line arguments then patch the memory with benign arguments that may bypass subsequent process memory analysis.(Citation: FireEye FiveHands April 2021)

This behavior may also be combined with other tricks (such as [Parent PID Spoofing](https://attack.mitre.org/techniques/T1134/004)) to manipulate or further evade process-based detections.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/010)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can use spoof arguments in spawned processes that execute beacon commands.(Citation: Cobalt Strike Manual 4.3 November 2020) [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf)
- [S0615 - SombRAT](../../../../Threat%20Intelligence/Software/Malware/S0615%20-%20SombRAT.md) — [SombRAT](https://attack.mitre.org/software/S0615) has the ability to modify its process memory to hide process command-line arguments.(Citation: FireEye FiveHands April 2021) [FireEye FiveHands April 2021](https://www.fireeye.com/blog/threat-research/2021/04/unc2447-sombrat-and-fivehands-ransomware-sophisticated-financial-threat.html)

## Detection strategies

- [DET0045 - Detection Strategy for Process Argument Spoofing on Windows](../../../../Defenses/Detection%20Strategies/DET0045%20-%20Detection%20Strategy%20for%20Process%20Argument%20Spoofing%20on%20Windows.md)

## Sources

- [Xpn Argue Like Cobalt 2019](https://blog.xpnsec.com/how-to-argue-like-cobalt-strike/)
- [Nviso Spoof Command Line 2020](https://blog.nviso.eu/2020/02/04/the-return-of-the-spoof-part-2-command-line-spoofing/)
- [FireEye FiveHands April 2021](https://www.fireeye.com/blog/threat-research/2021/04/unc2447-sombrat-and-fivehands-ransomware-sophisticated-financial-threat.html)
- [Microsoft PEB 2021](https://docs.microsoft.com/en-us/windows/win32/api/winternl/ns-winternl-peb)
- [Cobalt Strike Arguments 2019](https://blog.cobaltstrike.com/2019/01/02/cobalt-strike-3-13-why-do-we-argue/)
