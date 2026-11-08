# T0861 - Point & Tag Identification

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may collect point and tag values to gain a more comprehensive understanding of the process environment. Points may be values such as inputs, memory locations, outputs or other process specific variables. (Citation: Dennis L. Sloatman September 2016) Tags are the identifiers given to points for operator convenience. 

Collecting such tags provides valuable context to environmental points and enables an adversary to map inputs, outputs, and other values to their control processes. Understanding the points being collected may inform an adversary on which processes and values to keep track of over the course of an operation.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0861)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Procedure examples

- [S0093 - Backdoor.Oldrea](../../../Threat%20Intelligence/Software/Malware/S0093%20-%20Backdoor.Oldrea.md) — The [Backdoor.Oldrea](https://attack.mitre.org/software/S0093) payload has the capability of enumerating OPC tags, in addition to more generic OPC server information. The server data and tag names can provide information about the names and function of control devices. (Citation: ICS-CERT August 2018) (Citation: Daavid Hentunen, Antti Tikkanen June 2014) [Daavid Hentunen, Antti Tikkanen June 2014](https://www.f-secure.com/weblog/archives/00002718.html) · [ICS-CERT August 2018](https://ics-cert.us-cert.gov/advisories/ICSA-14-178-01)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can remotely read the OCP UA structure from devices.(Citation: CISA-AA22-103A) [CISA-AA22-103A](https://www.cisa.gov/uscert/ncas/alerts/aa22-103a)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Authenticate all access to field controllers before authorizing access to, or modification of, a device's state, logic, or programs. Centralized authentication techniques can help manage the large number of field controller accounts needed across the ICS.
- [M0800 - Authorization Enforcement](../../../Defenses/Mitigations/M0800%20-%20Authorization%20Enforcement.md) — Systems and devices should restrict access to any data with potential confidentiality concerns, including point and tag information.
- [M0802 - Communication Authenticity](../../../Defenses/Mitigations/M0802%20-%20Communication%20Authenticity.md) — Protocols used for control functions should provide authenticity through MAC functions or digital signatures. If not, utilize bump-in-the-wire devices or VPNs to enforce communication authenticity between devices that are not capable of supporting this (e.g., legacy controllers, RTUs).
- [M0937 - Filter Network Traffic](../../../Defenses/Mitigations/M0937%20-%20Filter%20Network%20Traffic.md) — Perform inline allowlisting of automation protocol commands to prevent devices from sending unauthorized command or reporting messages. Allow/denylist techniques need to be designed with sufficient accuracy to prevent the unintended blocking of valid messages.
- [M0804 - Human User Authentication](../../../Defenses/Mitigations/M0804%20-%20Human%20User%20Authentication.md) — All field controllers should require users to authenticate for all remote or local management sessions. The authentication mechanisms should also support [Account Use Policies](https://attack.mitre.org/mitigations/M0936), [Password Policies](https://attack.mitre.org/mitigations/M0927), and [User Account Management](https://attack.mitre.org/mitigations/M0918).
- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Use host-based allowlists to prevent devices from accepting connections from unauthorized systems. For example, allowlists can be used to ensure devices can only connect with master stations or known management/engineering workstations. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational assets and their management devices based on their functional role within the process. Enabling more strict isolation to more critical control and operational information within the control environment. (Citation: Karen Scarfone; Paul Hoffman September 2009) (Citation: Keith Stouffer May 2015) (Citation: Department of Homeland Security September 2016) (Citation: Dwight Anderson 2014) [Karen Scarfone; Paul Hoffman September 2009](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-41r1.pdf) · [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf) · [Dwight Anderson 2014](https://www.sans.org/reading-room/whitepapers/ICS/protect-critical-infrastructure-systems-whitelisting-35312)
- [M0813 - Software Process and Device Authentication](../../../Defenses/Mitigations/M0813%20-%20Software%20Process%20and%20Device%20Authentication.md) — Devices should authenticate all messages between master and outstation assets.

## Detection strategies

- [DET0788 - Detection of Point & Tag Identification](../../../Defenses/Detection%20Strategies/DET0788%20-%20Detection%20of%20Point%20%26%20Tag%20Identification.md)

## Targeted assets

- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Sources

- [Dennis L. Sloatman September 2016](https://www.radioworld.com/industry/understanding-plc-programming-methods-and-the-tag-database-system)
