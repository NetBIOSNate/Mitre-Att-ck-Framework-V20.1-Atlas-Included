# T0881 - Service Stop

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may stop or disable services on a system to render those services unavailable to legitimate users. Stopping critical services can inhibit or stop response to an incident or aid in the adversary's overall objectives to cause damage to the environment. (Citation: Enterprise ATT&CK)  Services may not allow for modification of their data stores while running. Adversaries may stop services in order to conduct Data Destruction. (Citation: Enterprise ATT&CK)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0881)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Mitigations

- [M0930 - Network Segmentation](../../../Defenses/Mitigations/M0930%20-%20Network%20Segmentation.md) — Segment operational network and systems to restrict access to critical system functions to predetermined management systems. (Citation: Department of Homeland Security September 2016) [Department of Homeland Security September 2016](https://us-cert.cisa.gov/sites/default/files/recommended_practices/NCCIC_ICS-CERT_Defense_in_Depth_2016_S508C.pdf)
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure proper process and file permissions are in place to inhibit adversaries from disabling or interfering with critical services.
- [M0924 - Restrict Registry Permissions](../../../Defenses/Mitigations/M0924%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper registry permissions are in place to inhibit adversaries from disabling or interfering with critical services.
- [M0918 - User Account Management](../../../Defenses/Mitigations/M0918%20-%20User%20Account%20Management.md) — Limit privileges of user accounts and groups so that only authorized administrators can change service states and configurations.

## Procedure examples

- [S0605 - EKANS](../../../Threat%20Intelligence/Software/Malware/S0605%20-%20EKANS.md) — Before encrypting the process, [EKANS](https://attack.mitre.org/software/S0605) first kills the process if its name matches one of the processes defined on the kill-list. (Citation: Daniel Kapellmann Zafra, Keith Lunden, Nathan Brubaker, Jeremy Kennelly July 2020) (Citation: Daniel Kapellmann Zafra, Keith Lunden, Nathan Brubaker, Jeremy Kennelly July 2020) EKANS also utilizes netsh commands to implement firewall rules that blocks any remote communication with the device. (Citation: Ben Hunter and Fred Gutierrez July 2020) [Ben Hunter and Fred Gutierrez July 2020](https://www.fortinet.com/blog/threat-research/ekans-ransomware-targeting-ot-ics-systems) · [Daniel Kapellmann Zafra, Keith Lunden, Nathan Brubaker, Jeremy Kennelly July 2020](https://www.fireeye.com/blog/threat-research/2020/02/ransomware-against-machine-learning-to-disrupt-industrial-production.html)
- [S0604 - Industroyer](../../../Threat%20Intelligence/Software/Malware/S0604%20-%20Industroyer.md) — [Industroyer](https://attack.mitre.org/software/S0604) has the capability to stop a service itself, or to login as a user and stop a service as that user. (Citation: Anton Cherepanov, ESET June 2017) [Anton Cherepanov, ESET June 2017](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [S1072 - Industroyer2](../../../Threat%20Intelligence/Software/Malware/S1072%20-%20Industroyer2.md) — [Industroyer2](https://attack.mitre.org/software/S1072) has the capability to terminate specified processes (i.e., PServiceControl.exe and PService_PDD.exe) and rename each process to prevent restart. These are defined through a hardcoded configuration.(Citation: Industroyer2 Mandiant April 2022) [Industroyer2 Mandiant April 2022](https://www.mandiant.com/resources/blog/industroyer-v2-old-malware-new-tricks)
- [S0607 - KillDisk](../../../Threat%20Intelligence/Software/Malware/S0607%20-%20KillDisk.md) — [KillDisk](https://attack.mitre.org/software/S0607) looks for and terminates two non-standard processes, one of which is an ICS application. (Citation: Anton Cherepanov) [Anton Cherepanov](https://www.welivesecurity.com/2016/01/03/blackenergy-sshbeardoor-details-2015-attacks-ukrainian-news-media-electric-industry/)
- [S0496 - REvil](../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) searches for all processes listed in the prc field within its configuration file and then terminates each process. (Citation: McAfee Labs October 2019) [McAfee Labs October 2019](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/mcafee-atr-analyzes-sodinokibi-aka-revil-ransomware-as-a-service-what-the-code-tells-us)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0005 - Intelligent Electronic Device (IED)](../../../Defenses/Assets/A0005%20-%20Intelligent%20Electronic%20Device%20%28IED%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Detection strategies

- [DET0765 - Detection of Service Stop](../../../Defenses/Detection%20Strategies/DET0765%20-%20Detection%20of%20Service%20Stop.md)

## Sources

- [Enterprise ATT&CK](https://attack.mitre.org/techniques/T1489/)
