# S9002 - Diskpart

[Enterprise](../../../README.md) / [Tools](README.md)

[Diskpart](https://attack.mitre.org/software/S9002) is a Windows command-line utility that is used to manage the computer’s drives, which includes disks, partitions, volumes and virtual hard disks.(Citation: Microsoft_diskpart_Feb2023)  

Adversaries may abuse [Diskpart](https://attack.mitre.org/software/S9002) to perform discovery and destructive actions on a system’s storage. For example, adversaries have been observed using [Diskpart](https://attack.mitre.org/software/S9002) to conduct [Discovery](https://attack.mitre.org/tactics/TA0007) techniques to enumerate disks and volumes to gather information about the host environment, and to execute commands such as `clean all` to remove partition information and overwrite data across disks, resulting in data destruction.(Citation: Trendmicro_RansomHub_Dec2024)

[MITRE ATT&CK record](https://attack.mitre.org/software/S9002)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1561.002 - Disk Structure Wipe](../../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.002%20-%20Disk%20Structure%20Wipe/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1059.003 - Windows Command Shell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1222.001 - Windows Permissions](../../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/T1222.001%20-%20Windows%20Permissions/README.md)

## Sources

- [Microsoft_diskpart_Feb2023](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/diskpart)
- [Trendmicro_RansomHub_Dec2024](https://www.trendmicro.com/vinfo/us/security/news/ransomware-spotlight/ransomware-spotlight-ransomhub)
