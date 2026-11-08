# T0846 - Remote System Discovery

[ICS](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to get a listing of other systems by IP address, hostname, or other logical identifier on a network that may be used for subsequent Lateral Movement or Discovery techniques. Functionality could exist within adversary tools to enable this, but utilities available on the operating system or vendor software could also be used.(Citation: Enterprise ATT&CK January 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0846)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T0846.002 - Broadcast Discovery](T0846.002%20-%20Broadcast%20Discovery/README.md)
- [T0846.003 - Multicast Discovery](T0846.003%20-%20Multicast%20Discovery/README.md)
- [T0846.001 - Port Scan](T0846.001%20-%20Port%20Scan/README.md)

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

## Detection strategies

- [DET0739 - Detection of Remote System Discovery](../../../Defenses/Detection%20Strategies/DET0739%20-%20Detection%20of%20Remote%20System%20Discovery.md)

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) remotely discovered operational assets once on the OT network. (Citation: Charles McLellan March 2016) (Citation: Booz Allen Hamilton) [Booz Allen Hamilton](https://www.boozallen.com/content/dam/boozallen/documents/2016/09/ukraine-report-when-the-lights-went-out.pdf) · [Charles McLellan March 2016](https://www.zdnet.com/article/how-hackers-attacked-ukraines-power-grid-implications-for-industrial-iot-security/)
- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used `nslookup` and `ping` to conduct remote system discovery activities.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — The [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) ICS malware plugin relies on Windows networking (WNet) to discover all the servers, including OPC servers, that are reachable by the compromised machine over the network. (Citation: Julian Rrushi, Hassan Farhangi, Clay Howey, Kelly Carmichael, Joey Dabell December 2015) [Julian Rrushi, Hassan Farhangi, Clay Howey, Kelly Carmichael, Joey Dabell December 2015](https://pdfs.semanticscholar.org/18df/43ef1690b0fae15a36f770001160aefbc6c5.pdf)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can use the FINS (Factory Interface Network Service) protocol to scan for and obtain MAC address associated with Omron devices.(Citation: CISA-AA22-103A)(Citation: Wylie-22) [CISA-AA22-103A](https://www.cisa.gov/uscert/ncas/alerts/aa22-103a) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) contains an OPC DA module that enumerates all OPC servers using the `ICatInformation::EnumClassesOfCategories` method with `CATID_OPCDAServer20` category identifier and `IOPCServer::GetStatus` to identify the ones running.

## Mitigations

- [M0814 - Static Network Configuration](../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — ICS environments typically have more statically defined devices, therefore minimize the use of both IT discovery protocols (e.g., DHCP, LLDP) and discovery functions in automation protocols.(Citation: D. Parsons and D. Wylie September 2019)(Citation: Colin Gray) Examples of automation protocols with discovery capabilities include OPC UA Device Discovery(Citation: Josh Rinaldi April 2016), BACnet(Citation: Aditya K Sood July 2019), and Ethernet/IP.(Citation: Langner November 2018) [Aditya K Sood July 2019](https://www.helpnetsecurity.com/2019/07/10/bacnet-devices/) · [Colin Gray](https://cdn.selinc.com/assets/Literature/Publications/Technical%20Papers/6891_HowSDN_CG_20180720_Web2.pdf?v=20190312-231901) · [D. Parsons and D. Wylie September 2019](https://www.csiac.org/journal-article/practical-industrial-control-system-ics-cybersecurity-it-and-ot-have-converged-discover-and-defend-your-assets/) · [Josh Rinaldi April 2016](https://www.rtautomation.com/rtas-blog/still-a-thrill-opc-ua-device-discovery/) · [Langner November 2018](https://www.langner.com/2018/11/why-ethernet-ip-changes-the-ot-asset-discovery-game/)

## Sources

- [Enterprise ATT&CK January 2018](https://attack.mitre.org/wiki/Technique/T1018)
