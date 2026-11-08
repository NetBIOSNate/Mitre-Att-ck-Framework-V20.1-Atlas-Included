# T1092 - Communication Through Removable Media

[Enterprise](../../../README.md) / [Command and Control](../README.md)

Adversaries can perform command and control between compromised hosts on potentially disconnected networks using removable media to transfer commands from system to system.(Citation: ESET Sednit USBStealer 2014) Both systems would need to be compromised, with the likelihood that an Internet-connected system was compromised first and the second through lateral movement by [Replication Through Removable Media](https://attack.mitre.org/techniques/T1091). Commands and files would be relayed from the disconnected system to the Internet-connected system to which the adversary has direct access.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1092)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) uses a tool that captures information from air-gapped computers via an infected USB and transfers it to network-connected computer when the USB is inserted.(Citation: Microsoft SIR Vol 19) [Microsoft SIR Vol 19](http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf)
- [S0023 - CHOPSTICK](../../../Threat%20Intelligence/Software/Malware/S0023%20-%20CHOPSTICK.md) — Part of [APT28](https://attack.mitre.org/groups/G0007)'s operation involved using [CHOPSTICK](https://attack.mitre.org/software/S0023) modules to copy itself to air-gapped machines, using files written to USB sticks to transfer data and command traffic.(Citation: FireEye APT28)(Citation: ESET Sednit Part 2)(Citation: Microsoft SIR Vol 19) [Microsoft SIR Vol 19](http://download.microsoft.com/download/4/4/C/44CDEF0E-7924-4787-A56A-16261691ACE3/Microsoft_Security_Intelligence_Report_Volume_19_English.pdf) · [ESET Sednit Part 2](http://www.welivesecurity.com/wp-content/uploads/2016/10/eset-sednit-part-2.pdf) · [FireEye APT28](https://web.archive.org/web/20151022204649/https://www.fireeye.com/content/dam/fireeye-www/global/en/current-threats/pdfs/rpt-apt28.pdf)
- [S0136 - USBStealer](../../../Threat%20Intelligence/Software/Malware/S0136%20-%20USBStealer.md) — [USBStealer](https://attack.mitre.org/software/S0136) drops commands for a second victim onto a removable media drive inserted into the first victim, and commands are executed when the drive is inserted into the second victim.(Citation: ESET Sednit USBStealer 2014) [ESET Sednit USBStealer 2014](http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/)

## Detection strategies

- [DET0090 - Cross-host C2 via Removable Media Relay](../../../Defenses/Detection%20Strategies/DET0090%20-%20Cross-host%20C2%20via%20Removable%20Media%20Relay.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable Autoruns if it is unnecessary.(Citation: Microsoft Disable Autorun) [Microsoft Disable Autorun](https://support.microsoft.com/en-us/kb/967715)
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Disallow or restrict removable media at an organizational policy level if they are not required for business operations.(Citation: TechNet Removable Media Control) [TechNet Removable Media Control](https://technet.microsoft.com/en-us/library/cc772540%28v=ws.10%29.aspx)

## Sources

- [ESET Sednit USBStealer 2014](http://www.welivesecurity.com/2014/11/11/sednit-espionage-group-attacking-air-gapped-networks/)
