# DC0108 - Device Alarm

[ICS](../../README.md) / [Data Components](README.md)

This includes alarms associated with unexpected device functions, such as shutdowns, restarts, failures, or configuration changes

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0108)

## Log sources and channels

- **Operational Databases** — None
- **alarmserver:ApplicationLog** — alarm suppression Application Programming Interface (API) call logged without operator session identifier (ID)
- **alarmserver:ApplicationLog** — alarm class disabled or suppressed Application Programming Interface (API) event logged without operator_id field populated
- **operationaldb:AlarmEvent** — device reboot/restart alarm within firmware update window of the flagged transfer session
- **operationaldb:AlarmEvent** — device reboot within firmware update window of the flagged transfer session
- **operationaldb:AlarmEvent** — device receives commands from two distinct master identities within a short window
- **device:VendorLog** — measured scan cycle time or interrupt response latency deviates from baseline cycle time by more than cycle timing deviation threshold following a task configuration change
- **operationaldb:AlarmEvent** — device_ip transitions to PROGRAM/STOP mode without operator_ack and without corresponding open change ticket reference
- **device:VendorLog** — measurable change in scan cycle timing or Input/Output (I/O) update pattern following a flagged program write
- **operationaldb:AlarmEvent** — device mode-change alarm generated without corresponding operator_id entry within mode change ack window
- **operationaldb:AlarmEvent** — alarm threshold configuration changed without operator_ack or change ticket reference
- **operationaldb:AlarmEvent** — more than one device generates restart/offline alarm within bulk restart time window without open maintenance ticket
- **operationaldb:AlarmEvent** — device_ip alarm telemetry goes silent within alarm silence grace period of the mode-activation message without operator acknowledgment
- **operationaldb:AlarmEvent** — device offline alarm coinciding with switch port admin-down syslog for that port
- **processsensor:RedundantComparison** — device-reported value for a tag diverges from independently measured value for same physical quantity by more than sensor tolerance threshold

## Analytics using this component

- [AN1864 - Analytic 1864](../Analytics/AN1864.md)
- [AN1874 - Analytic 1874](../Analytics/AN1874.md)
- [AN1884 - Analytic 1884](../Analytics/AN1884.md)
- [AN1887 - Analytic 1887](../Analytics/AN1887.md)
- [AN1915 - Analytic 1915](../Analytics/AN1915.md)
- [AN1924 - Analytic 1924](../Analytics/AN1924.md)
- [AN1933 - Analytic 1933](../Analytics/AN1933.md)
- [AN1934 - Analytic 1934](../Analytics/AN1934.md)
- [AN2047 - Analytic 2047](../Analytics/AN2047.md)
- [AN2107 - Analytic 2107](../Analytics/AN2107.md)
- [AN2108 - Analytic 2108](../Analytics/AN2108.md)
- [AN2211 - Analytic 2211](../Analytics/AN2211.md)
- [AN2214 - Analytic 2214](../Analytics/AN2214.md)
- [AN2215 - Analytic 2215](../Analytics/AN2215.md)
