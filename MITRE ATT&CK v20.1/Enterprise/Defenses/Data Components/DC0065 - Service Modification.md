# DC0065 - Service Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to an existing service or daemon, such as modifying the service name, start type, execution parameters, or security configurations.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0065)

## Log sources and channels

- **esxi:hostd** — service state change
- **Service** — None
- **WinEventLog:Microsoft-IIS-Configuration** — Module or ISAPI filter registration events
- **WinEventLog:System** — EventCode=7040

## Analytics using this component

- [AN0184 - Analytic 0184](../Analytics/AN0184.md)
- [AN1195 - Analytic 1195](../Analytics/AN1195.md)
- [AN2044 - Analytic 2044](../Analytics/AN2044.md)
