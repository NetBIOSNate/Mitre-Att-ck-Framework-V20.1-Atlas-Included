# DC0060 - Service Creation

[Enterprise](../../README.md) / [Data Components](README.md)

The registration of a new service or daemon on an operating system.

*Data Collection Measures:*

- Windows Event Logs
    - Event ID 4697 - Captures the creation of a new Windows service.
    - Event ID 7045 - Captures services installed by administrators or adversaries.
    - Event ID 7034 - Could indicate malicious service modification or exploitation.
- Sysmon Logs
    - Sysmon Event ID 1 - Process Creation (captures service executables).
    - Sysmon Event ID 4 - Service state changes (detects service installation).
    - Sysmon Event ID 13 - Registry modifications (captures service persistence changes).
- PowerShell Logging
    - Monitor `New-Service` and `Set-Service` PowerShell cmdlets in Event ID 4104 (Script Block Logging).
- Linux/macOS Collection Methods
    - AuditD & Syslog Daemon Logs (`/var/log/syslog`, `/var/log/messages`, `/var/log/daemon.log`)
    - AuditD Rules:
        - `auditctl -w /etc/systemd/system -p wa -k service_creation`
        - Detects changes to `systemd` service configurations.
- Systemd Journals (`journalctl -u <service_name>`)
    - Captures newly created systemd services.
- LaunchDaemons & LaunchAgents (macOS)
    - Monitor `/Library/LaunchDaemons/` and `/Library/LaunchAgents/` for new plist files.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0060)

## Log sources and channels

- **Service** — None
- **WinEventLog:System** — EventCode=7036
- **auditd:CONFIG_CHANGE** — creation or modification of systemd services
- **macos:osquery** — Process Events and Launch Daemons
- **WinEventLog:System** — EventCode=7045
- **linux:osquery** — newly registered unit file with ExecStart pointing to unknown binary
- **macos:unifiedlog** — creation or loading of new launchd services
- **WinEventLog:Security** — EventCode=4697
- **linux:syslog** — systemctl start/enable with uncommon binary paths
- **WinEventLog:System** — EventCode=7031, 7034
- **macos:osquery** — launch_daemons
- **macos:unifiedlog** — launchd loading new LaunchDaemon or changes to existing daemon configuration
- **macos:osquery** — detection of new launch agents with suspicious paths or unsigned binaries
- **kubernetes:audit** — create
- **containerLogs:systemd_unit_files** — unit file referencing container binary with persistent flags
- **WinEventLog:System** — EventCode=7045 where ServiceName/ImagePath references Industrial Control Systems (ICS) vendor application with hash/path mismatch
- **WinEventLog:System** — EventCode=7045 enabling Transmission Control Protocol (TCP) port forwarding on Industrial Control Systems (ICS) protocol port not in known ICS services

## Analytics using this component

- [AN0061 - Analytic 0061](../Analytics/AN0061.md)
- [AN0200 - Analytic 0200](../Analytics/AN0200.md)
- [AN0206 - Analytic 0206](../Analytics/AN0206.md)
- [AN0243 - Analytic 0243](../Analytics/AN0243.md)
- [AN0274 - Analytic 0274](../Analytics/AN0274.md)
- [AN0324 - Analytic 0324](../Analytics/AN0324.md)
- [AN0355 - Analytic 0355](../Analytics/AN0355.md)
- [AN0462 - Analytic 0462](../Analytics/AN0462.md)
- [AN0701 - Analytic 0701](../Analytics/AN0701.md)
- [AN0736 - Analytic 0736](../Analytics/AN0736.md)
- [AN0778 - Analytic 0778](../Analytics/AN0778.md)
- [AN0779 - Analytic 0779](../Analytics/AN0779.md)
- [AN0850 - Analytic 0850](../Analytics/AN0850.md)
- [AN0868 - Analytic 0868](../Analytics/AN0868.md)
- [AN0875 - Analytic 0875](../Analytics/AN0875.md)
- [AN0886 - Analytic 0886](../Analytics/AN0886.md)
- [AN0909 - Analytic 0909](../Analytics/AN0909.md)
- [AN1061 - Analytic 1061](../Analytics/AN1061.md)
- [AN1063 - Analytic 1063](../Analytics/AN1063.md)
- [AN1126 - Analytic 1126](../Analytics/AN1126.md)
- [AN1185 - Analytic 1185](../Analytics/AN1185.md)
- [AN1208 - Analytic 1208](../Analytics/AN1208.md)
- [AN1211 - Analytic 1211](../Analytics/AN1211.md)
- [AN1274 - Analytic 1274](../Analytics/AN1274.md)
- [AN1304 - Analytic 1304](../Analytics/AN1304.md)
- [AN1366 - Analytic 1366](../Analytics/AN1366.md)
- [AN1369 - Analytic 1369](../Analytics/AN1369.md)
- [AN1527 - Analytic 1527](../Analytics/AN1527.md)
- [AN1575 - Analytic 1575](../Analytics/AN1575.md)
- [AN1620 - Analytic 1620](../Analytics/AN1620.md)
- [AN2043 - Analytic 2043](../Analytics/AN2043.md)
