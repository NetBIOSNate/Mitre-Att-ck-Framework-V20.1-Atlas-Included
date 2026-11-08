# T1692 - Unauthorized Message

[ICS](../../../README.md) / [Impair Process Control](../README.md)

Adversaries may send unauthorized messages to ICS systems and devices to evade defenses or manipulate processes. Unauthorized messages can be categorized as either reporting messages that contain telemetry data about the current state of systems, devices, and processes or as command messages which instruct systems and devices on how to operate. By injecting unauthorized messages, adversaries can make it appear as if everything is working correctly when it isn’t, trigger alarms to misdirect personnel or impact processes, and manipulate controls to disrupt processes.(Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)

Adversaries may send unauthorized messages in an ICS environment using software found within the environment (living-off-the-land, vendor-specific interfaces, etc.), custom tooling leveraging OT protocols and libraries, or by positioning themselves between systems and devices and injecting messages into the communications such as the case with an [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T0830) attack.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1692)

**Tactics**  [Evasion](../../05%20TA0103%20-%20Evasion/README.md), [Impair Process Control](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Sub-techniques

- [T1692.001 - Command Message](T1692.001%20-%20Command%20Message/README.md)
- [T1692.002 - Reporting Message](T1692.002%20-%20Reporting%20Message/README.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Detection strategies

- [DET0902 - Detection of Unauthorized Message](../../../Defenses/Detection%20Strategies/DET0902%20-%20Detection%20of%20Unauthorized%20Message.md)

## Mitigations

- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for control functions should provide authenticity through MAC functions or digital signatures. If not, utilize bump-in-the-wire devices or VPNs to enforce communication authenticity between devices that are not capable of supporting this (e.g., legacy controllers, RTUs).
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Perform inline allowlisting of automation protocol commands to prevent devices from sending unauthorized command or reporting messages. Allow/denylist techniques need to be designed with sufficient accuracy to prevent the unintended blocking of valid messages.
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations.(Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational assets and their management devices based on their functional role within the process. Enabling more strict isolation to more critical control and operational information within the control environment.(Citation: Karen Scarfone; Paul Hoffman September 2009)(Citation: Keith Stouffer May 2015)(Citation: Department of Homeland Security September 2016)(Citation: Dwight Anderson 2014) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf) · [Dwight Anderson 2014](https://www.sans.org/reading-room/whitepapers/ICS/protect-critical-infrastructure-systems-whitelisting-35312) · [Karen Scarfone; Paul Hoffman September 2009](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-41r1.pdf) · [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Devices should authenticate all messages between master and outstation assets.

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
