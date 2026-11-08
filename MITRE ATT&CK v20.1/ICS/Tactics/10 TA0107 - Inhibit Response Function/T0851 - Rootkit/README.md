# T0851 - Rootkit

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may deploy rootkits to hide the presence of programs, files, network connections, services, drivers, and other system components. Rootkits are programs that hide the existence of malware by intercepting and modifying operating-system API calls that supply system information. Rootkits or rootkit-enabling functionality may reside at the user or kernel level in the operating system, or lower. (Citation: Enterprise ATT&CK January 2018)   

Firmware rootkits that affect the operating system yield nearly full control of the system. While firmware rootkits are normally developed for the main processing board, they can also be developed for the I/O that is attached to an asset. Compromise of this firmware allows the modification of all of the process variables and functions the module engages in. This may result in commands being disregarded and false information being fed to the main device. By tampering with device processes, an adversary may inhibit its expected response functions and possibly enable [Impact](https://attack.mitre.org/tactics/TA0105).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0851)

**Tactics**  [Evasion](../../05%20TA0103%20-%20Evasion/README.md), [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0780 - Detection of Rootkit](../../../Defenses/Detection%20Strategies/DET0780%20-%20Detection%20of%20Rootkit.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Audit the integrity of PLC system and application code functionality, such as the manipulation of standard function blocks (e.g., Organizational Blocks) that manage the execution of application logic programs. (Citation: IEC February 2019) [IEC February 2019](https://webstore.iec.ch/publication/34421)
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Digital signatures may be used to ensure application DLLs are authentic prior to execution.

## Procedure examples

- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — One of [Stuxnet](https://attack.mitre.org/software/S0603)'s rootkits is contained entirely in the fake s7otbxdx.dll. In order to continue existing undetected on the PLC it needs to account for at least the following situations: read requests for its own malicious code blocks, read requests for infected blocks (OB1, OB35, DP_RECV), and write requests that could overwrite Stuxnets own code. Stuxnet contains code to monitor and intercept these types of requests. The rootkit modifies these requests so that Stuxnets PLC code is not discovered or damaged. (Citation: Langer Stuxnet) [Langer Stuxnet](https://www.langner.com/wp-content/uploads/2017/03/to-kill-a-centrifuge.pdf)

## Sources

- [Enterprise ATT&CK January 2018](https://attack.mitre.org/wiki/Technique/T1014)
