# T1701.003 - Unix Shell

[ICS](../../../../README.md) / [Execution](../../README.md) / [T1701 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse Unix shell commands and scripts for execution. Unix shells are the primary command prompt on Linux, macOS, and ESXi systems, though many variations of the Unix shell exist (e.g. sh, ash, bash, zsh, etc.) depending on the specific OS or distribution.(Citation: DieNet Bash)(Citation: Apple ZShell) Unix shells can control every aspect of a system, with certain commands requiring elevated privileges.

Unix shells also support scripts that enable sequential execution of commands as well as other typical programming operations such as conditionals and loops. Common uses of shell scripts include long or repetitive tasks, or the need to run the same set of commands on multiple systems.

Adversaries may abuse Unix shells to execute various commands or payloads. Interactive shells may be accessed through command and control channels or during lateral movement such as with [Remote Services](https://attack.mitre.org/techniques/T0886). Adversaries may also leverage shell scripts to deliver and execute multiple commands on victims or as part of payloads used for persistence.

Within Industrial control system networks, workstations, control servers, hypervisors, networking devices, and embedded devices that run on linux platforms may allow for Unix command shell access or stripped-down shells to implement a subset of commands. Industrial automation equipment generally does not offer command shells as a native user interface.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701/003)

**Tactics**  [Execution](../../README.md)

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0014 - Routers](../../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0015 - Switch](../../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0938 - Execution Prevention](../../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Restrict interactive and scripted shell execution on Linux, network, and embedded ICS assets to approved accounts, management paths, commands, and vendor workflows. Where full application control is unavailable, constrain SSH/Telnet access and privileged shell use to dedicated administration paths.

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries logged into the Mikronika RTUs via SSH, with root privileges, and executed Linux commands to delete all the files on the system resulting in device failure.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S9046 - IOControl](../../../../Threat%20Intelligence/Software/Malware/S9046%20-%20IOControl.md) — IOCONTROL has executed arbitrary commands using system calls as well as scripts with the UNIX Shell.(Citation: Claroty-IOCONTROL) [Claroty-IOCONTROL](https://claroty.com/team82/research/inside-a-new-ot-iot-cyber-weapon-iocontrol)

## Detection strategies

- [DET0931 - Behavioral Detection of Unix Shell Execution in ICS](../../../../Defenses/Detection%20Strategies/DET0931%20-%20Behavioral%20Detection%20of%20Unix%20Shell%20Execution%20in%20ICS.md)

## Sources

- [Apple ZShell](https://support.apple.com/HT208050)
- [DieNet Bash](https://linux.die.net/man/1/bash)
