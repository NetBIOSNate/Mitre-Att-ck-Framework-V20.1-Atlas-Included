# DC0042 - Drive Creation

[ICS](../../README.md) / [Data Components](README.md)

The activity of assigning a new drive letter or creating a mount point for a data storage device, such as a USB, network share, or external hard drive, enabling access to its content on a host system. Examples: 

- USB Drive Insertion: A USB drive is plugged in and automatically assigned the letter `E:\` on a Windows machine.
- Network Drive Mapping: A network share `\\server\share` is mapped to the drive `Z:\`.
- Virtual Drive Creation: A virtual disk is mounted on `/mnt/virtualdrive` using an ISO image or a virtual hard disk (VHD).
- Cloud Storage Mounting: Google Drive is mounted as `G:\` on a Windows machine using a cloud sync tool.
- External Storage Integration: An external HDD or SSD is connected and assigned `/mnt/external` on a Linux system..

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0042)

## Log sources and channels

- **auditd:SYSCALL** — mknod,open,openat
- **auditd:SYSCALL** — Removable media mount notification
- **auditd:SYSCALL** — device event logs
- **auditd:SYSCALL** — udev events or drive enumeration involving TinyPilot paths or device classes
- **auditd:SYSCALL** — Kernel Device Events - USB Block Devices
- **Drive** — None
- **journald:systemd** — udisks2 or udevd logs
- **linux:osquery** — mount_events
- **linux:syslog** — Device attach logs containing TinyPilot/PiKVM identifiers
- **linux:syslog** — New HID device enumeration with type 'keyboard' followed by immediate input injection
- **macos:unifiedlog** — mounted|appeared|DA: disk* attached
- **macos:unifiedlog** — com.apple.diskarbitration
- **macos:unifiedlog** — Volume Mount + File Read
- **macos:unifiedlog** — Hardware enumeration events via IOKit or USBMuxd showing TinyPilot or unknown keyboard/mouse
- **macos:unifiedlog** — Volume Mount + Process Trace + File Read
- **macos:unifiedlog** — log stream --predicate 'eventMessage contains "USBMSC"'
- **macos:unifiedlog** — New IOUSB keyboard/HID device enumerated with suspicious attributes
- **macos:osquery** — mount_events
- **WinEventLog:System** — Kernel-PnP 410/400 device install, disk added
- **WinEventLog:System** — EventCode=1006
- **WinEventLog:System** — EventCode=1006, 10001
- **WinEventLog:System** — EventCode=2003
- **WinEventLog:System** — EventCode=20001, 2003 not in authorized Universal Serial Bus (USB) allowlist on Industrial Control Systems (ICS) host
- **WinEventLog:System** — EventCode=20001 correlated with autorun registry modification within autorun modification window

## Analytics using this component

- [AN1866 - Analytic 1866](../Analytics/AN1866.md)
- [AN2273 - Analytic 2273](../Analytics/AN2273.md)
