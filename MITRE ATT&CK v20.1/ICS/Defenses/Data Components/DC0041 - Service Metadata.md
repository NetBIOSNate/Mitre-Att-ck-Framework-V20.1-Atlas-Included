# DC0041 - Service Metadata

[ICS](../../README.md) / [Data Components](README.md)

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

- [AN1897 - Analytic 1897](../Analytics/AN1897.md)
- [AN2268 - Analytic 2268](../Analytics/AN2268.md)
