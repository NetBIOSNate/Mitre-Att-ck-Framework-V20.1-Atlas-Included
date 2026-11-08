# DC0040 - File Deletion

[Enterprise](../../README.md) / [Data Components](README.md)

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

- [AN0062 - Analytic 0062](../Analytics/AN0062.md)
- [AN0114 - Analytic 0114](../Analytics/AN0114.md)
- [AN0115 - Analytic 0115](../Analytics/AN0115.md)
- [AN0116 - Analytic 0116](../Analytics/AN0116.md)
- [AN0392 - Analytic 0392](../Analytics/AN0392.md)
- [AN0393 - Analytic 0393](../Analytics/AN0393.md)
- [AN0395 - Analytic 0395](../Analytics/AN0395.md)
- [AN0411 - Analytic 0411](../Analytics/AN0411.md)
- [AN0412 - Analytic 0412](../Analytics/AN0412.md)
- [AN0413 - Analytic 0413](../Analytics/AN0413.md)
- [AN0416 - Analytic 0416](../Analytics/AN0416.md)
- [AN0467 - Analytic 0467](../Analytics/AN0467.md)
- [AN0469 - Analytic 0469](../Analytics/AN0469.md)
- [AN0470 - Analytic 0470](../Analytics/AN0470.md)
- [AN0520 - Analytic 0520](../Analytics/AN0520.md)
- [AN0521 - Analytic 0521](../Analytics/AN0521.md)
- [AN0522 - Analytic 0522](../Analytics/AN0522.md)
- [AN0523 - Analytic 0523](../Analytics/AN0523.md)
- [AN0524 - Analytic 0524](../Analytics/AN0524.md)
- [AN0555 - Analytic 0555](../Analytics/AN0555.md)
- [AN0557 - Analytic 0557](../Analytics/AN0557.md)
- [AN0737 - Analytic 0737](../Analytics/AN0737.md)
- [AN0738 - Analytic 0738](../Analytics/AN0738.md)
- [AN0739 - Analytic 0739](../Analytics/AN0739.md)
- [AN0933 - Analytic 0933](../Analytics/AN0933.md)
- [AN0934 - Analytic 0934](../Analytics/AN0934.md)
- [AN1216 - Analytic 1216](../Analytics/AN1216.md)
- [AN1438 - Analytic 1438](../Analytics/AN1438.md)
- [AN1472 - Analytic 1472](../Analytics/AN1472.md)
