# T1701 - Command and Scripting Interpreter

[ICS](../../../README.md) / [Execution](../README.md)

Adversaries may abuse command and script interpreters to execute commands, scripts, or binaries. These interfaces and languages provide ways of interacting with computer systems and are a common feature across many different platforms within industrial control system environments. Most systems come with some built-in command-line interface and scripting capabilities, for example, macOS and Linux distributions include some flavor of [Unix Shell](https://attack.mitre.org/techniques/T1701/003) while Windows installations include the [Windows Command Shell](https://attack.mitre.org/techniques/T1701/002) and [PowerShell](https://attack.mitre.org/techniques/T1701/001). Some also have cross-platform interpreters such as [Python](https://attack.mitre.org/techniques/T1701/005), as well as those commonly associated with client applications such as [JavaScript](https://attack.mitre.org/techniques/T1701/006) and [Visual Basic](https://attack.mitre.org/techniques/T1701/004). Many controllers have command-line interfaces for management purposes. 

Adversaries may abuse these technologies in various ways as a means of executing arbitrary commands. Commands and scripts can be embedded in [Initial Access](https://attack.mitre.org/tactics/TA0108) payloads delivered to victims as lure documents or as secondary payloads downloaded from an existing C2. Adversaries may also execute commands through interactive terminals/shells, as well as utilize various [Remote Services](https://attack.mitre.org/techniques/T0886) (e.g., Telnet, SSH, RDP, etc.) often found in industrial control system environments to achieve remote [Execution](https://attack.mitre.org/tactics/TA0104).(Citation: Powershell Remote Commands)(Citation: Cisco IOS Software Integrity Assurance - Command History)(Citation: Remote Shell Execution in Python)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701)

**Tactics**  [Execution](../README.md)

## Sub-techniques

- [T1701.006 - JavaScript](T1701.006%20-%20JavaScript/README.md)
- [T1701.001 - PowerShell](T1701.001%20-%20PowerShell/README.md)
- [T1701.005 - Python](T1701.005%20-%20Python/README.md)
- [T1701.003 - Unix Shell](T1701.003%20-%20Unix%20Shell/README.md)
- [T1701.004 - Visual Basic](T1701.004%20-%20Visual%20Basic/README.md)
- [T1701.002 - Windows Command Shell](T1701.002%20-%20Windows%20Command%20Shell/README.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0014 - Routers](../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0928 - Behavioral Detection of Command and Scripting Abuse in ICS](../../../Defenses/Detection%20Strategies/DET0928%20-%20Behavioral%20Detection%20of%20Command%20and%20Scripting%20Abuse%20in%20ICS.md)

## Mitigations

- [M0948 - Application Isolation and Sandboxing](../../../Defenses/Mitigations/M0948%20-%20Application%20Isolation%20and%20Sandboxing.md) — Consider the use of application isolation and sandboxing to restrict specific operating system interactions such as access through user accounts, services, system calls, registry, and network access. This may be even more useful in cases where the source of the executed script is unknown.
- [M0942 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider removing or restricting features that are unnecessary to an asset's intended function within the control environment.
- [M0938 - Execution Prevention](../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Execution prevention may block malicious software from accessing protected resources through the command-line interface.

## Procedure examples

- [S1165 - FrostyGoop](../../../Threat%20Intelligence/Software/Malware/S1165%20-%20FrostyGoop.md) — [FrostyGoop](https://attack.mitre.org/software/S1165) is compiled for Windows systems and leverages a Windows-based command line interface.(Citation: Dragos FROSTYGOOP 2024) Modbus interaction functionality is based off a publicly available Github repository for command line input.(Citation: Nozomi BUSTLEBERM 2024) [Dragos FROSTYGOOP 2024](https://hub.dragos.com/hubfs/Reports/Dragos-FrostyGoop-ICS-Malware-Intel-Brief-0724_r2.pdf) · [Nozomi BUSTLEBERM 2024](https://www.nozominetworks.com/blog/protecting-against-frostygoop-bustleberm-malware)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088)’ tool took one option from the command line, which was a single IP address of the target Triconex device.(Citation: FireEye TRITON Dec 2017) [FireEye TRITON Dec 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)

## Sources

- [Remote Shell Execution in Python](https://www.thepythoncode.com/article/executing-bash-commands-remotely-in-python)
- [Cisco IOS Software Integrity Assurance - Command History](https://tools.cisco.com/security/center/resources/integrity_assurance.html#23)
- [Powershell Remote Commands](https://docs.microsoft.com/en-us/powershell/scripting/learn/remoting/running-remote-commands?view=powershell-7.1)
