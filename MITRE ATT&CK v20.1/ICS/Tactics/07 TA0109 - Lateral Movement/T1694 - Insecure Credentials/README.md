# T1694 - Insecure Credentials

[ICS](../../../README.md) / [Lateral Movement](../README.md)

Adversaries may target insecure credentials as a means to persist on a system or device or move laterally from one system or device to another. Insecure credentials may appear as default credentials which are pre-configured credentials on a system, device, or software that are well-known in documentation or hard-coded credentials which are built into the system, device, or software that cannot be changed or not easily changed because of the impact on control processes.(Citation: NIST SP 800-82r3)(Citation: ICS-ALERT-13-164-01)(Citation: OT IceFall)
 Adversaries often times use insecure credentials to evade detection as they are typically forgotten about by system and device owners.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1694)

**Tactics**  [Persistence](../../03%20TA0110%20-%20Persistence/README.md), [Lateral Movement](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1694.001 - Default Credentials](T1694.001%20-%20Default%20Credentials/README.md)
- [T1694.002 - Hardcoded Credentials](T1694.002%20-%20Hardcoded%20Credentials/README.md)

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
- [A0014 - Routers](../../../Defenses/Assets/A0014%20-%20Routers.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0905 - Detection of Insecure Credentials](../../../Defenses/Detection%20Strategies/DET0905%20-%20Detection%20of%20Insecure%20Credentials.md)

## Mitigations

- [M0801 - Access Management](../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Ensure embedded controls and network devices are protected through access management, as these devices often have insecure credentials which could be used to gain unauthorized access.

## Sources

- [ICS-ALERT-13-164-01](https://www.cisa.gov/news-events/ics-alerts/ics-alert-13-164-01)
- [OT IceFall](https://www.forescout.com/resources/ot-icefall-report/)
- [NIST SP 800-82r3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r3.pdf)
