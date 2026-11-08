# T1546.012 - Image File Execution Options Injection

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence and/or elevate privileges by executing malicious content triggered by Image File Execution Options (IFEO) debuggers. IFEOs enable a developer to attach a debugger to an application. When a process is created, a debugger present in an application’s IFEO will be prepended to the application’s name, effectively launching the new process under the debugger (e.g., <code>C:\dbg\ntsd.exe -g  notepad.exe</code>).(Citation: Microsoft Dev Blog IFEO Mar 2010)

IFEOs can be set directly via the Registry or in Global Flags via the GFlags tool.(Citation: Microsoft GFlags Mar 2017) IFEOs are represented as <code>Debugger</code> values in the Registry under <code>HKLM\SOFTWARE{\Wow6432Node}\Microsoft\Windows NT\CurrentVersion\Image File Execution Options\<executable></code> where <code>&lt;executable&gt;</code> is the binary on which the debugger is attached.(Citation: Microsoft Dev Blog IFEO Mar 2010)

IFEOs can also enable an arbitrary monitor program to be launched when a specified program silently exits (i.e. is prematurely terminated by itself or a second, non kernel-mode process).(Citation: Microsoft Silent Process Exit NOV 2017)(Citation: Oddvar Moe IFEO APR 2018) Similar to debuggers, silent exit monitoring can be enabled through GFlags and/or by directly modifying IFEO and silent process exit Registry values in <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit\</code>.(Citation: Microsoft Silent Process Exit NOV 2017)(Citation: Oddvar Moe IFEO APR 2018)

Similar to [Accessibility Features](https://attack.mitre.org/techniques/T1546/008), on Windows Vista and later as well as Windows Server 2008 and later, a Registry key may be modified that configures "cmd.exe," or another program that provides backdoor access, as a "debugger" for an accessibility program (ex: utilman.exe). After the Registry is modified, pressing the appropriate key combination at the login screen while at the keyboard or when connected with [Remote Desktop Protocol](https://attack.mitre.org/techniques/T1021/001) will cause the "debugger" program to be executed with SYSTEM privileges.(Citation: Tilbury 2014)

Similar to [Process Injection](https://attack.mitre.org/techniques/T1055), these values may also be abused to obtain privilege escalation by causing a malicious executable to be loaded and run in the context of separate processes on the computer.(Citation: Elastic Process Injection July 2017) Installing IFEO mechanisms may also provide Persistence via continuous triggered invocation.

Malware may also use IFEO to impair defenses by registering invalid debuggers that redirect and effectively disable various system and security applications.(Citation: FSecure Hupigon)(Citation: Symantec Ushedix June 2008)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/012)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0032 - C0032](../../../../Threat%20Intelligence/Campaigns/C0032%20-%20C0032.md) — During the [C0032](https://attack.mitre.org/campaigns/C0032) campaign, [TEMP.Veles](https://attack.mitre.org/groups/G0088) modified and added entries within <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options</code> to maintain persistence.(Citation: FireEye TRITON 2019) [FireEye TRITON 2019](https://www.fireeye.com/blog/threat-research/2019/04/triton-actor-ttp-profile-custom-attack-tools-detections.html)
- [S0461 - SDBbot](../../../../Threat%20Intelligence/Software/Malware/S0461%20-%20SDBbot.md) — [SDBbot](https://attack.mitre.org/software/S0461) has the ability to use image file execution options for persistence if it detects it is running with admin privileges on a Windows version newer than Windows 7.(Citation: Proofpoint TA505 October 2019) [Proofpoint TA505 October 2019](https://www.proofpoint.com/us/threat-insight/post/ta505-distributes-new-sdbbot-remote-access-trojan-get2-downloader)
- [S0559 - SUNBURST](../../../../Threat%20Intelligence/Software/Malware/S0559%20-%20SUNBURST.md) — [SUNBURST](https://attack.mitre.org/software/S0559) created an Image File Execution Options (IFEO) Debugger registry value for the process <code>dllhost.exe</code> to trigger the installation of [Cobalt Strike](https://attack.mitre.org/software/S0154).(Citation: Microsoft Deep Dive Solorigate January 2021) [Microsoft Deep Dive Solorigate January 2021](https://www.microsoft.com/security/blog/2021/01/20/deep-dive-into-the-solorigate-second-stage-activation-from-sunburst-to-teardrop-and-raindrop/)

## Detection strategies

- [DET0422 - Detection Strategy for IFEO Injection on Windows](../../../../Defenses/Detection%20Strategies/DET0422%20-%20Detection%20Strategy%20for%20IFEO%20Injection%20on%20Windows.md)

## Sources

- [FSecure Hupigon](https://www.f-secure.com/v-descs/backdoor_w32_hupigon_emv.shtml)
- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
- [Microsoft Silent Process Exit NOV 2017](https://docs.microsoft.com/windows-hardware/drivers/debugger/registry-entries-for-silent-process-exit)
- [Microsoft GFlags Mar 2017](https://docs.microsoft.com/windows-hardware/drivers/debugger/gflags-overview)
- [Oddvar Moe IFEO APR 2018](https://oddvar.moe/2018/04/10/persistence-using-globalflags-in-image-file-execution-options-hidden-from-autoruns-exe/)
- [Microsoft Dev Blog IFEO Mar 2010](https://blogs.msdn.microsoft.com/mithuns/2010/03/24/image-file-execution-options-ifeo/)
- [Symantec Ushedix June 2008](https://www.symantec.com/security_response/writeup.jsp?docid=2008-062807-2501-99&tabid=2)
- [Tilbury 2014](https://web.archive.org/web/20200730053039/https://www.crowdstrike.com/blog/registry-analysis-with-crowdresponse/)
