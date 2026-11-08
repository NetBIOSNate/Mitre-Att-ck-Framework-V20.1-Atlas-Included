# T1518.002 - Backup Software Discovery

[Enterprise](../../../../README.md) / [Discovery](../../README.md) / [T1518 - Software Discovery](../README.md)

Adversaries may attempt to get a listing of backup software or configurations that are installed on a system. Adversaries may use this information to shape follow-on behaviors, such as [Data Destruction](https://attack.mitre.org/techniques/T1485), [Inhibit System Recovery](https://attack.mitre.org/techniques/T1490), or [Data Encrypted for Impact](https://attack.mitre.org/techniques/T1486).  

Commands that can be used to obtain security software information are [netsh](https://attack.mitre.org/software/S0108), `reg query` with [Reg](https://attack.mitre.org/software/S0075), `dir` with [cmd](https://attack.mitre.org/software/S0106), and [Tasklist](https://attack.mitre.org/software/S0057), but other indicators of discovery behavior may be more specific to the type of software or security system the adversary is looking for, such as Veeam, Acronis, Dropbox, or Paragon.(Citation: Symantec Play Ransomware 2023)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1518/002)

**Tactics**  [Discovery](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md), [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0088 - Backup Software Discovery via CLI, Registry, and Process Inspection (T1518.002)](../../../../Defenses/Detection%20Strategies/DET0088%20-%20Backup%20Software%20Discovery%20via%20CLI%2C%20Registry%2C%20and%20Process%20Inspection%20%28T1518.002%29.md)

## Procedure examples

- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has utilized the PowerShell script `Get-DataInfo.ps1` to collect installed backup software information from a compromised machine.(Citation: Mandiant FIN12 Oct 2021) [Mandiant FIN12 Oct 2021](https://web.archive.org/web/20220313061955/https://www.mandiant.com/sites/default/files/2021-10/fin12-group-profile.pdf)

## Sources

- [Symantec Play Ransomware 2023](https://www.security.com/threat-intelligence/play-ransomware-volume-shadow-copy)
