# T0872 - Indicator Removal on Host

[ICS](../../../README.md) / [Evasion](../README.md)

Adversaries may attempt to remove indicators of their presence on a system in an effort to cover their tracks. In cases where an adversary may feel detection is imminent, they may try to overwrite, delete, or cover up changes they have made to the device.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0872)

**Tactics**  [Evasion](../README.md)

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

## Procedure examples

- [S0607 - KillDisk](../../../Threat%20Intelligence/Software/Malware/S0607%20-%20KillDisk.md) — [KillDisk](https://attack.mitre.org/software/S0607) deletes application, security, setup, and system event logs from Windows systems. (Citation: Anton Cherepanov) [Anton Cherepanov](https://www.welivesecurity.com/2016/01/03/blackenergy-sshbeardoor-details-2015-attacks-ukrainian-news-media-electric-industry/)
- [S1009 - Triton](../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) would reset the controller to the previous state over TriStation and if this failed it would write a dummy program to memory in what was likely an attempt at anti-forensics. (Citation: Jos Wetzels January 2018) [Jos Wetzels January 2018](https://www.midnightbluelabs.com/blog/2018/1/16/analyzing-the-triton-industrial-malware)
- [C0030 - Triton Safety Instrumented System Attack](../../../Threat%20Intelligence/Campaigns/C0030%20-%20Triton%20Safety%20Instrumented%20System%20Attack.md) — In the [Triton Safety Instrumented System Attack](https://attack.mitre.org/campaigns/C0030), [TEMP.Veles](https://attack.mitre.org/groups/G0088) would programmatically return the controller to a normal running state if the [Triton](https://attack.mitre.org/software/S1009) malware failed. If the controller could not recover in a defined time window, [TEMP.Veles](https://attack.mitre.org/groups/G0088) programmatically overwrote their malicious program with invalid data.(Citation: FireEye TRITON Dec 2017) [FireEye TRITON Dec 2017](https://www.fireeye.com/blog/threat-research/2017/12/attackers-deploy-new-ics-attack-framework-triton.html)

## Mitigations

- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Protect files stored locally with proper permissions to limit opportunities for adversaries to remove indicators of their activity on the system. (Citation: Keith Stouffer May 2015) (Citation: National Institute of Standards and Technology April 2013) [Keith Stouffer May 2015](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-82r2.pdf) · [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)

## Detection strategies

- [DET0750 - Detection of Indicator Removal on Host](../../../Defenses/Detection%20Strategies/DET0750%20-%20Detection%20of%20Indicator%20Removal%20on%20Host.md)
