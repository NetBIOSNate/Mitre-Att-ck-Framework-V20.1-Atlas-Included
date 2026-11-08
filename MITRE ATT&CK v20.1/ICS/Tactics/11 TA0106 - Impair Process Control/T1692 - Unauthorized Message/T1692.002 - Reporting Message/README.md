# T1692.002 - Reporting Message

[ICS](../../../../README.md) / [Impair Process Control](../../README.md) / [T1692 - Unauthorized Message](../README.md)

Adversaries may spoof reporting messages in control system environments for evasion and to impair process control. In control systems, reporting messages contain telemetry data (e.g., I/O values) pertaining to the current state of equipment and the industrial process. Reporting messages are important for monitoring the normal operation of a system or identifying important events such as deviations from expected values.

If an adversary has the ability to Spoof Reporting Messages, they can impact the control system in many ways. The adversary can Spoof Reporting Messages that state that the process is operating normally, as a form of evasion. The adversary could also Spoof Reporting Messages to make the defenders and operators think that other errors are occurring in order to distract them from the actual source of a problem.(Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1692/002)

**Tactics**  [Evasion](../../../05%20TA0103%20-%20Evasion/README.md), [Impair Process Control](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0020 - Maroochy Water Breach](../../../../Threat%20Intelligence/Campaigns/C0020%20-%20Maroochy%20Water%20Breach.md) — In the [Maroochy Water Breach](https://attack.mitre.org/campaigns/C0020), the adversary used a dedicated analog two-way radio system to send false data and instructions to pumping stations and the central computer.(Citation: Marshall Abrams July 2008) [Marshall Abrams July 2008](https://www.mitre.org/sites/default/files/pdf/08_1145.pdf)

## Mitigations

- [M0802 - Communication Authenticity](../../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for control functions should provide authenticity through MAC functions or digital signatures. If not, utilize bump-in-the-wire devices or VPNs to enforce communication authenticity between devices that are not capable of supporting this (e.g., legacy controllers, RTUs).
- [M0937 - Filter Network Traffic](../../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Perform inline allowlisting of automation protocol commands to prevent devices from sending unauthorized command or reporting messages. Allow/denylist techniques need to be designed with sufficient accuracy to prevent the unintended blocking of valid reporting messages.
- [M0807 - Network Allowlists](../../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational assets and their management devices based on their functional role within the process. Enabling more strict isolation to more critical control and operational information within the control environment.(Citation: Karen Scarfone; Paul Hoffman September 2009)(Citation: Keith Stouffer May 2015)(Citation: Department of Homeland Security September 2016)(Citation: Dwight Anderson 2014) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf) · [Dwight Anderson 2014](https://www.sans.org/reading-room/whitepapers/ICS/protect-critical-infrastructure-systems-whitelisting-35312) · [Karen Scarfone; Paul Hoffman September 2009](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-41r1.pdf) · [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
- [M0813 - Software Process and Device Authentication](../../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Devices should authenticate all messages between master and outstation assets.

## Targeted assets

- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Detection strategies

- [DET0746 - Detection of Spoof Reporting Message](../../../../Defenses/Detection%20Strategies/DET0746%20-%20Detection%20of%20Spoof%20Reporting%20Message.md)

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
