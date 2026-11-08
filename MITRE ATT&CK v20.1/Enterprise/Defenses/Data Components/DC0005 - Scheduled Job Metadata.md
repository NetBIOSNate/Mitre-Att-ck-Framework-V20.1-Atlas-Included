# DC0005 - Scheduled Job Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual data about a scheduled job, which may include information such as name, timing, command(s), etc.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0005)

## Log sources and channels

- **Scheduled Job** — None
- **linux:cron** — cron activity
- **fs:fileevents** — /Library/LaunchDaemons/*.plist, ~/Library/LaunchAgents/*.plist
- **WinEventLog:TaskScheduler** — Task registration/execution shortly after a time discovery event
- **macos:unifiedlog** — New/modified launchd plist (persistence/scheduling) within TimeWindow after time query
- **esxi:syslog** — /var/log/vpxa.log task invocations tied to time configuration
- **WinEventLog:System** — EventCode=106, 200
- **macos:launchd** — launchd.plist and logs

## Analytics using this component

- [AN0325 - Analytic 0325](../Analytics/AN0325.md)
- [AN0326 - Analytic 0326](../Analytics/AN0326.md)
- [AN0430 - Analytic 0430](../Analytics/AN0430.md)
- [AN0431 - Analytic 0431](../Analytics/AN0431.md)
- [AN0432 - Analytic 0432](../Analytics/AN0432.md)
- [AN0433 - Analytic 0433](../Analytics/AN0433.md)
- [AN1118 - Analytic 1118](../Analytics/AN1118.md)
- [AN1119 - Analytic 1119](../Analytics/AN1119.md)
- [AN1120 - Analytic 1120](../Analytics/AN1120.md)
