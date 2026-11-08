# DC0050 - Windows Registry Key Access

[Enterprise](../../README.md) / [Data Components](README.md)

The action of opening a specific Windows Registry key, typically to read its associated value. This activity can be used for system configuration, application settings retrieval, and security policies.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0050)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4663, 4670, 4656
- **WinEventLog:Security** — EventCode=4657
- **EDR:hunting** — Behavioral rule for registry enumeration under credential-related paths
- **Autoruns:RegistryScan** — Enumerate Winlogon subkeys for unknown or unsigned binaries

## Analytics using this component

- [AN0628 - Analytic 0628](../Analytics/AN0628.md)
- [AN0671 - Analytic 0671](../Analytics/AN0671.md)
- [AN0694 - Analytic 0694](../Analytics/AN0694.md)
- [AN1133 - Analytic 1133](../Analytics/AN1133.md)
- [AN1393 - Analytic 1393](../Analytics/AN1393.md)
- [AN1561 - Analytic 1561](../Analytics/AN1561.md)
