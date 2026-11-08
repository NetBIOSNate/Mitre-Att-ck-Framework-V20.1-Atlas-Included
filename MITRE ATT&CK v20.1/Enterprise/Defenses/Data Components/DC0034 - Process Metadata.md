# DC0034 - Process Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual data about a running process, which may include information such as environment variables, image name, user/owner, etc.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0034)

## Log sources and channels

- **WinEventLog:PowerShell** — EventCode=400/403; engine lifecycle/context
- **auditd:SYSCALL** — execve call for sudo where euid != uid
- **auditd:SYSCALL** — Use of fork/exec with DISPLAY unset or redirected
- **auditd:SYSCALL** — execve, prctl, or ptrace activity affecting process memory or command-line arguments
- **auditd:SYSCALL** — execve with UID ≠ EUID
- **auditd:SYSCALL** — execve with escalated privileges
- **AWS:CloudTrail** — cross-account or unexpected assume role
- **containerd:events** — Docker or containerd image pulls and process executions
- **EDR:hunting** — Correlation of signer info, parent-child lineage, rare invocation context (user host role), and API surfaces (CreateProcess*, LoadLibrary*)
- **EDR:Telemetry** — Process lineage and API usage enrichment (GetSystemTime, GetTimeZoneInformation, NtQuerySystemTime)
- **esxi:auth** — user session
- **esxi:hostd** — /var/log/hostd.log API calls reading/altering time/ntp settings
- **etw:Microsoft-Windows-ClickOnce** — provider: Event Tracing for Windows (ETW) events associated with ClickOnce deployment (dfsvc.exe activity)
- **etw:Microsoft-Windows-Kernel-Process** — process_start: EventHeader.ProcessId true parent vs reported PPID mismatch
- **linux:osquery** — Cross-reference argv[0] with actual executable path and parent process metadata
- **linux:osquery** — select: path LIKE '/dev/video%'
- **linux:osquery** — state=attached/debugged
- **linux:osquery** — process metadata mismatch between /proc and runtime attributes
- **linux:osquery** — process environment variables containing LD_PRELOAD
- **linux:syslog** — sudo or service accounts invoking loaders with suspicious env vars
- **linux:syslog** — Kernel or daemon warnings of downgraded TLS or cryptographic settings
- **macos:endpointsecurity** — ES_EVENT_TYPE_NOTIFY_EXEC, ES_EVENT_TYPE_NOTIFY_MMAP
- **macos:osquery** — Process Context
- **macos:osquery** — Process Execution + Hash
- **macos:unifiedlog** — subsystem=com.apple.process
- **macos:unifiedlog** — subsystem=com.apple.TCC
- **macos:unifiedlog** — exec of binary with setuid/setgid and EUID != UID
- **macos:unifiedlog** — process
- **macos:unifiedlog** — Code Execution & Entitlement Access
- **macos:unifiedlog** — Process opening SSH_AUTH_SOCK or /tmp/ssh-* socket not owned by same UID
- **macos:unifiedlog** — code signature/memory protection
- **macos:unifiedlog** — log collect from launchd and process start
- **macos:unifiedlog** — Modifications or writes to EFI system partition for downgraded bootloaders
- **macos:unifiedlog** — non-shell process tree accessing bash history
- **macos:unifiedlog** — Crash or abnormal termination of security agent or system extension host
- **networkdevice:syslog** — Admin activity
- **Process** — None
- **WinEventLog:AppLocker** — AppLocker audit/blocks showing developer utilities executing scripts/binaries outside policy
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — CodeIntegrity/WDAC events indicating unsigned/invalid DLL loads
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — Unsigned/invalid signature modules or images loaded by msbuild.exe or its children
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — Unsigned or untrusted modules loaded during JamPlus.exe runtime
- **WinEventLog:Microsoft-Windows-DeviceGuard/Operational** — WDAC policy audit/block affecting msbuild.exe spawned payloads
- **WinEventLog:Microsoft-Windows-Security-Mitigations/KernelMode** — ETW telemetry indicating ClickOnce deployment (dfsvc.exe) launching payloads
- **WinEventLog:Microsoft-Windows-SmartAppControl/Operational** — Smart App Control decisions (audit/block) for msbuild.exe-launched executables
- **WinEventLog:Microsoft-Windows-Windows Camera Frame Server/Operational** — Process session start/stop events for camera pipeline by unexpected executables
- **WinEventLog:PowerShell** — EventCode=400, 403
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: running process names read from /proc/<PID>/status or /proc/<PID>/cmdline by app NOT IN $ProcessDiscoveryAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: process executing with effective UID=0
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): execve with env containing LD_PRELOAD where exe matches Industrial Control Systems (ICS) service binary list and preload library not in vendor package manifest
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): execve where exe basename matches Industrial Control Systems (ICS) daemon names but path outside vendor install paths
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): execve of wireless configuration utility setting monitor/promiscuous mode outside change management window
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): setuid/setgid to root from a process owned by Industrial Control Systems (ICS) service User Identifier (UID) that was not invoked via sudo
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): execve of wireless configuration utility setting monitor mode on Industrial Control Systems (ICS) Linux asset by User Identifier (UID) not in authorized wireless admin UIDs
- **edr:ProcessIntegrity** — Process integrity/hash mismatch detected on Industrial Control Systems (ICS) communication process post-hook-install event
- **WinEventLog:Sysmon** — EventCode=1 where image filename matches Industrial Control Systems (ICS) vendor process names but hash not in vendor hash baseline or current directory outside vendor install paths

## Analytics using this component

- [AN0013 - Analytic 0013](../Analytics/AN0013.md)
- [AN0052 - Analytic 0052](../Analytics/AN0052.md)
- [AN0053 - Analytic 0053](../Analytics/AN0053.md)
- [AN0097 - Analytic 0097](../Analytics/AN0097.md)
- [AN0098 - Analytic 0098](../Analytics/AN0098.md)
- [AN0099 - Analytic 0099](../Analytics/AN0099.md)
- [AN0142 - Analytic 0142](../Analytics/AN0142.md)
- [AN0245 - Analytic 0245](../Analytics/AN0245.md)
- [AN0284 - Analytic 0284](../Analytics/AN0284.md)
- [AN0308 - Analytic 0308](../Analytics/AN0308.md)
- [AN0357 - Analytic 0357](../Analytics/AN0357.md)
- [AN0361 - Analytic 0361](../Analytics/AN0361.md)
- [AN0430 - Analytic 0430](../Analytics/AN0430.md)
- [AN0433 - Analytic 0433](../Analytics/AN0433.md)
- [AN0466 - Analytic 0466](../Analytics/AN0466.md)
- [AN0488 - Analytic 0488](../Analytics/AN0488.md)
- [AN0550 - Analytic 0550](../Analytics/AN0550.md)
- [AN0568 - Analytic 0568](../Analytics/AN0568.md)
- [AN0569 - Analytic 0569](../Analytics/AN0569.md)
- [AN0579 - Analytic 0579](../Analytics/AN0579.md)
- [AN0650 - Analytic 0650](../Analytics/AN0650.md)
- [AN0711 - Analytic 0711](../Analytics/AN0711.md)
- [AN0921 - Analytic 0921](../Analytics/AN0921.md)
- [AN0976 - Analytic 0976](../Analytics/AN0976.md)
- [AN0977 - Analytic 0977](../Analytics/AN0977.md)
- [AN0979 - Analytic 0979](../Analytics/AN0979.md)
- [AN0985 - Analytic 0985](../Analytics/AN0985.md)
- [AN0986 - Analytic 0986](../Analytics/AN0986.md)
- [AN0996 - Analytic 0996](../Analytics/AN0996.md)
- [AN0997 - Analytic 0997](../Analytics/AN0997.md)
- [AN1086 - Analytic 1086](../Analytics/AN1086.md)
- [AN1196 - Analytic 1196](../Analytics/AN1196.md)
- [AN1209 - Analytic 1209](../Analytics/AN1209.md)
- [AN1252 - Analytic 1252](../Analytics/AN1252.md)
- [AN1296 - Analytic 1296](../Analytics/AN1296.md)
- [AN1351 - Analytic 1351](../Analytics/AN1351.md)
- [AN1401 - Analytic 1401](../Analytics/AN1401.md)
- [AN1535 - Analytic 1535](../Analytics/AN1535.md)
- [AN1610 - Analytic 1610](../Analytics/AN1610.md)
- [AN2040 - Analytic 2040](../Analytics/AN2040.md)
