# T1701.002 - Windows Command Shell

[ICS](../../../../README.md) / [Execution](../../README.md) / [T1701 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse the Windows command shell for execution. The Windows command shell (cmd) is the primary command prompt on Windows systems which is used in industrial control system environments. The Windows command prompt can be used to control almost any aspect of a system, with various permission levels required for different subsets of commands. The command prompt can be invoked remotely via  [Remote Services](https://attack.mitre.org/techniques/T0886) (e.g., Telnet, SSH, RDP, etc.) 

Batch files (ex: .bat or .cmd) also provide the shell with a list of sequential commands to run, as well as normal scripting operations such as conditionals and loops. Common uses of batch files include long or repetitive tasks, or the need to run the same set of commands on multiple systems. 

Adversaries may leverage [cmd](https://attack.mitre.org/software/S0106) to execute various commands and payloads. Common uses include [cmd](https://attack.mitre.org/software/S0106) to execute a single command, or abusing [cmd](https://attack.mitre.org/software/S0106) interactively with input and output forwarded over a command and control channel. 

Within industrial control system networks, adversaries may abuse the use of Windows Command Shell on overlap assets that run on Microsoft Windows operating systems (Workstations, Data Historians, Human Machine Interfaces, Application Servers, Jump Hosts, etc.).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701/002)

**Tactics**  [Execution](../../README.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) utilized VBS and batch scripts for file movement and as wrappers for PowerShell execution.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0034 - 2022 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0034%20-%202022%20Ukraine%20Electric%20Power%20Attack.md) — During the [2022 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0034), [Sandworm Team](https://attack.mitre.org/groups/G0034) utilizes a Visual Basic script `lun.vbs` to execute `n.bat` which then executed the MicroSCADA `scilc.exe` command.(Citation: Mandiant-Sandworm-Ukraine-2022) [Mandiant-Sandworm-Ukraine-2022](https://www.mandiant.com/resources/blog/sandworm-disrupts-power-ukraine-operational-technology)
- [S0604 - Industroyer](../../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — The name of the [Industroyer](https://attack.mitre.org/software/S0604) payload DLL is supplied by the attackers via a command line parameter supplied in one of the main backdoors that executes shell commands. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) uses the MS-SQL server xp_cmdshell command, and PowerShell to execute commands. (Citation: Dragos October 2018) [Dragos October 2018](https://dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [S0603 - Stuxnet](../../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) will store and execute SQL code that will extract and execute Stuxnet from the saved CAB file using xp_cmdshell with the following command: `set @s = master..xp _ cmdshell extrac32 /y +@t+ +@t+x; exec(@s);` (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

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

## Detection strategies

- [DET0930 - Behavioral Detection of Windows Command Shell Execution in ICS](../../../../Defenses/Detection%20Strategies/DET0930%20-%20Behavioral%20Detection%20of%20Windows%20Command%20Shell%20Execution%20in%20ICS.md)

## Mitigations

- [M0938 - Execution Prevention](../../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Restrict cmd.exe, batch files, and command-shell child processes to approved binaries, paths, parent processes, accounts, and maintenance workflows on Windows-based ICS assets. Preserve documented vendor and engineering dependencies.
