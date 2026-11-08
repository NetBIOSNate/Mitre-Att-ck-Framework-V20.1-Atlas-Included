# T1546.011 - Application Shimming

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence and/or elevate privileges by executing malicious content triggered by application shims. The Microsoft Windows Application Compatibility Infrastructure/Framework (Application Shim) was created to allow for backward compatibility of software as the operating system codebase changes over time. For example, the application shimming feature allows developers to apply fixes to applications (without rewriting code) that were created for Windows XP so that they will work with Windows 10.(Citation: Elastic Process Injection July 2017)

Within the framework, shims are created to act as a buffer between the program (or more specifically, the Import Address Table) and the Windows OS. When a program is executed, the shim cache is referenced to determine if the program requires the use of the shim database (.sdb). If so, the shim database uses hooking to redirect the code as necessary in order to communicate with the OS. 

A list of all shims currently installed by the default Windows installer (sdbinst.exe) is kept in:

* <code>%WINDIR%\AppPatch\sysmain.sdb</code> and
* <code>hklm\software\microsoft\windows nt\currentversion\appcompatflags\installedsdb</code>

Custom databases are stored in:

* <code>%WINDIR%\AppPatch\custom & %WINDIR%\AppPatch\AppPatch64\Custom</code> and
* <code>hklm\software\microsoft\windows nt\currentversion\appcompatflags\custom</code>

To keep shims secure, Windows designed them to run in user mode so they cannot modify the kernel and you must have administrator privileges to install a shim. However, certain shims can be used to [Bypass User Account Control](https://attack.mitre.org/techniques/T1548/002) (UAC and RedirectEXE), inject DLLs into processes (InjectDLL), disable Data Execution Prevention (DisableNX) and Structure Exception Handling (DisableSEH), and intercept memory addresses (GetProcAddress).

Utilizing these shims may allow an adversary to perform several malicious acts such as elevate privileges, install backdoors, disable defenses like Windows Defender, etc.(Citation: FireEye Application Shimming) Shims can also be abused to establish persistence by continuously being invoked by affected programs.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/011)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0046 - FIN7](../../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — [FIN7](https://attack.mitre.org/groups/G0046) has used application shim databases for persistence.(Citation: FireEye FIN7 Shim Databases) [FireEye FIN7 Shim Databases](https://www.fireeye.com/blog/threat-research/2017/05/fin7-shim-databases-persistence.html)
- [S0517 - Pillowmint](../../../../Threat%20Intelligence/Software/Malware/S0517%20-%20Pillowmint.md) — [Pillowmint](https://attack.mitre.org/software/S0517) has used a malicious shim database to maintain persistence.(Citation: Trustwave Pillowmint June 2020) [Trustwave Pillowmint June 2020](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/pillowmint-fin7s-monkey-thief/)
- [S0461 - SDBbot](../../../../Threat%20Intelligence/Software/Malware/S0461%20-%20SDBbot.md) — [SDBbot](https://attack.mitre.org/software/S0461) has the ability to use application shimming for persistence if it detects it is running as admin on Windows XP or 7, by creating a shim database to patch services.exe.(Citation: Proofpoint TA505 October 2019) [Proofpoint TA505 October 2019](https://www.proofpoint.com/us/threat-insight/post/ta505-distributes-new-sdbbot-remote-access-trojan-get2-downloader)
- [S0444 - ShimRat](../../../../Threat%20Intelligence/Software/Malware/S0444%20-%20ShimRat.md) — [ShimRat](https://attack.mitre.org/software/S0444) has installed shim databases in the <code>AppPatch</code> folder.(Citation: FOX-IT May 2016 Mofang) [FOX-IT May 2016 Mofang](https://foxitsecurity.files.wordpress.com/2016/06/fox-it_mofang_threatreport_tlp-white.pdf)

## Mitigations

- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Microsoft released an optional patch update - KB3045645 - that will remove the "auto-elevate" flag within the sdbinst.exe. This will prevent use of application shimming to bypass UAC.
- [M1052 - User Account Control](../../../../Defenses/Mitigations/M1052%20-%20User%20Account%20Control.md) — Changing UAC settings to "Always Notify" will give the user more visibility when UAC elevation is requested, however, this option will not be popular among users due to the constant UAC interruptions.

## Detection strategies

- [DET0017 - Detection Strategy for Application Shimming via sdbinst.exe and Registry Artifacts (Windows)](../../../../Defenses/Detection%20Strategies/DET0017%20-%20Detection%20Strategy%20for%20Application%20Shimming%20via%20sdbinst.exe%20and%20Registry%20Artifacts%20%28W.md)

## Sources

- [FireEye Application Shimming](http://files.brucon.org/2015/Tomczak_and_Ballenthin_Shims_for_the_Win.pdf)
- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
