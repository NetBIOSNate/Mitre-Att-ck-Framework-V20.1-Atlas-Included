# DC0042 - Drive Creation

[Enterprise](../../README.md) / [Data Components](README.md)

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

- [AN0185 - Analytic 0185](../Analytics/AN0185.md)
- [AN0186 - Analytic 0186](../Analytics/AN0186.md)
- [AN0187 - Analytic 0187](../Analytics/AN0187.md)
- [AN0247 - Analytic 0247](../Analytics/AN0247.md)
- [AN0248 - Analytic 0248](../Analytics/AN0248.md)
- [AN0249 - Analytic 0249](../Analytics/AN0249.md)
- [AN0342 - Analytic 0342](../Analytics/AN0342.md)
- [AN0343 - Analytic 0343](../Analytics/AN0343.md)
- [AN0344 - Analytic 0344](../Analytics/AN0344.md)
- [AN0446 - Analytic 0446](../Analytics/AN0446.md)
- [AN0447 - Analytic 0447](../Analytics/AN0447.md)
- [AN0448 - Analytic 0448](../Analytics/AN0448.md)
- [AN0616 - Analytic 0616](../Analytics/AN0616.md)
- [AN0617 - Analytic 0617](../Analytics/AN0617.md)
- [AN0618 - Analytic 0618](../Analytics/AN0618.md)
- [AN0841 - Analytic 0841](../Analytics/AN0841.md)
- [AN1410 - Analytic 1410](../Analytics/AN1410.md)
- [AN1411 - Analytic 1411](../Analytics/AN1411.md)
- [AN1412 - Analytic 1412](../Analytics/AN1412.md)
- [AN1567 - Analytic 1567](../Analytics/AN1567.md)
- [AN1568 - Analytic 1568](../Analytics/AN1568.md)
- [AN1569 - Analytic 1569](../Analytics/AN1569.md)
