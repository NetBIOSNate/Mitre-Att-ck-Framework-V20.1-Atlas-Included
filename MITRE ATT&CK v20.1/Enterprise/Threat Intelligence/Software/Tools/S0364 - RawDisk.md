# S0364 - RawDisk

[Enterprise](../../../README.md) / [Tools](README.md)

[RawDisk](https://attack.mitre.org/software/S0364) is a legitimate commercial driver from the EldoS Corporation that is used for interacting with files, disks, and partitions. The driver allows for direct modification of data on a local computer's hard drive. In some cases, the tool can enact these raw disk modifications from user-mode processes, circumventing Windows operating system security features.(Citation: EldoS RawDisk ITpro)(Citation: Novetta Blockbuster Destructive Malware)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0364)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Used by

- [C0038 - HomeLand Justice](../../Campaigns/C0038%20-%20HomeLand%20Justice.md)
- [G0032 - Lazarus Group](../../Groups/G0032%20-%20Lazarus%20Group.md)

## Techniques used

- [T1485 - Data Destruction](../../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/README.md)
- [T1561.001 - Disk Content Wipe](../../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.001%20-%20Disk%20Content%20Wipe/README.md)
- [T1561.002 - Disk Structure Wipe](../../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.002%20-%20Disk%20Structure%20Wipe/README.md)

## Sources

- [EldoS RawDisk ITpro](https://www.itprotoday.com/windows-78/eldos-provides-raw-disk-access-vista-and-xp)
- [Novetta Blockbuster Destructive Malware](https://web.archive.org/web/20160303200515/https:/operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf)
