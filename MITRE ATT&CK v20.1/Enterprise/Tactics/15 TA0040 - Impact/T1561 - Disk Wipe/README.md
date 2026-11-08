# T1561 - Disk Wipe

[Enterprise](../../../README.md) / [Impact](../README.md)

Adversaries may wipe or corrupt raw disk data on specific systems or in large numbers in a network to interrupt availability to system and network resources. With direct write access to a disk, adversaries may attempt to overwrite portions of disk data. Adversaries may opt to wipe arbitrary portions of disk data and/or wipe disk structures like the master boot record (MBR). A complete wipe of all disk sectors may be attempted.

To maximize impact on the target organization in operations where network-wide availability interruption is the goal, malware used for wiping disks may have worm-like features to propagate across a network by leveraging additional techniques like [Valid Accounts](https://attack.mitre.org/techniques/T1078), [OS Credential Dumping](https://attack.mitre.org/techniques/T1003), and [SMB/Windows Admin Shares](https://attack.mitre.org/techniques/T1021/002).(Citation: Novetta Blockbuster Destructive Malware)

On network devices, adversaries may wipe configuration files and other data from the device using [Network Device CLI](https://attack.mitre.org/techniques/T1059/008) commands such as `erase`.(Citation: erase_cmd_cisco)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1561)

**Tactics**  [Impact](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1561.001 - Disk Content Wipe](T1561.001%20-%20Disk%20Content%20Wipe/README.md)
- [T1561.002 - Disk Structure Wipe](T1561.002%20-%20Disk%20Structure%20Wipe/README.md)

## Detection strategies

- [DET0137 - Detection Strategy for Disk Wipe via Direct Disk Access and Destructive Commands](../../../Defenses/Detection%20Strategies/DET0137%20-%20Detection%20Strategy%20for%20Disk%20Wipe%20via%20Direct%20Disk%20Access%20and%20Destructive%20Commands.md)

## Mitigations

- [M1053 - Data Backup](../../../Defenses/Mitigations/M1053%20-%20Data%20Backup.md) — Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.(Citation: Ready.gov IT DRP) Ensure backups are stored off system and is protected from common methods adversaries may use to gain access and destroy the backups to prevent recovery. [Ready.gov IT DRP](https://www.ready.gov/business/implementation/IT)

## Sources

- [erase_cmd_cisco](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/fundamentals/command/cf_command_ref/D_through_E.html#wp3557227463)
- [Novetta Blockbuster Destructive Malware](https://web.archive.org/web/20160303200515/https:/operationblockbuster.com/wp-content/uploads/2016/02/Operation-Blockbuster-Destructive-Malware-Report.pdf)
- [Microsoft Sysmon v6 May 2017](https://docs.microsoft.com/sysinternals/downloads/sysmon)
