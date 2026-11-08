# DC0018 - Host Status

[Enterprise](../../README.md) / [Data Components](README.md)

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

- [AN0214 - Analytic 0214](../Analytics/AN0214.md)
- [AN0489 - Analytic 0489](../Analytics/AN0489.md)
- [AN0491 - Analytic 0491](../Analytics/AN0491.md)
- [AN0492 - Analytic 0492](../Analytics/AN0492.md)
- [AN0584 - Analytic 0584](../Analytics/AN0584.md)
- [AN0585 - Analytic 0585](../Analytics/AN0585.md)
- [AN0586 - Analytic 0586](../Analytics/AN0586.md)
- [AN0587 - Analytic 0587](../Analytics/AN0587.md)
- [AN0588 - Analytic 0588](../Analytics/AN0588.md)
- [AN0667 - Analytic 0667](../Analytics/AN0667.md)
- [AN0741 - Analytic 0741](../Analytics/AN0741.md)
- [AN0742 - Analytic 0742](../Analytics/AN0742.md)
- [AN0744 - Analytic 0744](../Analytics/AN0744.md)
- [AN0745 - Analytic 0745](../Analytics/AN0745.md)
- [AN0869 - Analytic 0869](../Analytics/AN0869.md)
- [AN0870 - Analytic 0870](../Analytics/AN0870.md)
- [AN0972 - Analytic 0972](../Analytics/AN0972.md)
- [AN1012 - Analytic 1012](../Analytics/AN1012.md)
- [AN1013 - Analytic 1013](../Analytics/AN1013.md)
- [AN1014 - Analytic 1014](../Analytics/AN1014.md)
- [AN1035 - Analytic 1035](../Analytics/AN1035.md)
- [AN1036 - Analytic 1036](../Analytics/AN1036.md)
- [AN1037 - Analytic 1037](../Analytics/AN1037.md)
- [AN1140 - Analytic 1140](../Analytics/AN1140.md)
- [AN1141 - Analytic 1141](../Analytics/AN1141.md)
- [AN1143 - Analytic 1143](../Analytics/AN1143.md)
- [AN1165 - Analytic 1165](../Analytics/AN1165.md)
- [AN1168 - Analytic 1168](../Analytics/AN1168.md)
- [AN1374 - Analytic 1374](../Analytics/AN1374.md)
- [AN1474 - Analytic 1474](../Analytics/AN1474.md)
- [AN1493 - Analytic 1493](../Analytics/AN1493.md)
- [AN1538 - Analytic 1538](../Analytics/AN1538.md)
- [AN1539 - Analytic 1539](../Analytics/AN1539.md)
- [AN1540 - Analytic 1540](../Analytics/AN1540.md)
- [AN1541 - Analytic 1541](../Analytics/AN1541.md)
- [AN1542 - Analytic 1542](../Analytics/AN1542.md)
