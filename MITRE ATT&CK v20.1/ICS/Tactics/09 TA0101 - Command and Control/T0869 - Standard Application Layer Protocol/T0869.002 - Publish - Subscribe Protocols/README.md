# T0869.002 - Publish/Subscribe Protocols

[ICS](../../../../README.md) / [Command and Control](../../README.md) / [T0869 - Standard Application Layer Protocol](../README.md)

Adversaries may communicate using publish/subscribe (pub/sub) application layer protocols to avoid detection/network filtering by blending in with existing traffic. Commands to the remote system, and often the results of those commands, will be embedded within the protocol traffic between the client and broker.

Protocols such as MQTT are widely used in Internet-of-Things (IoT) and operational technology environments where devices are resource constrained and there is limited or unreliable network bandwidth. The protocol follows a publish/subscribe design, with message distribution managed by a centralized broker. Publishers categorize their messages by topics, while subscribers receive messages according to their subscribed topics. An adversary may abuse publish/subscribe protocols to communicate with systems under their control from behind a message broker while also blending in with normal, expected traffic.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0869/002)

**Tactics**  [Command and Control](../../README.md)

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

## Mitigations

- [M0937 - Filter Network Traffic](../../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Restrict MQTT, AMQP, DDS, and other publish/subscribe traffic to approved brokers, peers, ports, topics, namespaces, and security zones. Block unauthorized external broker access while preserving documented IIoT/OT messaging paths.
- [M0931 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M0931%20-%20Network%20Intrusion%20Prevention.md) — Use protocol-aware network controls to detect and, where operationally safe, prevent connections to unapproved brokers or malicious infrastructure and misuse of publish/subscribe protocol features for command-and-control.

## Detection strategies

- [DET0935 - Behavioral Detection of Publish/Subscribe Protocol Misuse for Command and Control](../../../../Defenses/Detection%20Strategies/DET0935%20-%20Behavioral%20Detection%20of%20Publish%20-%20Subscribe%20Protocol%20Misuse%20for%20Command%20and%20Control.md)

## Procedure examples

- [S9046 - IOControl](../../../../Threat%20Intelligence/Software/Malware/S9046%20-%20IOControl.md) — IOCONTROL connects to C2 servers using the MQTT protocol over port 1883 and 8883 (encrypted via SSL/TLS). The command-and-control servers are resolved using DNS-over-HTTPS (DoH).(Citation: Claroty-IOCONTROL)(Citation: Dragos 2025 Year in Review)(Citation: Armis-IOCONTROL) [Claroty-IOCONTROL](https://claroty.com/team82/research/inside-a-new-ot-iot-cyber-weapon-iocontrol) · [Dragos 2025 Year in Review](https://5943619.hs-sites.com/hubfs/312-Year-in-Review/2026/Dragos-2026-OT-Cybersecurity-Report-A-Year-in-Review.pdf?hsCtaAttrib=205683189348) · [Armis-IOCONTROL](https://www.armis.com/blog/iocontrol-malware-whats-new-whats-not/)
