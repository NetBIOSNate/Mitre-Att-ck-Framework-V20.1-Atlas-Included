# T0842 - Network Sniffing

[ICS](../../../README.md) / [Discovery](../README.md)

Network sniffing is the practice of using a network interface on a computer system to monitor or capture information (Citation: Enterprise ATT&CK January 2018) regardless of whether it is the specified destination for the information. 

An adversary may attempt to sniff the traffic to gain information about the target. This information can vary in the level of importance. Relatively unimportant information is general communications to and from machines.  Relatively important information would be login information. User credentials may be sent over an unencrypted protocol, such as Telnet, that can be captured and obtained through network packet analysis. 

In addition, ARP and Domain Name Service (DNS) poisoning can be used to capture credentials to websites, proxies, and internal systems by redirecting traffic to an adversary.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0842)

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

## Mitigations

- [M0808 - Encrypt Network Traffic](../../../Defenses/Mitigations/M0808%20-%20Encrypt%20Network%20Traffic.md) — Ensure that wired and/or wireless traffic is encrypted when feasible. Use best practices for authentication protocols, such as Kerberos, and ensure web traffic that may contain credentials is protected by SSL/TLS. (Citation: Keith Stouffer May 2015) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
- [M0932 - Multi-factor Authentication](../../../Defenses/Mitigations/M0932%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication wherever possible.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment networks and systems appropriately to reduce access to critical system and services communications.
- [M0926 - Privileged Account Management](../../../Defenses/Mitigations/M0926%20-%20Privileged%20Account%20Management.md) — Restrict root or administrator access on user accounts to limit the ability to capture promiscuous traffic on a network through common packet capture tools. (Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0814 - Static Network Configuration](../../../Defenses/Mitigations/M0814%20-%20Static%20Network%20Configuration.md) — Statically defined ARP entries can prevent manipulation and sniffing of switched network traffic, as some AiTM techniques depend on sending spoofed ARP messages to manipulate network host's dynamic ARP tables.

## Detection strategies

- [DET0800 - Detection of Network Sniffing](../../../Defenses/Detection%20Strategies/DET0800%20-%20Detection%20of%20Network%20Sniffing.md)

## Procedure examples

- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can deploy Tcpdump to sniff network traffic and collect PCAP files.(Citation: Wylie-22) [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — DP_RECV is the name of a standard function block used by network coprocessors. It is used to receive network frames on the Profibus a standard industrial network bus used for distributed I/O. The original block is copied to FC1869, and then replaced by a malicious block. Each time the function is used to receive a packet, the malicious [Stuxnet](https://attack.mitre.org/software/S0603) block takes control: it will call the original DP_RECV in FC1869 and then perform postprocessing on the packet data. The replaced DP_RECV block (later on referred to as the DP_RECV monitor) is meant to monitor data sent by the frequency converter drives to the 315-2 CPU via CP 342-5 Profibus communication modules. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [S1010 - VPNFilter](../../../Threat%20Intelligence/Software/Malware/S1010%20-%20VPNFilter.md) — The [VPNFilter](https://attack.mitre.org/software/S1010) packet sniffer looks for basic authentication as well as monitors ICS traffic, and is specific to the TP-LINK R600-VPN. The malware uses a raw socket to look for connections to a pre-specified IP address, only looking at TCP packets that are 150 bytes or larger. Packets that are not on port 502, are scanned for BasicAuth, and that information is logged. This may have allowed credential harvesting from communications between devices accessing a modbus-enabled HMI. (Citation: William Largent June 2018) (Citation: Carl Hurd March 2019) [Carl Hurd March 2019](https://www.youtube.com/watch?v=yuZazP22rpI) · [William Largent June 2018](https://blog.talosintelligence.com/2018/06/vpnfilter-update.html)

## Sources

- [Enterprise ATT&CK January 2018](https://attack.mitre.org/wiki/Technique/T1040)
