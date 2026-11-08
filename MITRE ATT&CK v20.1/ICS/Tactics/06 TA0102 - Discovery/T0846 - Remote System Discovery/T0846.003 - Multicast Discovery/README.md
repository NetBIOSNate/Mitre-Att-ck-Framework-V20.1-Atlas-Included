# T0846.003 - Multicast Discovery

[ICS](../../../../README.md) / [Discovery](../../README.md) / [T0846 - Remote System Discovery](../README.md)

Adversaries may perform multicast discovery requests which is when one system or device sends messages to all systems and devices in a pre-defined group on a network (or subnet) and then waits for a response. If a response is received that means the system or device that responded is live and can communicate over that protocol.  Multicast discovery tends to be stealthier than broadcast discovery because every system or device on the network (or subnet) is not being messaged. 

One common OT protocol that has a multicast discovery mechanism is the Process Field Network (PROFINET) Discovery and Configuration Protocol (DCP) with its Identify All requests.(Citation: Cisco Active Discovery)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0846/003)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

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

- [S1045 - INCONTROLLER](../../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can perform a UDP multicast scan of UDP port 27127 to identify Schneider PLCs that use that port for the NetManage protocol.(Citation: Dragos-Pipedream)(Citation: Wylie-22) [Dragos-Pipedream](https://hub.dragos.com/hubfs/116-Whitepapers/Dragos_ChernoviteWP_v2b.pdf?hsLang=en) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)

## Mitigations

- [M0930 - Network Segmentation](../../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Ensure proper network segmentation is followed to protect critical servers and devices.
- [M0814 - Static Network Configuration](../../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — ICS environments typically have more statically defined devices, therefore minimize the use of both IT discovery protocols (e.g., DHCP, LLDP) and discovery functions in automation protocols.(Citation: D. Parsons and D. Wylie September 2019)(Citation: Colin Gray) Examples of automation protocols with discovery capabilities include OPC UA Device Discovery (Citation: Josh Rinaldi April 2016), BACnet(Citation: Aditya K Sood July 2019), and Ethernet/IP.(Citation: Langner November 2018) [Aditya K Sood July 2019](https://www.helpnetsecurity.com/2019/07/10/bacnet-devices/) · [Colin Gray](https://cdn.selinc.com/assets/Literature/Publications/Technical%20Papers/6891_HowSDN_CG_20180720_Web2.pdf?v=20190312-231901) · [D. Parsons and D. Wylie September 2019](https://www.csiac.org/journal-article/practical-industrial-control-system-ics-cybersecurity-it-and-ot-have-converged-discover-and-defend-your-assets/) · [Josh Rinaldi April 2016](https://www.rtautomation.com/rtas-blog/still-a-thrill-opc-ua-device-discovery/) · [Langner November 2018](https://www.langner.com/2018/11/why-ethernet-ip-changes-the-ot-asset-discovery-game/)

## Detection strategies

- [DET0909 - Detection of Multicast Discovery](../../../../Defenses/Detection%20Strategies/DET0909%20-%20Detection%20of%20Multicast%20Discovery.md)

## Sources

- [Cisco Active Discovery](https://www.cisco.com/c/en/us/td/docs/security/cyber_vision/publications/Active-Discovery/Release-4-3-0/b_Cisco_Cyber_Vision_Active_Discovery_Configuration_Guide.pdf)
