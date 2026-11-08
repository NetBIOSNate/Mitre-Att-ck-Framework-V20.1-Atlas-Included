# T0846.001 - Port Scan

[ICS](../../../../README.md) / [Discovery](../../README.md) / [T0846 - Remote System Discovery](../README.md)

Adversaries may perform a port scan on a system, device, or network to identify live hosts, enumerate open ports and running services, identify operating systems, and map out the network.(Citation: NIST SP 800-82r3) The results of a port scan may inform adversary [Discovery](https://attack.mitre.org/tactics/TA0102), [Lateral Movement](https://attack.mitre.org/tactics/TA0109), and vulnerability exploitation decisions ([Exploitation for Evasion](https://attack.mitre.org/techniques/T0820), [Exploitation for Privilege Escalation](https://attack.mitre.org/techniques/T0890), [Exploitation of Remote Services](https://attack.mitre.org/techniques/T0866)). 

Some common tools for executing a port scan include `nmap`, `netcat`, and the Advanced Port Scanner.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0846/001)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Mitigations

- [M0931 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Use network intrusion detection/prevention systems to detect and prevent port scans.
- [M0930 - Network Segmentation](../../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Ensure proper network segmentation is followed to protect critical systems and devices.
- [M0814 - Static Network Configuration](../../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — ICS environments typically have more statically defined devices, therefore minimize the use of both IT discovery protocols (e.g., DHCP, LLDP) and discovery functions in automation protocols.(Citation: D. Parsons and D. Wylie September 2019)(Citation: Colin Gray) Examples of automation protocols with discovery capabilities include OPC UA Device Discovery(Citation: Josh Rinaldi April 2016), BACnet(Citation: Aditya K Sood July 2019), and Ethernet/IP.(Citation: Langner November 2018) [Aditya K Sood July 2019](https://www.helpnetsecurity.com/2019/07/10/bacnet-devices/) · [Colin Gray](https://cdn.selinc.com/assets/Literature/Publications/Technical%20Papers/6891_HowSDN_CG_20180720_Web2.pdf?v=20190312-231901) · [D. Parsons and D. Wylie September 2019](https://www.csiac.org/journal-article/practical-industrial-control-system-ics-cybersecurity-it-and-ot-have-converged-discover-and-defend-your-assets/) · [Josh Rinaldi April 2016](https://www.rtautomation.com/rtas-blog/still-a-thrill-opc-ua-device-discovery/) · [Langner November 2018](https://www.langner.com/2018/11/why-ethernet-ip-changes-the-ot-asset-discovery-game/)

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0014 - Routers](../../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0010 - Safety Controller](../../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used Advanced Port Scanner and Advanced IP Scanner to conduct remote system discovery activities.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S1045 - INCONTROLLER](../../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) has the ability to perform scans for TCP port 4840 to identify devices running OPC UA servers.(Citation: Wylie-22) [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S0604 - Industroyer](../../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — The [Industroyer](https://attack.mitre.org/software/S0604) IEC 61850 payload component has the ability to discover relevant devices in the infected host's network subnet by attempting to connect on port 102.(Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S9046 - IOControl](../../../../Threat%20Intelligence/Software/Malware/S9046%20-%20IOControl.md) — IOCONTROL has conducted port scans on a network.(Citation: Claroty-IOCONTROL) [Claroty-IOCONTROL](https://claroty.com/team82/research/inside-a-new-ot-iot-cyber-weapon-iocontrol)
- [S1006 - PLC-Blaster](../../../../Threat%20Intelligence/Software/Malware/S1006%20-%20PLC-Blaster.md) — [PLC-Blaster](https://attack.mitre.org/software/S1006) scans the network to find other Siemens S7 PLC devices to infect. It locates these devices by checking for a service listening on TCP port 102.(Citation: Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016) [Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC-wp.pdf)

## Detection strategies

- [DET0907 - Detection of Port Scan](../../../../Defenses/Detection%20Strategies/DET0907%20-%20Detection%20of%20Port%20Scan.md)

## Sources

- [NIST SP 800-82r3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r3.pdf)
