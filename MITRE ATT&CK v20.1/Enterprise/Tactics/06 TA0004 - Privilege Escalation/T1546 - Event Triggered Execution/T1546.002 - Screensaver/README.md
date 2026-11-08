# T1546.002 - Screensaver

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence by executing malicious content triggered by user inactivity. Screensavers are programs that execute after a configurable time of user inactivity and consist of Portable Executable (PE) files with a .scr file extension.(Citation: Wikipedia Screensaver) The Windows screensaver application scrnsave.scr is located in <code>C:\Windows\System32\</code>, and <code>C:\Windows\sysWOW64\</code>  on 64-bit Windows systems, along with screensavers included with base Windows installations.

The following screensaver settings are stored in the Registry (<code>HKCU\Control Panel\Desktop\</code>) and could be manipulated to achieve persistence:

* <code>SCRNSAVE.exe</code> - set to malicious PE path
* <code>ScreenSaveActive</code> - set to '1' to enable the screensaver
* <code>ScreenSaverIsSecure</code> - set to '0' to not require a password to unlock
* <code>ScreenSaveTimeout</code> - sets user inactivity timeout before screensaver is executed

Adversaries can use screensaver settings to maintain persistence by setting the screensaver to run malware after a certain timeframe of user inactivity.(Citation: ESET Gazer Aug 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/002)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Use Group Policy to disable screensavers if they are unnecessary.(Citation: TechNet Screensaver GP) [TechNet Screensaver GP](https://technet.microsoft.com/library/cc938799.aspx)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Block .scr files from being executed from non-standard locations.

## Detection strategies

- [DET0154 - Detect Screensaver-Based Persistence via Registry and Execution Chains](../../../../Defenses/Detection%20Strategies/DET0154%20-%20Detect%20Screensaver-Based%20Persistence%20via%20Registry%20and%20Execution%20Chains.md)

## Procedure examples

- [S0168 - Gazer](../../../../Threat%20Intelligence/Software/Malware/S0168%20-%20Gazer.md) — [Gazer](https://attack.mitre.org/software/S0168) can establish persistence through the system screensaver by configuring it to execute the malware.(Citation: ESET Gazer Aug 2017) [ESET Gazer Aug 2017](https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf)

## Sources

- [ESET Gazer Aug 2017](https://www.welivesecurity.com/wp-content/uploads/2017/08/eset-gazer.pdf)
- [Wikipedia Screensaver](https://en.wikipedia.org/wiki/Screensaver)
