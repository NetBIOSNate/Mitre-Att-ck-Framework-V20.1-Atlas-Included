# DC0018 - Host Status

[Mobile](../../README.md) / [Data Components](README.md)

Logging, messaging, and other artifacts that highlight the health and operational state of host-based security sensors, such as Endpoint Detection and Response (EDR) agents, antivirus software, logging services, and system monitoring tools. Monitoring sensor health is essential for detecting misconfigurations, sensor failures, tampering, or deliberate security control evasion by adversaries.

*Data Collection Measures:*

- Windows Event Logs:
    - Event ID 1074 (System Shutdown): Detects unexpected system reboots/shutdowns.
    - Event ID 6006 (Event Log Stopped): Logs when Windows event logging is stopped.
    - Event ID 16 (Sysmon): Detects configuration state changes that may indicate log tampering.
    - Event ID 12 (Windows Defender Status Change) – Detects changes in Windows Defender state.
- Linux/macOS Monitoring:
    - `/var/log/syslog`, `/var/log/auth.log`, `/var/log/kern.log`
    - Journald (journalctl) for kernel and system alerts.
- Endpoint Detection and Response (EDR) Tools:
    - Monitor agent health status, detect sensor tampering, and alert on missing telemetry.
- Mobile Threat Intelligence Logs:
    - Samsung Knox, SafetyNet, iOS Secure Enclave provide sensor health status for mobile endpoints.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0018)

## Log sources and channels

- **iOS:MDMLog** — jailbreak_status=true on device where Keychain path file access was observed — stock iOS Keychain sandbox prevents direct file access; jailbreak is the prerequisite
- **android:appops** — ACCESS_FINE_LOCATION|NEARBY_DEVICES|BLUETOOTH_SCAN used in close proximity to network-context queries
- **AndroidAttestation:SafetyNet** — SafetyNet attestation with CTSProfileMatch=false or BasicIntegrity=false
- **AndroidAttestation:VerifiedBoot** — Verified Boot or dm-verity reports partition hash mismatch, non-green boot state, or integrity failure
- **AndroidLogs:Crash** — Crash or abnormal restart of privileged system services (for example, system_server, mediaserver, installd) followed shortly by new privileged process activity or binder connections from a single app UID
- **AndroidLogs:Crash** — Application or system process crash/restart patterns temporally associated with remote service communications
- **auditd:SYSCALL** — firmware_update, kexec_load
- **AWS:CloudMetrics** — Autoscaling, memory/cpu alarms, or instance unhealthiness
- **AWS:CloudWatch** — Sustained spike in CPU usage on EC2 instance with web service role
- **AWS:CloudWatch** — StatusCheckFailed or StatusCheckFailed_System for burstable instances (t2/t3)
- **AWS:CloudWatch** — Sustained EC2 CPU usage above normal baseline
- **AWS:CloudWatch** — NetworkOut spike beyond baseline
- **AWS:CloudWatch** — Sudden spike in network output without a corresponding inbound request ratio
- **AWS:CloudWatch** — Unusual CPU burst or metric anomalies
- **esxi:hostd** — Powering off or restarting host
- **iOS:MDMLog** — Device risk, compliance, or security posture changes after trusted host pairing or developer-state transition
- **iOS:unifiedlog** — code signature validation failure / exec of invalidly-signed payload from sandboxed app
- **iOS:unifiedlog** — Application crash logs, watchdog terminations, or abnormal execution events associated with service communication
- **journald:boot** — Secure Boot failure, firmware version change
- **kubernetes:events** — CrashLoopBackOff, OOMKilled, container restart count exceeds threshold
- **linux:procfs** — Sustained high /proc/[pid]/stat usage
- **linux:syslog** — Out of memory killer invoked or kernel panic entries
- **linux:syslog** — Service stop or disable messages for security tools not reflected in SIEM alerts
- **linux:syslog** — system is powering down
- **macos:osquery** — interface_details 
- **macos:syslog** — Hardware UUID or device list drift
- **macos:unifiedlog** — Web service process (e.g., httpd) entering crash loop or consuming excessive CPU
- **macos:unifiedlog** — Spike in CPU or memory use from non-user-initiated processes
- **macos:unifiedlog** — Termination or disabling of XProtect, Gatekeeper, or third-party AV daemons
- **macos:unifiedlog** — network stack resource exhaustion, tcp_accept queue overflow, repeated resets
- **macos:unifiedlog** — EFI firmware integrity check failed
- **macos:unifiedlog** — System Integrity Protection (SIP) state reported as disabled
- **macos:unifiedlog** — System shutdown or reboot requested
- **MDM:DeviceIntegrity** — jailbreak/root compromise indicators or integrity attestation failures enabling process visibility
- **networkdevice:syslog** — no logging host, no aaa new-model, no snmp-server, commit
- **networkdevice:syslog** — System reboot scheduled or performed
- **NSM:Flow** — TCP: possible SYN flood or backlog limit exceeded
- **OEMAttestation:Knox** — Samsung Knox attestation shows attestation_state=COMPROMISED or warranty bit set
- **prometheus:metrics** — Container CPU/Memory usage exceeding threshold
- **sar:network** — Outbound network saturation with minimal process activity
- **Sensor Health** — None
- **Windows:perfmon** — Sustained CPU/memory exhaustion by service process (e.g., w3wp.exe)
- **Windows:perfmon** — High sustained CPU usage by a single process
- **Windows:perfmon** — Sudden spike in outbound throughput without corresponding inbound traffic
- **Windows:perfmon** — Sudden spikes in CPU/Memory usage linked to specific application processes
- **WinEventLog:Microsoft-Windows-TCPIP** — Connection queue overflow or failure to allocate TCP state object
- **WinEventLog:Security** — EventCode=1166, 7045
- **WinEventLog:Security** — EventCode=1074
- **WinEventLog:Security** — EventCode=6006
- **WinEventLog:Sysmon** — EventCode=16
- **WinEventLog:System** — System shutdowns due to bugcheck (Event ID 1001) or watchdog timer expirations
- **android:DevicePolicyManager** — DevicePolicyManager policy/compliance/security-state queries and SecurityLog events where supported
- **iOS:MDM** — DeviceInformation / SecurityInfo / ProfileList / restrictions and compliance queries

## Analytics using this component

- [AN1651 - Analytic 1651](../Analytics/AN1651.md)
- [AN1655 - Analytic 1655](../Analytics/AN1655.md)
- [AN1684 - Analytic 1684](../Analytics/AN1684.md)
- [AN1685 - Analytic 1685](../Analytics/AN1685.md)
- [AN1686 - Analytic 1686](../Analytics/AN1686.md)
- [AN1695 - Analytic 1695](../Analytics/AN1695.md)
- [AN1696 - Analytic 1696](../Analytics/AN1696.md)
- [AN1699 - Analytic 1699](../Analytics/AN1699.md)
- [AN1700 - Analytic 1700](../Analytics/AN1700.md)
- [AN1703 - Analytic 1703](../Analytics/AN1703.md)
- [AN1704 - Analytic 1704](../Analytics/AN1704.md)
- [AN1705 - Analytic 1705](../Analytics/AN1705.md)
- [AN1707 - Analytic 1707](../Analytics/AN1707.md)
- [AN1739 - Analytic 1739](../Analytics/AN1739.md)
- [AN1740 - Analytic 1740](../Analytics/AN1740.md)
- [AN1747 - Analytic 1747](../Analytics/AN1747.md)
- [AN1748 - Analytic 1748](../Analytics/AN1748.md)
- [AN1757 - Analytic 1757](../Analytics/AN1757.md)
- [AN1758 - Analytic 1758](../Analytics/AN1758.md)
- [AN1759 - Analytic 1759](../Analytics/AN1759.md)
- [AN1760 - Analytic 1760](../Analytics/AN1760.md)
- [AN1761 - Analytic 1761](../Analytics/AN1761.md)
- [AN1789 - Analytic 1789](../Analytics/AN1789.md)
- [AN1796 - Analytic 1796](../Analytics/AN1796.md)
- [AN1803 - Analytic 1803](../Analytics/AN1803.md)
- [AN1805 - Analytic 1805](../Analytics/AN1805.md)
- [AN1835 - Analytic 1835](../Analytics/AN1835.md)
- [AN1836 - Analytic 1836](../Analytics/AN1836.md)
- [AN1839 - Analytic 1839](../Analytics/AN1839.md)
