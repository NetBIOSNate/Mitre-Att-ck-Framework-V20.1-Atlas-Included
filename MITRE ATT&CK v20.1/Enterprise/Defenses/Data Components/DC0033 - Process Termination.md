# DC0033 - Process Termination

[Enterprise](../../README.md) / [Data Components](README.md)

The exit or termination of a running process on a system. This can occur due to normal operations, user-initiated commands, or malicious actions such as process termination by malware to disable security controls.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0033)

## Log sources and channels

- **Process** — None
- **WinEventLog:Sysmon** — EventCode=5
- **linux:syslog** — Unexpected termination of daemons or critical services not aligned with admin change tickets
- **macos:osquery** — process_termination: Unexpected termination of processes tied to vulnerable or high-value services
- **esxi:hostd** — Log entries indicating VM powered off or forcibly terminated
- **macos:unifiedlog** — Terminal process killed (killall Terminal) immediately after sudoers modification
- **auditd:SYSCALL** — exit_group
- **macos:unifiedlog** — process.*exit.*code
- **linux:osquery** — unexpected termination of syslog or rsyslog processes
- **auditd:SYSCALL** — Process segfault or abnormal termination after invoking vulnerable syscall sequence
- **auditd:SYSCALL** — kill syscalls targeting logging/security processes
- **macos:unifiedlog** — Termination of syspolicyd or XProtect processes
- **docker:runtime** — Termination of monitoring sidecar or security container
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): Industrial Control Systems (ICS) service process terminated (SIGKILL/SIGSEGV) following high-rate inbound connections recorded in netflow within the same window

## Analytics using this component

- [AN0045 - Analytic 0045](../Analytics/AN0045.md)
- [AN0046 - Analytic 0046](../Analytics/AN0046.md)
- [AN0047 - Analytic 0047](../Analytics/AN0047.md)
- [AN0064 - Analytic 0064](../Analytics/AN0064.md)
- [AN0143 - Analytic 0143](../Analytics/AN0143.md)
- [AN0373 - Analytic 0373](../Analytics/AN0373.md)
- [AN0374 - Analytic 0374](../Analytics/AN0374.md)
- [AN0413 - Analytic 0413](../Analytics/AN0413.md)
- [AN0668 - Analytic 0668](../Analytics/AN0668.md)
- [AN0851 - Analytic 0851](../Analytics/AN0851.md)
- [AN0887 - Analytic 0887](../Analytics/AN0887.md)
- [AN0888 - Analytic 0888](../Analytics/AN0888.md)
- [AN0889 - Analytic 0889](../Analytics/AN0889.md)
- [AN1369 - Analytic 1369](../Analytics/AN1369.md)
