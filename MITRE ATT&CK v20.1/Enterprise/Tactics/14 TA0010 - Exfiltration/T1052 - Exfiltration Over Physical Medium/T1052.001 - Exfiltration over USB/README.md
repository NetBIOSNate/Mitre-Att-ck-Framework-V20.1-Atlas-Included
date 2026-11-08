# T1052.001 - Exfiltration over USB

[Enterprise](../../../../README.md) / [Exfiltration](../../README.md) / [T1052 - Exfiltration Over Physical Medium](../README.md)

Adversaries may attempt to exfiltrate data over a USB connected physical device. In certain circumstances, such as an air-gapped network compromise, exfiltration could occur via a USB device introduced by a user. The USB device could be used as the final exfiltration point or to hop between otherwise disconnected systems.(Citation: A USB data exfiltration case study)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1052/001)

**Tactics**  [Exfiltration](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0092 - Agent.btz](../../../../Threat%20Intelligence/Software/Malware/S0092%20-%20Agent.btz.md) — [Agent.btz](https://attack.mitre.org/software/S0092) creates a file named thumb.dd on all USB flash drives connected to the victim. This file contains information about the infected system and activity logs.(Citation: Securelist Agent.btz) [Securelist Agent.btz](https://securelist.com/agent-btz-a-source-of-inspiration/58551/)
- [S0409 - Machete](../../../../Threat%20Intelligence/Software/Malware/S0409%20-%20Machete.md) — [Machete](https://attack.mitre.org/software/S0409) has a feature to copy files from every drive onto a removable drive in a hidden folder.(Citation: ESET Machete July 2019)(Citation: Securelist Machete Aug 2014) [ESET Machete July 2019](https://www.welivesecurity.com/wp-content/uploads/2019/08/ESET_Machete.pdf) · [Securelist Machete Aug 2014](https://securelist.com/el-machete/66108/)
- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used a customized [PlugX](https://attack.mitre.org/software/S0013) variant which could exfiltrate documents from air-gapped networks.(Citation: Avira Mustang Panda January 2020) [Avira Mustang Panda January 2020](https://www.avira.com/en/blog/new-wave-of-plugx-targets-hong-kong)
- [S0125 - Remsec](../../../../Threat%20Intelligence/Software/Malware/S0125%20-%20Remsec.md) — [Remsec](https://attack.mitre.org/software/S0125) contains a module to move data from airgapped networks to Internet-connected systems by using a removable USB device.(Citation: Kaspersky ProjectSauron Full Report) [Kaspersky ProjectSauron Full Report](https://securelist.com/files/2016/07/The-ProjectSauron-APT_research_KL.pdf)
- [S0035 - SPACESHIP](../../../../Threat%20Intelligence/Software/Malware/S0035%20-%20SPACESHIP.md) — [SPACESHIP](https://attack.mitre.org/software/S0035) copies staged data to removable drives when they are inserted into the system.(Citation: FireEye APT30) [FireEye APT30](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2015/05/20081935/rpt-apt30.pdf)
- [G0081 - Tropic Trooper](../../../../Threat%20Intelligence/Groups/G0081%20-%20Tropic%20Trooper.md) — [Tropic Trooper](https://attack.mitre.org/groups/G0081) has exfiltrated data using USB storage devices.(Citation: TrendMicro Tropic Trooper May 2020) [TrendMicro Tropic Trooper May 2020](https://documents.trendmicro.com/assets/Tech-Brief-Tropic-Trooper-s-Back-USBferry-Attack-Targets-Air-gapped-Environments.pdf)
- [S0136 - USBStealer](../../../../Threat%20Intelligence/Software/Malware/S0136%20-%20USBStealer.md) — [USBStealer](https://attack.mitre.org/software/S0136) exfiltrates collected files via removable media from air-gapped victims.(Citation: ESET Sednit USBStealer 2014) [ESET Sednit USBStealer 2014](http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/)

## Mitigations

- [M1057 - Data Loss Prevention](../../../../Defenses/Mitigations/M1057%20-%20Data%20Loss%20Prevention.md) — Data loss prevention can detect and block sensitive data being copied to USB devices.
- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable Autorun if it is unnecessary. (Citation: Microsoft Disable Autorun) Disallow or restrict removable media at an organizational policy level if they are not required for business operations. (Citation: TechNet Removable Media Control) [Microsoft Disable Autorun](https://support.microsoft.com/en-us/kb/967715) · [TechNet Removable Media Control](https://technet.microsoft.com/en-us/library/cc772540%28v=ws.10%29.aspx)
- [M1034 - Limit Hardware Installation](../../../../Defenses/Mitigations/M1034%20-%20Limit%20Hardware%20Installation.md) — Limit the use of USB devices and removable media within a network.

## Detection strategies

- [DET0220 - Detection of USB-Based Data Exfiltration](../../../../Defenses/Detection%20Strategies/DET0220%20-%20Detection%20of%20USB-Based%20Data%20Exfiltration.md)

## Sources

- [A USB data exfiltration case study](https://www.cell.com/heliyon/fulltext/S2405-8440%2823%2900232-3)
