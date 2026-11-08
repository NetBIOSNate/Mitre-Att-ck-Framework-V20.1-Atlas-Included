# T1574.008 - Path Interception by Search Order Hijacking

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1574 - Hijack Execution Flow](../README.md)

Adversaries may execute their own malicious payloads by hijacking the search order used to load other programs. Because some programs do not call other programs using the full path, adversaries may place their own file in the directory where the calling program is located, causing the operating system to launch their malicious software at the request of the calling program.

Search order hijacking occurs when an adversary abuses the order in which Windows searches for programs that are not given a path. Unlike [DLL](https://attack.mitre.org/techniques/T1574/001) search order hijacking, the search order differs depending on the method that is used to execute the program.(Citation: Microsoft CreateProcess)(Citation: Windows NT Command Shell)(Citation: Microsoft WinExec) However, it is common for Windows to search in the directory of the initiating program before searching through the Windows system directory. An adversary who finds a program vulnerable to search order hijacking (i.e., a program that does not specify the path to an executable) may take advantage of this vulnerability by creating a program named after the improperly specified program and placing it within the initiating program's directory.

For example, "example.exe" runs "cmd.exe" with the command-line argument <code>net user</code>. An adversary may place a program called "net.exe" within the same directory as example.exe, "net.exe" will be run instead of the Windows system utility net. In addition, if an adversary places a program called "net.com" in the same directory as "net.exe", then <code>cmd.exe /C net user</code> will execute "net.com" instead of "net.exe" due to the order of executable extensions defined under PATHEXT.(Citation: Microsoft Environment Property)

Search order hijacking is also a common practice for hijacking DLL loads and is covered in [DLL](https://attack.mitre.org/techniques/T1574/001).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1574/008)

**Tactics**  [Execution](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0564 - Detection Strategy for Hijack Execution Flow using Path Interception by Search Order Hijacking](../../../../Defenses/Detection%20Strategies/DET0564%20-%20Detection%20Strategy%20for%20Hijack%20Execution%20Flow%20using%20Path%20Interception%20by%20Search%20Order.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Find and eliminate path interception weaknesses in program configuration files, scripts, the PATH environment variable, services, and in shortcuts by surrounding PATH variables with quotation marks when functions allow for them. Be aware of the search order Windows uses for executing or loading binaries and use fully qualified paths wherever appropriate. Clean up old Windows Registry keys when software is uninstalled to avoid keys with no associated legitimate binaries. Periodically search for and correct or report path interception weaknesses on systems that may have been introduced using custom or available tools that report software using insecure path configurations.(Citation: Microsoft CreateProcess)(Citation: Microsoft Dynamic-Link Library Security)(Citation: Vulnerability and Exploit Detector) [Vulnerability and Exploit Detector](https://skanthak.homepage.t-online.de/sentinel.html) · [Microsoft CreateProcess](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessa) · [Microsoft Dynamic-Link Library Security](https://docs.microsoft.com/en-us/windows/win32/dlls/dynamic-link-library-security?redirectedfrom=MSDN)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Adversaries will likely need to place new binaries in locations to be executed through this weakness. Identify and block potentially malicious software executed path interception by using application control tools, like Windows Defender Application Control, AppLocker, or Software Restriction Policies where appropriate.(Citation: SANS Application Whitelisting)(Citation: Microsoft Windows Defender Application Control)(Citation: Windows Commands JPCERT)(Citation: NSA MS AppLocker)(Citation: Microsoft Application Lockdown)(Citation: Microsoft Using Software Restriction ) [SANS Application Whitelisting](https://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599) · [Microsoft Windows Defender Application Control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) · [Windows Commands JPCERT](https://blogs.jpcert.or.jp/en/2016/01/windows-commands-abused-by-attackers.html) · [NSA MS AppLocker](https://apps.nsa.gov/iaarchive/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm) · [Microsoft Application Lockdown](https://docs.microsoft.com/en-us/previous-versions/technet-magazine/cc510322%28v=msdn.10%29?redirectedfrom=MSDN) · [Microsoft Using Software Restriction ](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/ee791851%28v=ws.11%29?redirectedfrom=MSDN)
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure that proper permissions and directory access control are set to deny users the ability to write files to the top-level directory <code>C:</code> and system directories, such as <code>C:\Windows\</code>, to reduce places where malicious files could be placed for execution. Require that all executables be placed in write-protected directories.

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) contains modules that can discover and exploit search order hijacking vulnerabilities.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0194 - PowerSploit](../../../../Threat%20Intelligence/Software/Tools/S0194%20-%20PowerSploit.md) — [PowerSploit](https://attack.mitre.org/software/S0194) contains a collection of Privesc-PowerUp modules that can discover and exploit search order hijacking vulnerabilities.(Citation: GitHub PowerSploit May 2012)(Citation: PowerSploit Documentation) [GitHub PowerSploit May 2012](https://github.com/PowerShellMafia/PowerSploit) · [PowerSploit Documentation](http://powersploit.readthedocs.io)

## Sources

- [Microsoft Environment Property](https://docs.microsoft.com/en-us/previous-versions//fd7hxfdd%28v=vs.85%29?redirectedfrom=MSDN)
- [Microsoft CreateProcess](https://learn.microsoft.com/en-us/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessa)
- [Microsoft WinExec](https://learn.microsoft.com/en-us/windows/win32/api/winbase/nf-winbase-winexec)
- [Windows NT Command Shell](https://docs.microsoft.com/en-us/previous-versions//cc723564%28v=technet.10%29?redirectedfrom=MSDN#XSLTsection127121120120)
