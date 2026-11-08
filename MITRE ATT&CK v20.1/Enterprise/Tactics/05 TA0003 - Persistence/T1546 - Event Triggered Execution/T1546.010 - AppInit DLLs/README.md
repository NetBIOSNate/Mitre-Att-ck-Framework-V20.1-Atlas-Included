# T1546.010 - AppInit DLLs

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence and/or elevate privileges by executing malicious content triggered by AppInit DLLs loaded into processes. Dynamic-link libraries (DLLs) that are specified in the <code>AppInit_DLLs</code> value in the Registry keys <code>HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Windows</code> or <code>HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Windows NT\CurrentVersion\Windows</code> are loaded by user32.dll into every process that loads user32.dll. In practice this is nearly every program, since user32.dll is a very common library.(Citation: Elastic Process Injection July 2017)

Similar to Process Injection, these values can be abused to obtain elevated privileges by causing a malicious DLL to be loaded and run in the context of separate processes on the computer.(Citation: AppInit Registry) Malicious AppInit DLLs may also provide persistence by continuously being triggered by API activity. 

The AppInit DLL functionality is disabled in Windows 8 and later versions when secure boot is enabled.(Citation: AppInit Secure Boot)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/010)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0087 - APT39](../../../../Threat%20Intelligence/Groups/G0087%20-%20APT39.md) — [APT39](https://attack.mitre.org/groups/G0087) has used malware to set <code>LoadAppInit_DLLs</code> in the Registry key <code>SOFTWARE\Microsoft\Windows NT\CurrentVersion\Windows</code> in order to establish persistence.(Citation: FBI FLASH APT39 September 2020) [FBI FLASH APT39 September 2020](https://www.iranwatch.org/sites/default/files/public-intelligence-alert.pdf)
- [S0107 - Cherry Picker](../../../../Threat%20Intelligence/Software/Malware/S0107%20-%20Cherry%20Picker.md) — Some variants of [Cherry Picker](https://attack.mitre.org/software/S0107) use AppInit_DLLs to achieve persistence by creating the following Registry key: <code>HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Windows "AppInit_DLLs"="pserver32.dll"</code>(Citation: Trustwave Cherry Picker) [Trustwave Cherry Picker](https://www.trustwave.com/Resources/SpiderLabs-Blog/Shining-the-Spotlight-on-Cherry-Picker-PoS-Malware/)
- [S0458 - Ramsay](../../../../Threat%20Intelligence/Software/Malware/S0458%20-%20Ramsay.md) — [Ramsay](https://attack.mitre.org/software/S0458) can insert itself into the address space of other applications using the AppInit DLL Registry key.(Citation: Eset Ramsay May 2020) [Eset Ramsay May 2020](https://www.welivesecurity.com/2020/05/13/ramsay-cyberespionage-toolkit-airgapped-networks/)
- [S0098 - T9000](../../../../Threat%20Intelligence/Software/Malware/S0098%20-%20T9000.md) — If a victim meets certain criteria, [T9000](https://attack.mitre.org/software/S0098) uses the AppInit_DLL functionality to achieve persistence by ensuring that every user mode process that is spawned will load its malicious DLL, ResN32.dll. It does this by creating the following Registry keys: <code>HKLM\Software\Microsoft\Windows NT\CurrentVersion\Windows\AppInit_DLLs – %APPDATA%\Intel\ResN32.dll</code> and <code>HKLM\Software\Microsoft\Windows NT\CurrentVersion\Windows\LoadAppInit_DLLs – 0x1</code>.(Citation: Palo Alto T9000 Feb 2016) [Palo Alto T9000 Feb 2016](http://researchcenter.paloaltonetworks.com/2016/02/t9000-advanced-modular-backdoor-uses-complex-anti-analysis-techniques/)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Adversaries can install new AppInit DLLs binaries to execute this technique. Identify and block potentially malicious software executed through AppInit DLLs functionality by using application control (Citation: Beechey 2010) tools, like Windows Defender Application Control(Citation: Microsoft Windows Defender Application Control), AppLocker, (Citation: Windows Commands JPCERT) (Citation: NSA MS AppLocker) or Software Restriction Policies (Citation: Corio 2008) where appropriate. (Citation: TechNet Applocker vs SRP) [Beechey 2010](http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599) · [Corio 2008](https://learn.microsoft.com/en-us/previous-versions/technet-magazine/cc510322%28v=msdn.10%29) · [Microsoft Windows Defender Application Control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) · [TechNet Applocker vs SRP](https://technet.microsoft.com/en-us/library/ee791851.aspx) · [NSA MS AppLocker](https://apps.nsa.gov/iaarchive/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm) · [Windows Commands JPCERT](https://blogs.jpcert.or.jp/en/2016/01/windows-commands-abused-by-attackers.html)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Upgrade to Windows 8 or later and enable secure boot.

## Detection strategies

- [DET0557 - Detection Strategy for Event Triggered Execution: AppInit DLLs (Windows)](../../../../Defenses/Detection%20Strategies/DET0557%20-%20Detection%20Strategy%20for%20Event%20Triggered%20Execution%20-%20AppInit%20DLLs%20%28Windows%29.md)

## Sources

- [Elastic Process Injection July 2017](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
- [AppInit Registry](https://support.microsoft.com/en-us/kb/197571)
- [AppInit Secure Boot](https://msdn.microsoft.com/en-us/library/dn280412)
