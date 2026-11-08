# DC0035 - Process Access

[Mobile](../../README.md) / [Data Components](README.md)

Refers to an event where one process attempts to open another process, typically to inspect or manipulate its memory, access handles, or modify execution flow. Monitoring these access attempts can provide valuable insight into both benign and malicious behaviors, such as debugging, inter-process communication (IPC), or process injection.

*Data Collection Measures:*

- Endpoint Detection and Response (EDR) Tools:
    -  EDR solutions that provide telemetry on inter-process access and memory manipulation.
- Sysmon (Windows):
    - Event ID 10: Captures process access attempts, including:
        - Source process (initiator)
        - Target process (victim)
        - Access rights requested
        - Process ID correlation
- Windows Event Logs:
    - Event ID 4656 (Audit Handle to an Object): Logs access attempts to system objects.
    - Event ID 4690 (Attempted Process Modification): Can help identify unauthorized process changes.
- Linux/macOS Monitoring:
    - AuditD: Monitors process access through syscall tracing (e.g., `ptrace`, `open`, `read`, `write`).
    - eBPF/XDP: Used for low-level monitoring of kernel process access.
    - OSQuery: Query process access behavior via structured SQL-like logging.
- Procmon (Process Monitor) and Debugging Tools:
    - Windows Procmon: Captures real-time process interactions.
    - Linux strace / ptrace: Useful for tracking process behavior at the system call level.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0035)

## Log sources and channels

- **android:logcat** — Runtime grant or manifest presence for MANAGE_EXTERNAL_STORAGE/READ_EXTERNAL_STORAGE/READ_MEDIA_*; legacy external storage mode detection
- **android:logcat** — Activity/Process state change (mFocusedApp, onResume/onPause) identifying <pkg> as foreground
- **android:logcat** — Grant/activation of BIND_ACCESSIBILITY_SERVICE, BIND_INPUT_METHOD, SYSTEM_ALERT_WINDOW, POST_NOTIFICATIONS for <pkg>
- **android:logcat** — Grant/enablement for BIND_ACCESSIBILITY_SERVICE or BIND_INPUT_METHOD for <pkg>
- **android:logcat** — Grant/enablement of SYSTEM_ALERT_WINDOW, BIND_ACCESSIBILITY_SERVICE, POST_NOTIFICATIONS for <pkg>
- **android:logcat** — Reads/queries ops for PACKAGE_USAGE_STATS, QUERY_ALL_PACKAGES, BIND_DEVICE_ADMIN, BIND_VPN_SERVICE
- **Apple TCC Logs** — Microphone Access Events
- **auditd:SYSCALL** — ptrace attach
- **auditd:SYSCALL** — High frequency of accept(), read(), or SSL_read() syscalls tied to nginx/apache processes
- **auditd:SYSCALL** — ptrace
- **auditd:SYSCALL** — ptrace syscall or access to /proc/*/mem
- **auditd:SYSCALL** — ACCESS
- **auditd:SYSCALL** — execve, fork, mmap, ptrace
- **auditd:SYSCALL** — ptrace or process_vm_readv
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): syscall=ptrace/process_vm_readv; process accesses an ICS service process PID from an image or UID not in the debugger/diagnostic allowlist
- **EDR:telemetry** — Sustained or high-frequency location sensor access, including background location usage
- **iOS:unifiedlog** — Code signing validation events referencing newly written local Mach-O/bundle prior to exec or dlopen
- **iOS:unifiedlog** — Privacy (TCC) prompts/grants for Photos/Files or access changes indicating new visibility into user/app data
- **iOS:unifiedlog** — Foreground/background transition for <bundle_id> to contextualize access timing
- **iOS:unifiedlog** — Keyboard extension Full Access change; privacy grant touching input/keyboard categories for <bundle_id>
- **iOS:unifiedlog** — Keyboard extension Full Access change or related privacy grant for <bundle_id>
- **iOS:unifiedlog** — Scene/foreground transitions for <bundle_id> to contextualize timing
- **linux:osquery** — Process State
- **linux:osquery** — process_events
- **linux:syslog** — syscalls (open, read, ioctl) on /dev/input or /proc/*/fd/*
- **macos:endpointsecurity** — ES_EVENT_TYPE_NOTIFY_OPEN
- **macos:osquery** — process_open
- **macos:osquery** — unexpected memory inspection
- **macos:unifiedlog** — ptrace or task_for_pid
- **macos:unifiedlog** — Unexpected NSXPCConnection calls by non-Apple-signed or abnormal binaries
- **macos:unifiedlog** — Unusual Mach port registration or access attempts between unrelated processes
- **macos:unifiedlog** — subsystem=com.apple.security, library=libsystem_kernel.dylib
- **macos:unifiedlog** — vm_read, task_for_pid, or file open to cookie databases
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: accessibility_service or notification_listener appears attributed to a bundle IN $LegitimateSystemProcesses$ within $InjectionWindow$ of root detection — injected code requesting special permissions under a legitimate system process identit
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: kernel log entry at level=fault referencing task_for_pid or get-task-allow violation on SUPERVISED device with Unified Log forwarding — kernel records entitlement violations at fault level; requires supervised MDM with Unified Log export
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: process in $TargetProcessList$ shows unexpected behavior change (new network destinations, new permission accesses) within $InjectionWindow$ of root status change — behavioral delta in target process post-injection is the anomaly indicator
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: kernel log at level=fault referencing task_for_pid, mach_vm_write, or get-task-allow outside developer build on SUPERVISED device — Apple Unified Log kernel subsystem records these violations at fault level; supervised MDM with Unified Log
- **WinEventLog:Security** — EventCode=4663, 4670, 4656
- **WinEventLog:Sysmon** — EventCode=10
- **WinEventLog:Sysmon** — EventCode=25
- **WinEventLog:Sysmon** — EventCode=10 where SourceImage outside the approved ICS vendor/process baseline accesses TargetImage associated with an ICS application or service
- **WinEventLog:Sysmon** — EventCode=10 cross-process memory access into Industrial Control Systems (ICS) vendor process from image not in trusted security tool list, followed by unexpected termination within exploit crash correlation window

## Analytics using this component

- [AN1685 - Analytic 1685](../Analytics/AN1685.md)
- [AN1686 - Analytic 1686](../Analytics/AN1686.md)
- [AN1703 - Analytic 1703](../Analytics/AN1703.md)
- [AN1704 - Analytic 1704](../Analytics/AN1704.md)
