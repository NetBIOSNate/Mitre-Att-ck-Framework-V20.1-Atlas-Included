# T1695.002 - Ethernet

[ICS](../../../../README.md) / [Inhibit Response Function](../../README.md) / [T1695 - Block Communications](../README.md)

Adversaries may block access to Ethernet communications to prevent instructions or configurations messages from reaching target systems and devices. Ethernet connections allow for communications between IT and OT systems and devices. Blocking Ethernet communications may also block command and reporting messages.(Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)

An adversary may block Ethernet communications by disabling network interfaces, [Service Stop](https://attack.mitre.org/techniques/T0881), or conducting an [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T0830) attack and dropping the network traffic.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1695/002)

**Tactics**  [Inhibit Response Function](../../README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md), [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0017 - Distributed Control System (DCS) Controller](../../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0013 - Field I/O](../../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)
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

- [S0372 - LockerGoga](../../../../Threat%20Intelligence/Software/Malware/S0372%20-%20LockerGoga.md) — [LockerGoga](https://attack.mitre.org/software/S0372) had blocked network communications by disabling all the network interfaces on the system via netsh.exe.(Citation: LockerGoga Revisited)(Citation: Kevin Beaumont)(Citation: Detecting LockerGoga) [LockerGoga Revisited](https://www.dragos.com/blog/industry-news/spyware-stealer-locker-wiper-lockergoga-revisited/) · [Kevin Beaumont](https://doublepulsar.com/how-lockergoga-took-down-hydro-ransomware-used-in-targeted-attacks-aimed-at-big-business-c666551f5880) · [Detecting LockerGoga](https://www.securonix.com/wp-content/uploads/2021/07/Securonix-Threat-Research-Report-Detecting-LockerGoga.pdf)

## Mitigations

- [M0807 - Network Allowlists](../../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Implement network allowlists to minimize network access to only authorized hosts.
- [M0930 - Network Segmentation](../../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational networks to isolate critical systems and devices that do not require broad network access.
- [M0810 - Out-of-Band Communications Channel](../../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Ensure systems and devices have an alternative method for communicating in the event that Ethernet communication channels become unavailable.

## Detection strategies

- [DET0911 - Detection of Block Ethernet](../../../../Defenses/Detection%20Strategies/DET0911%20-%20Detection%20of%20Block%20Ethernet.md)

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
