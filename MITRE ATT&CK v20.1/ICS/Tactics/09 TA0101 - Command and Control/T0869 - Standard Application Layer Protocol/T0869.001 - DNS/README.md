# T0869.001 - DNS

[ICS](../../../../README.md) / [Command and Control](../../README.md) / [T0869 - Standard Application Layer Protocol](../README.md)

Adversaries may communicate using the Domain Name System (DNS) application layer protocol to avoid detection/network filtering by blending in with existing traffic. Commands to the remote system, and often the results of those commands, will be embedded within the protocol traffic between the client and server.
The DNS protocol serves an administrative function in computer networking and thus may be very common in environments. DNS traffic may also be allowed even before network authentication is completed. DNS packets contain many fields and headers in which data can be concealed. Often known as DNS tunneling, adversaries may abuse DNS to communicate with systems under their control within a victim network while also mimicking normal, expected traffic.(Citation: PAN DNS Tunneling)(Citation: Medium DnsTunneling)

DNS beaconing may be used to send commands to remote systems via DNS queries. A DNS beacon is created by tunneling DNS traffic (i.e. Protocol Tunneling). The commands may be embedded into different DNS records, for example, TXT or A records.(Citation: OilRig Uses Updated BONDUPDATER to Target Middle Eastern Government)
 DNS beacons may be difficult to detect because the beacons infrequently communicate with infected devices.(Citation: DNS Beacons) Infrequent communication conceals the malicious DNS traffic with normal DNS traffic.

Adversaries may also use DNS over TLS (DoT) or HTTPS (DoH) for resolving C2 servers. This encrypts the DNS requests and allows the malware to lookup C2 servers without being detected by security systems (e.g., DNS filtering based on indicators of compromise).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0869/001)

**Tactics**  [Command and Control](../../README.md)

## Mitigations

- [M0937 - Filter Network Traffic](../../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Require ICS assets to use approved DNS resolvers and restrict direct DNS, DoT, and DoH to unauthorized external resolvers or services. Apply allowlists for documented vendor/cloud dependencies and monitor exceptions rather than assuming all encrypted DNS is malicious.
- [M0931 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Use network security controls to identify and, where operationally safe, block DNS tunneling, unauthorized resolver use, suspicious DoH/DoT destinations, and known malicious DNS infrastructure at controlled ICS egress points.

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

## Detection strategies

- [DET0934 - Behavioral Detection of DNS Protocol Misuse for Command and Control](../../../../Defenses/Detection%20Strategies/DET0934%20-%20Behavioral%20Detection%20of%20DNS%20Protocol%20Misuse%20for%20Command%20and%20Control.md)

## Procedure examples

- [S9046 - IOControl](../../../../Threat%20Intelligence/Software/Malware/S9046%20-%20IOControl.md) — IOCONTROL has used DNS over HTTPS (DoH) via CloudFlare’s API to translate hostnames to IP addresses.(Citation: Claroty-IOCONTROL)(Citation: Dragos 2025 Year in Review)(Citation: Armis-IOCONTROL) [Claroty-IOCONTROL](https://claroty.com/team82/research/inside-a-new-ot-iot-cyber-weapon-iocontrol) · [Dragos 2025 Year in Review](https://5943619.hs-sites.com/hubfs/312-Year-in-Review/2026/Dragos-2026-OT-Cybersecurity-Report-A-Year-in-Review.pdf?hsCtaAttrib=205683189348) · [Armis-IOCONTROL](https://www.armis.com/blog/iocontrol-malware-whats-new-whats-not/)

## Sources

- [Medium DnsTunneling](https://medium.com/@galolbardes/learn-how-easy-is-to-bypass-firewalls-using-dns-tunneling-and-also-how-to-block-it-3ed652f4a000)
- [OilRig Uses Updated BONDUPDATER to Target Middle Eastern Government](https://unit42.paloaltonetworks.com/unit42-oilrig-uses-updated-bondupdater-target-middle-eastern-government/)
- [PAN DNS Tunneling](https://www.paloaltonetworks.com/cyberpedia/what-is-dns-tunneling)
- [DNS Beacons](https://vercara.digicert.com/resources/dns-beacons#page_top)
