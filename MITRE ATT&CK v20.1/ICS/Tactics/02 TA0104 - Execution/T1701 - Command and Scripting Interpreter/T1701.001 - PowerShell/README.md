# T1701.001 - PowerShell

[ICS](../../../../README.md) / [Execution](../../README.md) / [T1701 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse PowerShell commands and scripts for execution. PowerShell is a powerful interactive command-line interface and scripting environment included in the Windows operating system.(Citation: TechNet PowerShell) Adversaries can use PowerShell to perform a number of actions, including discovery of information and execution of code. Examples include the <code>Start-Process</code> cmdlet which can be used to run an executable and the <code>Invoke-Command</code> cmdlet which runs a command locally or on a remote computer (though administrator permissions are required to use PowerShell to connect to remote systems).

PowerShell may also be used to download and run executables from the Internet, which can be executed from disk or in memory without touching disk.

PowerShell commands/scripts can also be executed without directly invoking the <code>powershell.exe</code> binary through interfaces to PowerShell's underlying <code>System.Management.Automation</code> assembly DLL exposed through the .NET framework and Windows Common Language Interface (CLI).(Citation: Sixdub PowerPick Jan 2016)(Citation: SilentBreak Offensive PS Dec 2015)(Citation: Microsoft PSfromCsharp APR 2014)

Within industrial control system networks, adversaries may abuse the use of PowerShell on overlap assets that run on Microsoft Windows operating systems (Workstations, Data Historians, Human Machine Interfaces, Application Servers, Jump Hosts, etc.).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701/001)

**Tactics**  [Execution](../../README.md)

## Mitigations

- [M0945 - Code Signing](../../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Require signed PowerShell scripts where operationally feasible and restrict execution of unsigned or untrusted scripts on ICS Windows assets. Maintain explicit exceptions for validated vendor and engineering automation.
- [M0942 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Where PowerShell is not required for the documented function of an ICS asset, disable or remove access to it. Do not apply this control to systems where vendor support, engineering workflows, backup, patching, or approved automation depend on PowerShell.
- [M0938 - Execution Prevention](../../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Use application control/allowlisting to restrict PowerShell hosts, script paths, interpreters, and child-process behavior to approved engineering and operational workflows. Prefer explicit allowlists over broad blocking on production OT systems.
- [M0950 - Exploit Protection](../../../../Defenses/Mitigations/M0950%20-%20Exploit%20Protection.md) — Use supported exploit-protection controls on Windows-based ICS overlap assets to reduce execution paths commonly used to launch or inject PowerShell-driven payloads. Validate compatibility with HMI, historian, engineering, and vendor applications before enforcement.
- [M0926 - Privileged Account Management](../../../../Defenses/Mitigations/M0926%20-%20Privileged%20Account%20Management.md) — Restrict privileged PowerShell use to authorized engineering and administrative accounts and controlled access paths. Separate routine operator activity from privileged maintenance and engineering functions.

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) utilized VBS and batch scripts for file movement and as wrappers for PowerShell execution.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries executed PowerShell commands on the Human Machine Interface (HMI) to make configuration changes that enabled administrative shares and created a new firewall rule to enable traffic over port 445 as well as conducted network reconnaissance activities.(Citation: CERT Polska) During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries executed PowerShell commands on the domain controller that collected and exfiltrated the SAM and SYSTEM registry hives and the Active Directory database (ntds.dit).(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G0064 - APT33](../../../../Threat%20Intelligence/Groups/G0064%20-%20APT33.md) — [APT33](https://attack.mitre.org/groups/G0064) utilized PowerShell scripts to establish command and control and install files for execution. (Citation: Symantec March 2019) (Citation: Dragos) [Dragos](https://dragos.com/resource/allanite/) · [Symantec March 2019](https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has embedded a macro within spearphishing attachments that has been made up of both a VBScript and a PowerShell script.(Citation: Robert Falcone, Bryan Lee May 2016) [Robert Falcone, Bryan Lee May 2016](https://unit42.paloaltonetworks.com/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)
- [S0496 - REvil](../../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) utilizes JavaScript, WScript, and PowerShell scripts to execute. The malicious JavaScript attachment has an obfuscated PowerShell script that executes the malware. (Citation: Tom Fakterman August 2019) [Tom Fakterman August 2019](https://www.cybereason.com/blog/the-sodinokibi-ransomware-attack)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) uses the MS-SQL server xp_cmdshell command, and PowerShell to execute commands. (Citation: Dragos October 2018) [Dragos October 2018](https://dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0030 - Triton Safety Instrumented System Attack](../../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) used a publicly available PowerShell-based tool, WMImplant.(Citation: FireEye TEMP.Veles 2018) [FireEye TEMP.Veles 2018](https://web.archive.org/web/20190202205824/https://www.fireeye.com/blog/threat-research/2018/10/triton-attribution-russian-government-owned-lab-most-likely-built-tools.html)

## Detection strategies

- [DET0929 - Behavioral Detection of PowerShell Execution in ICS](../../../../Defenses/Detection%20Strategies/DET0929%20-%20Behavioral%20Detection%20of%20PowerShell%20Execution%20in%20ICS.md)

## Sources

- [Microsoft PSfromCsharp APR 2014](https://blogs.msdn.microsoft.com/kebab/2014/04/28/executing-powershell-scripts-from-c/)
- [SilentBreak Offensive PS Dec 2015](https://web.archive.org/web/20190508170150/https://silentbreaksecurity.com/powershell-jobs-without-powershell-exe/)
- [TechNet PowerShell](https://technet.microsoft.com/en-us/scriptcenter/dd742419.aspx)
- [Sixdub PowerPick Jan 2016](https://web.archive.org/web/20160327101330/http://www.sixdub.net/?p=367)
