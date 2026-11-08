# DC0107 - Process History/Live Data

[ICS](../../README.md) / [Data Components](README.md)

This includes any data stores that maintain historical or real-time events and telemetry recorded from various sensors or devices

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0107)

## Log sources and channels

- **Databases** — None
- **Operational Databases** — None
- **operationaldb:ProcessHistory** — no new process value recorded for device_ip within 1.5x expected poll interval immediately following a flood alert
- **operationaldb:ProcessHistory** — process value crosses known alarm threshold but no corresponding alarm event recorded within expected latency window
- **operationaldb:ProcessHistory** — multiple safety-critical outputs toggle within rapid toggle window, pattern consistent with scripted issuance
- **operationaldb:ProcessHistory** — I/O point value oscillates or changes state at frequency exceeding max normal state change rate, inconsistent with physical process response time
- **operationaldb:ProcessHistory** — reported values show statistically improbable stability during a period when physical process is known to be actively changing
- **operationaldb:ProcessHistory** — tag value deviates from rolling baseline mean by more than parameter drift threshold percent within time window following a flagged write
- **operationaldb:ProcessHistory** — process value expected to change following a command does not change within command confirmation window
- **operationaldb:ProcessHistory** — no unsolicited report received from device_ip within 1.5x expected reporting interval, while direct polling confirms device is reachable
- **processsensor:RedundantComparison** — Independent process measurement comparison: controller I/O image value diverges from independent sensor/measurement beyond configured integrity tolerance

## Analytics using this component

- [AN1856 - Analytic 1856](../Analytics/AN1856.md)
- [AN1861 - Analytic 1861](../Analytics/AN1861.md)
- [AN1870 - Analytic 1870](../Analytics/AN1870.md)
- [AN1905 - Analytic 1905](../Analytics/AN1905.md)
- [AN1908 - Analytic 1908](../Analytics/AN1908.md)
- [AN1916 - Analytic 1916](../Analytics/AN1916.md)
- [AN2212 - Analytic 2212](../Analytics/AN2212.md)
- [AN2215 - Analytic 2215](../Analytics/AN2215.md)
- [AN2216 - Analytic 2216](../Analytics/AN2216.md)
