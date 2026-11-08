# DC0117 - System Notifications

[Mobile](../../README.md) / [Data Components](README.md)

System Notifications represent operating system alerts, warnings, or status messages generated in response to application actions, system state changes, or security events. These notifications may indicate potentially malicious activity or abnormal application behavior.

Examples

- Application requesting sensitive permissions
- USB device connected notifications
- Security warnings triggered by device configuration changes

Collection Methods

- Mobile OS notification monitoring
- Mobile EDR sensors
- Device management telemetry

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0117)

## Log sources and channels

- **User Interface** — None
- **iOS:unifiedlog** — \"has pasted from\" cross-app paste notification text containing source app name
- **iOS:ManagedAppLog** — ManagedApplicationFeedback or application-generated telemetry
- **android:ManagedAppLog** — Documented DPC/admin callbacks or managed-app generated event telemetry

## Analytics using this component

- [AN1720 - Analytic 1720](../Analytics/AN1720.md)
- [AN1790 - Analytic 1790](../Analytics/AN1790.md)
- [AN1798 - Analytic 1798](../Analytics/AN1798.md)
