# T1563.002 - RDP Hijacking

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1563 - Remote Service Session Hijacking](../README.md)

Adversaries may hijack a legitimate user’s remote desktop session to move laterally within an environment. Remote desktop is a common feature in operating systems. It allows a user to log into an interactive session with a system desktop graphical user interface on a remote system. Microsoft refers to its implementation of the Remote Desktop Protocol (RDP) as Remote Desktop Services (RDS).(Citation: TechNet Remote Desktop Services)

Adversaries may perform RDP session hijacking which involves stealing a legitimate user's remote session. Typically, a user is notified when someone else is trying to steal their session. With System permissions and using Terminal Services Console, `c:\windows\system32\tscon.exe [session number to be stolen]`, an adversary can hijack a session without the need for credentials or prompts to the user.(Citation: RDP Hijacking Korznikov) This can be done remotely or locally and with active or disconnected sessions.(Citation: RDP Hijacking Medium) It can also lead to [Remote System Discovery](https://attack.mitre.org/techniques/T1018) and Privilege Escalation by stealing a Domain Admin or higher privileged account session. All of this can be done by using native Windows commands, but it has also been added as a feature in red teaming tools.(Citation: Kali Redsnarf)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1563/002)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0001 - Axiom](../../../../Threat%20Intelligence/Groups/G0001%20-%20Axiom.md) — [Axiom](https://attack.mitre.org/groups/G0001) has targeted victims with remote administration tools including RDP.(Citation: Novetta-Axiom) [Novetta-Axiom](https://web.archive.org/web/20230115144216/http://www.novetta.com/wp-content/uploads/2014/11/Executive_Summary-Final_1.pdf)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has conducted RDP session hijacking to gain access to victim devices.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [S0366 - WannaCry](../../../../Threat%20Intelligence/Software/Malware/S0366%20-%20WannaCry.md) — [WannaCry](https://attack.mitre.org/software/S0366) enumerates current remote desktop sessions and tries to execute the malware on each session.(Citation: LogRhythm WannaCry) [LogRhythm WannaCry](https://web.archive.org/web/20230522041200/https://logrhythm.com/blog/a-technical-analysis-of-wannacry-ransomware/)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Audit the Remote Desktop Users group membership regularly. Remove unnecessary accounts and groups from Remote Desktop Users groups.
- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable the RDP service if it is unnecessary.
- [M1035 - Limit Access to Resource Over Network](../../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Use remote desktop gateways.
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Enable firewall rules to block RDP traffic between network security zones within a network.
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Change GPOs to define shorter timeouts sessions and maximum amount of time any single session can be active. Change GPOs to specify the maximum amount of time that a disconnected session stays active on the RD session host server.(Citation: Windows RDP Sessions) [Windows RDP Sessions](https://technet.microsoft.com/en-us/library/cc754272%28v=ws.11%29.aspx)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Consider removing the local Administrators group from the list of groups allowed to log in through RDP.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit remote user permissions if remote access is necessary.

## Detection strategies

- [DET0588 - Detection of Remote Service Session Hijacking for RDP.](../../../../Defenses/Detection%20Strategies/DET0588%20-%20Detection%20of%20Remote%20Service%20Session%20Hijacking%20for%20RDP.md)

## Sources

- [RDP Hijacking Medium](https://medium.com/@networksecurity/rdp-hijacking-how-to-hijack-rds-and-remoteapp-sessions-transparently-to-move-through-an-da2a1e73a5f6)
- [RDP Hijacking Korznikov](http://www.korznikov.com/2017/03/0-day-or-feature-privilege-escalation.html)
- [TechNet Remote Desktop Services](https://technet.microsoft.com/en-us/windowsserver/ee236407.aspx)
- [Kali Redsnarf](https://github.com/nccgroup/redsnarf)
