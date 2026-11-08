# DC0040 - File Deletion

[Mobile](../../README.md) / [Data Components](README.md)

Refers to events where files are removed from a system or storage device. These events can indicate legitimate housekeeping activities or malicious actions such as attackers attempting to cover their tracks. Monitoring file deletions helps organizations identify unauthorized or suspicious activities.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0040)

## Log sources and channels

- **File** — None
- **auditd:SYSCALL** — unlink/unlinkat on service binaries or data targets
- **auditd:SYSCALL** — file deletion
- **macos:osquery** — file_events
- **esxi:shell** — shell history
- **WinEventLog:Sysmon** — EventCode=23
- **auditd:SYSCALL** — PATH
- **esxi:shell** — /var/log/shell.log
- **esxi:hostd** — delete action
- **auditd:SYSCALL** — unlink, unlinkat, openat, write
- **macos:unifiedlog** — exec rm -rf|dd if=/dev|srm|file unlink
- **auditd:SYSCALL** — unlink, unlinkat, rmdir
- **auditd:SYSCALL** — unlink, rename, open
- **linux:Sysmon** — EventCode=23
- **fs:fsusage** — unlink, fs_delete
- **docker:daemon** — container file operations
- **esxi:hostd** — rm, clearlogs, logrotate
- **esxi:hostd** — Datastore file operations
- **macos:osquery** — CREATE, DELETE, WRITE: Stored data manipulation attempts by unauthorized processes
- **auditd:SYSCALL** — unlink/unlinkat
- **WinEventLog:Microsoft-Windows-Backup** — Windows Backup Catalog deletion or catalog corruption
- **auditd:CONFIG_CHANGE** — /etc/fstab, /etc/systemd/*
- **MobileEDR:telemetry** — application deletes, alters, renames, relocates, or suppresses local artifacts relevant to detection, including files, hidden media, compromise markers, or app-local evidence, before later continued execution or transfer
- **MobileEDR:telemetry** — application deletes package files, cleanup artifacts, or app-local state immediately before disappearance from installed inventory or runtime
- **MobileEDR:telemetry** — application deletes, truncates, or removes user, operational, or evidence-bearing files after prior access or staging and before later continued execution or communication
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: App deletes, truncates, or removes files that were recently written by the same app (collected data, staged exfil artifacts, operation logs) within $PostExfilCleanupWindow$ of network upload event — post-exfil cleanup chain
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: App deletes package files or local state immediately before package inventory disappearance — pre-removal evidence cleanup
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: unlink() or rmdir() on path IN /data/data/ OR /data/user/ OR /sdcard/ by process NOT IN $MDMAgentPackageList$ at rate > $DeletionRateThreshold$ within $DestructionWindow$
- **auditd:SYSCALL+PATH** — Linux Audit SYSCALL+PATH records: truncate/shred/rm on Industrial Control Systems (ICS) application log files or auth.log by User Identifier (UID) not in authorized log admin UIDs
- **auditd:SYSCALL+PATH** — Linux Audit SYSCALL+PATH records: rm/shred/dd operations across multiple Industrial Control Systems (ICS) data directories exceeding bulk deletion threshold, by User Identifier (UID) not in authorized data management UIDs
- **WinEventLog:Sysmon** — EventCode=23 across multiple Industrial Control Systems (ICS) data directories exceeding bulk deletion threshold within data destruction time window, by process not in authorized data management tools
- **WinEventLog:Sysmon** — EventCode=23 or wevtutil/Clear-EventLog invocation deleting Industrial Control Systems (ICS) vendor application log file by process not in authorized log management tools
- **WinEventLog:System** — EventCode=104 outside scheduled log rotation window

## Analytics using this component

- [AN1712 - Analytic 1712](../Analytics/AN1712.md)
- [AN1769 - Analytic 1769](../Analytics/AN1769.md)
- [AN1801 - Analytic 1801](../Analytics/AN1801.md)
