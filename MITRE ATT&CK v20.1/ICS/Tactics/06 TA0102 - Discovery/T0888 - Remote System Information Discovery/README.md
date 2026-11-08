# T0888 - Remote System Information Discovery

[ICS](../../../README.md) / [Discovery](../README.md)

An adversary may attempt to get detailed information about remote systems and their peripherals, such as make/model, role, and configuration. Adversaries may use information from Remote System Information Discovery to aid in targeting and shaping follow-on behaviors. For example, the system's operational role and model information can dictate whether it is a relevant target for the adversary's operational objectives. In addition, the system's configuration may be used to scope subsequent technique usage. 

Requests for system information are typically implemented using automation and management protocols and are often automatically requested by vendor software during normal operation. This information may be used to tailor management actions, such as program download and system or module firmware. An adversary may leverage this same information by issuing calls directly to the system's API.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0888)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries remotely executed commands on systems using [PsExec](https://attack.mitre.org/software/S0029) to gather information about running processes, network connections, routing tables, ARP cache, and contents of user directories.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — The [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) payload gathers server information that includes CLSID, server name, Program ID, OPC version, vendor information, running state, group count, and server bandwidth. This information helps indicate the role the server has in the control process. (Citation: ICS-CERT August 2018) (Citation: Daavid Hentunen, Antti Tikkanen June 2014) [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html) · [ICS-CERT August 2018](https://ics-cert.us-cert.gov/advisories/ICSA-14-178-01)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) includes a library that creates Modbus connections with a device to request its device ID.(Citation: CISA-AA22-103A)(Citation: Wylie-22) [CISA-AA22-103A](https://www.cisa.gov/uscert/ncas/alerts/aa22-103a) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — The [Industroyer](https://attack.mitre.org/software/S0604) IEC 61850 component sends the domain-specific MMSgetNameList request to determine what logical nodes the device supports. It then searches the logical nodes for the CSW value, which indicates the device performs a circuit breaker or switch control function.(Citation: ESET Industroyer) [Industroyer](https://attack.mitre.org/software/S0604)'s OPC DA module also uses IOPCBrowseServerAddressSpace to look for items with the following strings: ctlSelOn, ctlOperOn, ctlSelOff, ctlOperOff, Pos and stVal.(Citation: ESET Industroyer) [Industroyer](https://attack.mitre.org/software/S0604) IEC 60870-5-104 module includes a range mode to discover Information Object Addresses (IOAs) by enumerating through each.(Citation: ESET Industroyer) [ESET Industroyer](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S1072 - Industroyer2](../../../Threat%20Intelligence/Software/Malware/S1072%20-%20Industroyer2.md) — [Industroyer2](https://attack.mitre.org/software/S1072) has the capability to poll a target device about its connection status, data transfer status, Common Address (CA), Information Object Addresses (IOAs), and IO state values across multiple priority levels.(Citation: Industroyer2 Forescout July 2022)(Citation: Industroyer2 ESET April 2022) [Industroyer2 ESET April 2022](https://www.welivesecurity.com/2022/04/12/industroyer2-industroyer-reloaded/) · [Industroyer2 Forescout July 2022](https://www.forescout.com/resources/industroyer2-and-incontroller-report/)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) enumerates and parses the System Data Blocks (SDB) using the s7blk_findfirst and s7blk_findnext API calls in s7otbxdx.dll. Stuxnet must find an SDB with the DWORD at offset 50h equal to 0100CB2Ch. This specifies that the system uses the Profibus communications processor module CP 342-5. In addition, specific values are searched for and counted: 7050h and 9500h. 7050h is assigned to part number KFC750V3 which appears to be a frequency converter drive (also known as variable frequency drive) manufactured by Fararo Paya in Teheran, Iran. 9500h is assigned to Vacon NX frequency converter drives manufactured by Vacon based in Finland.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Stuxnet](https://attack.mitre.org/software/S0603) was specifically targeting CPUs 6ES7-315-2 (Series 300) with special system data block characteristics for sequence A or B and 6ES7-315-2 for sequence C. The PLC type can also be checked using the s7ag_read_szl API.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

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
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0814 - Static Network Configuration](../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — ICS environments typically have more statically defined devices, therefore minimize the use of both IT discovery protocols (e.g., DHCP, LLDP) and discovery functions in automation protocols. (Citation: D. Parsons and D. Wylie September 2019) (Citation: Colin Gray) Examples of automation protocols with discovery capabilities include OPC UA Device Discovery (Citation: Josh Rinaldi April 2016), BACnet (Citation: Aditya K Sood July 2019), and Ethernet/IP. (Citation: Langner November 2018) [D. Parsons and D. Wylie September 2019](https://www.csiac.org/journal-article/practical-industrial-control-system-ics-cybersecurity-it-and-ot-have-converged-discover-and-defend-your-assets/) · [Colin Gray](https://cdn.selinc.com/assets/Literature/Publications/Technical%20Papers/6891_HowSDN_CG_20180720_Web2.pdf?v=20190312-231901) · [Josh Rinaldi April 2016](https://www.rtautomation.com/rtas-blog/still-a-thrill-opc-ua-device-discovery/) · [Aditya K Sood July 2019](https://www.helpnetsecurity.com/2019/07/10/bacnet-devices/) · [Langner November 2018](https://www.langner.com/2018/11/why-ethernet-ip-changes-the-ot-asset-discovery-game/)

## Detection strategies

- [DET0787 - Detection of Remote System Information Discovery](../../../Defenses/Detection%20Strategies/DET0787%20-%20Detection%20of%20Remote%20System%20Information%20Discovery.md)
