# DC0054 - Drive Access

[Enterprise](../../README.md) / [Data Components](README.md)

Refers to the act of accessing a data storage device, such as a hard drive, SSD, USB, or network-mounted drive. This data component logs the opening or mounting of drives, capturing activities such as reading, writing, or executing files within an assigned drive letter (e.g., `C:\`, `/mnt/drive`) or mount point. Examples: 

- Removable Drive Insertion: A USB drive is inserted, assigned the letter `F:\`, and files are accessed.
- Network Drive Mounting: A network share `\\server\share` is mapped to the drive `Z:\`.
- External Hard Drive Access: An external drive is connected, mounted at `/mnt/backup`, and accessed for copying files.
- System Volume Access: The system volume `C:\` is accessed for modifications to critical files.
- Cloud-Synced Drives: Cloud storage drives like OneDrive or Google Drive are accessed via local mounts.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0054)

## Log sources and channels

- **WinEventLog:Sysmon** — EventCode=9
- **auditd:SYSCALL** — open/write syscalls on /dev/sd* or /dev/nvme*
- **auditd:SYSCALL** — write syscalls to /dev/sd* targeting offset 0
- **auditd:SYSCALL** — open/write syscalls to block devices (/dev/sd*, /dev/nvme*)
- **linux:syslog** — mount/umount or file copy logs
- **fs:fsusage** — open/read/mount operations
- **linux:osquery** — hardware_events
- **macos:osquery** — usb_devices

## Analytics using this component

- [AN0275 - Analytic 0275](../Analytics/AN0275.md)
- [AN0385 - Analytic 0385](../Analytics/AN0385.md)
- [AN0428 - Analytic 0428](../Analytics/AN0428.md)
- [AN0774 - Analytic 0774](../Analytics/AN0774.md)
- [AN0828 - Analytic 0828](../Analytics/AN0828.md)
- [AN0883 - Analytic 0883](../Analytics/AN0883.md)
- [AN1146 - Analytic 1146](../Analytics/AN1146.md)
- [AN1147 - Analytic 1147](../Analytics/AN1147.md)
- [AN1354 - Analytic 1354](../Analytics/AN1354.md)
- [AN1355 - Analytic 1355](../Analytics/AN1355.md)
