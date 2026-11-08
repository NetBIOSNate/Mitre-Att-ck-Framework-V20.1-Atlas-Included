# DC0041 - Service Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual data about a service/daemon, which may include information such as name, service executable, start type, etc.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0041)

## Log sources and channels

- **Service** — None
- **WinEventLog:Sysmon** — EventCode=4
- **linux:syslog** — service stopped messages
- **macos:unifiedlog** — launchctl disable or bootout calls
- **esxi:hostd** — Stop VM or disable service events via vim-cmd
- **linux:syslog** — auditd service stopped or disabled
- **macos:osquery** — launchd
- **linux:osquery** — scheduled/real-time
- **macos:unifiedlog** — subsystem=com.apple.launchservices
- **esxi:hostd** — registers services with legitimate-sounding names
- **WinEventLog:System** — EventCode=7035
- **linux:syslog** — Service restart with modified executable path
- **macos:unifiedlog** — Observed loading of new LaunchAgent or LaunchDaemon plist
- **kubernetes:audit** — seccomp or AppArmor profile changes
- **WinEventLog:System** — Service stopped or RecoveryDisabled set via REAgentC
- **esxi:hostd** — Service events
- **WinEventLog:WinRM** — EventCode=6
- **auditd:CONFIG_CHANGE** — delete: Modification of systemd unit files or config for security agents
- **macos:unifiedlog** — Modification of system configuration profiles affecting security tools
- **kubernetes:audit** — kubectl delete or patch of security pods/admission controllers
- **networkdevice:config** — write: Startup configuration changes disabling security checks
- **auditd:DAEMON** — auditd stopped, config changed, logging suspended
- **WinEventLog:System** — EventCode=7034, 7036 for Industrial Control Systems (ICS) service within detection window of connection flood
- **WinEventLog:System** — EventCode=7036 critical Industrial Control Systems (ICS) service transitions to Stopped without preceding change ticket reference

## Analytics using this component

- [AN0061 - Analytic 0061](../Analytics/AN0061.md)
- [AN0062 - Analytic 0062](../Analytics/AN0062.md)
- [AN0063 - Analytic 0063](../Analytics/AN0063.md)
- [AN0064 - Analytic 0064](../Analytics/AN0064.md)
- [AN0171 - Analytic 0171](../Analytics/AN0171.md)
- [AN0313 - Analytic 0313](../Analytics/AN0313.md)
- [AN0325 - Analytic 0325](../Analytics/AN0325.md)
- [AN0326 - Analytic 0326](../Analytics/AN0326.md)
- [AN0359 - Analytic 0359](../Analytics/AN0359.md)
- [AN0535 - Analytic 0535](../Analytics/AN0535.md)
- [AN0610 - Analytic 0610](../Analytics/AN0610.md)
- [AN0766 - Analytic 0766](../Analytics/AN0766.md)
- [AN0889 - Analytic 0889](../Analytics/AN0889.md)
- [AN0933 - Analytic 0933](../Analytics/AN0933.md)
- [AN0987 - Analytic 0987](../Analytics/AN0987.md)
- [AN1313 - Analytic 1313](../Analytics/AN1313.md)
- [AN1370 - Analytic 1370](../Analytics/AN1370.md)
- [AN1371 - Analytic 1371](../Analytics/AN1371.md)
- [AN1373 - Analytic 1373](../Analytics/AN1373.md)
- [AN1374 - Analytic 1374](../Analytics/AN1374.md)
- [AN2038 - Analytic 2038](../Analytics/AN2038.md)
- [AN2039 - Analytic 2039](../Analytics/AN2039.md)
