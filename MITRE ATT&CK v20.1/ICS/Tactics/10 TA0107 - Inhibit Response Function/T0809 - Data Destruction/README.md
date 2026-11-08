# T0809 - Data Destruction

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may perform data destruction over the course of an operation. The adversary may drop or create malware, tools, or other non-native files on a target system to accomplish this, potentially leaving behind traces of malicious activities. Such non-native files and other data may be removed over the course of an intrusion to maintain a small footprint or as a standard part of the post-intrusion cleanup process. (Citation: Enterprise ATT&CK January 2018)

Data destruction may also be used to render operator interfaces unable to respond and to disrupt response functions from occurring as expected. An adversary may also destroy data backups that are vital to recovery after an incident.

Standard file deletion commands are available on most operating system and device interfaces to perform cleanup, but adversaries may use other tools as well. Two examples are Windows Sysinternals SDelete and Active@ Killdisk.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0809)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Detection strategies

- [DET0758 - Detection of Data Destruction](../../../Defenses/Detection%20Strategies/DET0758%20-%20Detection%20of%20Data%20Destruction.md)

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

## Mitigations

- [M0953 - Data Backup](../../../Defenses/Mitigations/M0953%20-%20Data%20Backup.md) — Utilize central storage servers for critical operations where possible (e.g., historians) and keep remote backups. For outstations, use local redundant storage for event recorders. Have backup control system platforms, preferably as hot-standbys to respond immediately to data destruction events. (Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0926 - Privileged Account Management](../../../Defenses/Mitigations/M0926%20-%20Privileged%20Account%20Management.md) — Minimize permissions and access for service accounts to limit the information that may be impacted by malicious users or software. (Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Protect files stored locally with proper permissions to limit opportunities for adversaries to impact data storage. (Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used DynoWiper and built-in commands to destroy data on Mikronika RTUs, Hitachi Relion Protection and Control Relays (IEDs), and HMI workstations.(Citation: CERT Polska) During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used LazyWiper to destroy data at a manufacturing sector company.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S1157 - Fuxnet](../../../Threat%20Intelligence/Software/Malware/S1157%20-%20Fuxnet.md) — [Fuxnet](https://attack.mitre.org/software/S1157) physically destroyed NAND memory chips on impacted devices through repeated bit-flip operations.(Citation: Claroty Fuxnet 2024) [Claroty Fuxnet 2024](https://claroty.com/team82/research/unpacking-the-blackjack-groups-fuxnet-malware)
- [S1045 - INCONTROLLER](../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can wipe the memory of Omron PLCs and reset settings through the remote HTTP service.(Citation: Brubaker-Incontroller)(Citation: Dragos-Pipedream)(Citation: Wylie-22) [Dragos-Pipedream](https://hub.dragos.com/hubfs/116-Whitepapers/Dragos_ChernoviteWP_v2b.pdf?hsLang=en) · [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf) · [Brubaker-Incontroller](https://www.mandiant.com/resources/incontroller-state-sponsored-ics-tool)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) has a destructive wiper that overwrites all ICS configuration files across the hard drives and all mapped network drives specifically targeting ABB PCM600 configuration files. (Citation: Dragos Inc. June 2017) [Dragos Inc. June 2017](https://dragos.com/blog/crashoverride/CrashOverride-01.pdf)
- [S0607 - KillDisk](../../../Threat%20Intelligence/Software/Malware/S0607%20-%20KillDisk.md) — [KillDisk](https://attack.mitre.org/software/S0607) is able to delete system files to make the system unbootable and targets 35 different types of files for deletion. (Citation: Anton Cherepanov) [Anton Cherepanov](https://www.welivesecurity.com/2016/01/03/blackenergy-sshbeardoor-details-2015-attacks-ukrainian-news-media-electric-industry/)

## Sources

- [Enterprise ATT&CK January 2018](https://attack.mitre.org/wiki/Technique/T1107)
