# DC0020 - Process Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to a running process, such as writing data into memory, modifying execution behavior, or injecting code into an existing process. Adversaries frequently modify processes to execute malicious payloads, evade detection, or gain escalated privileges.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0020)

## Log sources and channels

- **auditd:SYSCALL** — rename, chmod
- **auditd:SYSCALL** — mprotect
- **macos:endpointsecurity** — ES_EVENT_MMAP
- **auditd:SYSCALL** — kill syscalls targeting auditd process
- **macos:unifiedlog** — memory mapping
- **WinEventLog:Sysmon** — EventCode=8
- **macos:osquery** — Memory Mappings
- **ebpf:tracepoints** — Runtime memory overwrite of argv[] memory region
- **etw:Microsoft-Windows-Kernel-Process** — Memory Modification / Unmapped module load or suspicious RWX allocations in the process space of a browser process
- **macos:unifiedlog** — Anomalous dyld dynamic library loads or RWX memory mappings in browser process
- **auditd:SYSCALL** — open, rename
- **auditd:SYSCALL** — SYSCALL ptrace/mprotect
- **macos:endpointsecurity** — ES_EVENT_TYPE_NOTIFY_MMAP
- **macos:unifiedlog** — process, library load, memory operations
- **auditd:SYSCALL** — rename
- **linux:osquery** — Detection of bitwise operations or custom encryption functions in memory traces
- **macos:unifiedlog** — Abnormal memory operations (XOR/bitwise loops) during archive generation
- **auditd:memprotect** — change from PROT_READ|PROT_WRITE to PROT_EXEC
- **linux:procfs** — /proc/[pid]/maps, /proc/[pid]/mem

## Analytics using this component

- [AN0022 - Analytic 0022](../Analytics/AN0022.md)
- [AN0067 - Analytic 0067](../Analytics/AN0067.md)
- [AN0068 - Analytic 0068](../Analytics/AN0068.md)
- [AN0171 - Analytic 0171](../Analytics/AN0171.md)
- [AN0239 - Analytic 0239](../Analytics/AN0239.md)
- [AN0277 - Analytic 0277](../Analytics/AN0277.md)
- [AN0297 - Analytic 0297](../Analytics/AN0297.md)
- [AN0389 - Analytic 0389](../Analytics/AN0389.md)
- [AN0391 - Analytic 0391](../Analytics/AN0391.md)
- [AN0466 - Analytic 0466](../Analytics/AN0466.md)
- [AN0498 - Analytic 0498](../Analytics/AN0498.md)
- [AN0500 - Analytic 0500](../Analytics/AN0500.md)
- [AN0541 - Analytic 0541](../Analytics/AN0541.md)
- [AN0822 - Analytic 0822](../Analytics/AN0822.md)
- [AN0914 - Analytic 0914](../Analytics/AN0914.md)
- [AN0915 - Analytic 0915](../Analytics/AN0915.md)
- [AN0921 - Analytic 0921](../Analytics/AN0921.md)
- [AN0941 - Analytic 0941](../Analytics/AN0941.md)
- [AN0984 - Analytic 0984](../Analytics/AN0984.md)
- [AN1076 - Analytic 1076](../Analytics/AN1076.md)
- [AN1214 - Analytic 1214](../Analytics/AN1214.md)
- [AN1215 - Analytic 1215](../Analytics/AN1215.md)
- [AN1241 - Analytic 1241](../Analytics/AN1241.md)
- [AN1289 - Analytic 1289](../Analytics/AN1289.md)
- [AN1398 - Analytic 1398](../Analytics/AN1398.md)
- [AN1400 - Analytic 1400](../Analytics/AN1400.md)
- [AN1481 - Analytic 1481](../Analytics/AN1481.md)
- [AN1535 - Analytic 1535](../Analytics/AN1535.md)
- [AN1551 - Analytic 1551](../Analytics/AN1551.md)
