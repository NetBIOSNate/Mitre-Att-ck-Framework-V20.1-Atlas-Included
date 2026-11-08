# T0840 - Network Connection Enumeration

[ICS](../../../README.md) / [Discovery](../README.md)

Adversaries may perform network connection enumeration to discover information about device communication patterns. If an adversary can inspect the state of a network connection with tools, such as Netstat(Citation: Netstat), in conjunction with [System Firmware](https://attack.mitre.org/techniques/T0857), then they can determine the role of certain devices on the network  (Citation: MITRE). The adversary can also use [Network Sniffing](https://attack.mitre.org/techniques/T0842) to watch network traffic for details about the source, destination, protocol, and content.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0840)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used `netstat` to enumerate network connections on the Mikronika HMI computers.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S0605 - EKANS](../../../Threat%20Intelligence/Software/Malware/S0605%20-%20EKANS.md) — [EKANS](https://attack.mitre.org/software/S0605) performs a DNS lookup of an internal domain name associated with its target network to identify if it was deployed on the intended system. (Citation: Ben Hunter and Fred Gutierrez July 2020) [Ben Hunter and Fred Gutierrez July 2020](https://www.fortinet.com/blog/threat-research/ekans-ransomware-targeting-ot-ics-systems)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) contains an IEC 61850 module that enumerates all connected network adapters to determine their TCP/IP subnet masks. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)

## Detection strategies

- [DET0770 - Detection of Network Connection Enumeration](../../../Defenses/Detection%20Strategies/DET0770%20-%20Detection%20of%20Network%20Connection%20Enumeration.md)

## Mitigations

- [M0816 - Mitigation Limited or Not Effective](../../../Defenses/Mitigations/M0816%20-%20Mitigation%20Limited%20or%20Not%20Effective.md) — Network connection enumeration is likely obtained by using common system tools (e.g., netstat, ipconfig).

## Sources

- [MITRE](https://attack.mitre.org/wiki/Technique/T1049)
- [Netstat](https://en.wikipedia.org/wiki/Netstat)
