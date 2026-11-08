# DC0008 - WMI Creation

[Enterprise](../../README.md) / [Data Components](README.md)

Initial construction of a WMI object, such as a filter, consumer, subscription, binding, or providers.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0008)

## Log sources and channels

- **WinEventLog:WMI** — Creation or modification of __EventFilter, __FilterToConsumerBinding, or CommandLineEventConsumer
- **WinEventLog:WMI** — EventCode=5857, 5858, 5860, 5861
- **WinEventLog:Application** — WMI Object Creation Events

## Analytics using this component

- [AN0024 - Analytic 0024](../Analytics/AN0024.md)
- [AN0236 - Analytic 0236](../Analytics/AN0236.md)
- [AN0973 - Analytic 0973](../Analytics/AN0973.md)
- [AN1031 - Analytic 1031](../Analytics/AN1031.md)
- [AN1177 - Analytic 1177](../Analytics/AN1177.md)
- [AN1305 - Analytic 1305](../Analytics/AN1305.md)
- [AN1551 - Analytic 1551](../Analytics/AN1551.md)
