# T1574.009 - Path Interception by Unquoted Path

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1574 - Hijack Execution Flow](../README.md)

Adversaries may execute their own malicious payloads by hijacking vulnerable file path references. Adversaries can take advantage of paths that lack surrounding quotations by placing an executable in a higher level directory within the path, so that Windows will choose the adversary's executable to launch.

Service paths(Citation: Microsoft CurrentControlSet Services) and shortcut paths may also be vulnerable to path interception if the path has one or more spaces and is not surrounded by quotation marks (e.g., <code>C:\unsafe path with space\program.exe</code> vs. <code>"C:\safe path with space\program.exe"</code>).(Citation: Help eliminate unquoted path) (stored in Windows Registry keys) An adversary can place an executable in a higher level directory of the path, and Windows will resolve that executable instead of the intended executable. For example, if the path in a shortcut is <code>C:\program files\myapp.exe</code>, an adversary may create a program at <code>C:\program.exe</code> that will be run instead of the intended program.(Citation: Windows Unquoted Services)(Citation: Windows Privilege Escalation Guide)

This technique can be used for persistence if executables are called on a regular basis, as well as privilege escalation if intercepted executables are started by a higher privileged process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1574/009)

**Tactics**  [Execution](../../../04%20TA0002%20-%20Execution/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Find and eliminate path interception weaknesses in program configuration files, scripts, the PATH environment variable, services, and in shortcuts by surrounding PATH variables with quotation marks when functions allow for them. Be aware of the search order Windows uses for executing or loading binaries and use fully qualified paths wherever appropriate. Clean up old Windows Registry keys when software is uninstalled to avoid keys with no associated legitimate binaries. Periodically search for and correct or report path interception weaknesses on systems that may have been introduced using custom or available tools that report software using insecure path configurations.(Citation: Microsoft CreateProcess)(Citation: Microsoft Dynamic-Link Library Security)(Citation: Vulnerability and Exploit Detector) [Vulnerability and Exploit Detector](https://skanthak.homepage.t-online.de/sentinel.html) · [Microsoft CreateProcess](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessa) · [Microsoft Dynamic-Link Library Security](https://docs.microsoft.com/en-us/windows/win32/dlls/dynamic-link-library-security?redirectedfrom=MSDN)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Adversaries will likely need to place new binaries in locations to be executed through this weakness. Identify and block potentially malicious software executed path interception by using application control tools, like Windows Defender Application Control, AppLocker, or Software Restriction Policies where appropriate.(Citation: SANS Application Whitelisting)(Citation: Microsoft Windows Defender Application Control)(Citation: Windows Commands JPCERT)(Citation: NSA MS AppLocker)(Citation: Microsoft Application Lockdown)(Citation: Microsoft Using Software Restriction ) [SANS Application Whitelisting](https://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599) · [Microsoft Windows Defender Application Control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) · [Windows Commands JPCERT](https://blogs.jpcert.or.jp/en/2016/01/windows-commands-abused-by-attackers.html) · [NSA MS AppLocker](https://apps.nsa.gov/iaarchive/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm) · [Microsoft Application Lockdown](https://docs.microsoft.com/en-us/previous-versions/technet-magazine/cc510322%28v=msdn.10%29?redirectedfrom=MSDN) · [Microsoft Using Software Restriction ](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/ee791851%28v=ws.11%29?redirectedfrom=MSDN)
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure that proper permissions and directory access control are set to deny users the ability to write files to the top-level directory <code>C:</code> and system directories, such as <code>C:\Windows\</code>, to reduce places where malicious files could be placed for execution. Require that all executables be placed in write-protected directories.

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) contains modules that can discover and exploit unquoted path vulnerabilities.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0194 - PowerSploit](../../../../Threat%20Intelligence/Software/Tools/S0194%20-%20PowerSploit.md) — [PowerSploit](https://attack.mitre.org/software/S0194) contains a collection of Privesc-PowerUp modules that can discover and exploit unquoted path vulnerabilities.(Citation: GitHub PowerSploit May 2012)(Citation: PowerSploit Documentation) [GitHub PowerSploit May 2012](https://github.com/PowerShellMafia/PowerSploit) · [PowerSploit Documentation](http://powersploit.readthedocs.io)

## Detection strategies

- [DET0064 - Detection Strategy for Hijack Execution Flow through Path Interception by Unquoted Path](../../../../Defenses/Detection%20Strategies/DET0064%20-%20Detection%20Strategy%20for%20Hijack%20Execution%20Flow%20through%20Path%20Interception%20by%20Unquoted%20Pa.md)

## Sources

- [Windows Privilege Escalation Guide](https://www.absolomb.com/2018-01-26-Windows-Privilege-Escalation-Guide/)
- [Windows Unquoted Services](https://securityboulevard.com/2018/04/windows-privilege-escalation-unquoted-services/)
- [Help eliminate unquoted path](https://isc.sans.edu/diary/Help+eliminate+unquoted+path+vulnerabilities/14464)
- [Microsoft CurrentControlSet Services](https://docs.microsoft.com/en-us/windows-hardware/drivers/install/hklm-system-currentcontrolset-services-registry-tree)
