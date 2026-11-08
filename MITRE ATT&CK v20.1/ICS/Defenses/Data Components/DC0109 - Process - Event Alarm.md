# DC0109 - Process/Event Alarm

[ICS](../../README.md) / [Data Components](README.md)

This includes a list of any process alarms or alerts produced to indicate unusual or concerning activity within the operational process (e.g., increased temperature/pressure)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0109)

## Log sources and channels

- **Databases** — None
- **Operational Databases** — None
- **operationaldb:AlarmEvent** — communication-loss alarm for affected devices within comm block correlation window of the flagged configuration change
- **operationaldb:AlarmEvent** — alarm status transitions to suppressed/shelved/disabled/acknowledged without matching operator_id entry within suppress grace period
- **operationaldb:AlarmEvent** — process state change recorded without preceding operator_ack or scheduled switching order reference
- **operationaldb:AlarmEvent** — device_ip communication-loss alarm within serial block correlation window of a flagged serial gateway configuration change
- **operationaldb:AlarmEvent** — expected communication absent for device_ip without corresponding device-generated alarm explaining the gap

## Analytics using this component

- [AN1861 - Analytic 1861](../Analytics/AN1861.md)
- [AN1929 - Analytic 1929](../Analytics/AN1929.md)
- [AN2053 - Analytic 2053](../Analytics/AN2053.md)
- [AN2212 - Analytic 2212](../Analytics/AN2212.md)
- [AN2213 - Analytic 2213](../Analytics/AN2213.md)
