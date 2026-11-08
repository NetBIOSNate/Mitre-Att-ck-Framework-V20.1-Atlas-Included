# T1695 - Block Communications

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Operational technology communications occur over serial COM, Ethernet, Wi-Fi, cellular (4G/5G), and satellite mediums. Adversaries may block communications to prevent reporting messages and command messages from reaching their intended target devices disrupting processes, operations, and causing cyber-physical impacts.(Citation: Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011)  

Adversaries may block communications by either making modifications to software ([System Firmware](https://attack.mitre.org/techniques/T0857), [Module Firmware](https://attack.mitre.org/techniques/T0839), [Hooking](https://attack.mitre.org/techniques/T0874), and [Rootkit](https://attack.mitre.org/techniques/T0851)) and services ([Service Stop](https://attack.mitre.org/techniques/T0881), [Denial of Service](https://attack.mitre.org/techniques/T0814)) on systems and devices or by positioning themselves between systems and devices and intercepting and blocking the communications such as the case with an [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T0830) attack.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1695)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1695.002 - Ethernet](T1695.002%20-%20Ethernet/README.md)
- [T1695.001 - Serial COM](T1695.001%20-%20Serial%20COM/README.md)
- [T1695.003 - Wi-Fi](T1695.003%20-%20Wi-Fi/README.md)

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

- [DET0910 - Detection of Block Communications](../../../Defenses/Detection%20Strategies/DET0910%20-%20Detection%20of%20Block%20Communications.md)

## Mitigations

- [M0807 - Network Allowlists](../../../Defenses/Mitigations/M0807%20-%20Network%20Allowlists.md) — Implement network allowlists to minimize network access to only authorized hosts.
- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational networks to isolate critical systems and devices that do not require broad network access.
- [M0810 - Out-of-Band Communications Channel](../../../Defenses/Mitigations/M0810%20-%20Out-of-Band%20Communications%20Channel.md) — Ensure systems and devices have an alternative method for communicating in the event that communication channels become unavailable.

## Procedure examples

- [G1027 - CyberAv3ngers](../../../Threat%20Intelligence/Groups/G1027%20-%20CyberAv3ngers.md) — During the [2026 Iranian Water Campaign](https://attack.mitre.org/campaigns/C0065), [CyberAv3ngers](https://attack.mitre.org/groups/G1027) locked out operators by changing the PLC’s IP address.(Citation: Tenable Minnesota Water Utilities) [Tenable Minnesota Water Utilities](https://www.tenable.com/blog/coordinated-cyberattack-on-minnesota-water-utilities-what-you-need-to-know)

## Sources

- [Bonnie Zhu, Anthony Joseph, Shankar Sastry 2011](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6142258)
