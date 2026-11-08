# DC0110 - Asset Inventory

[ICS](../../README.md) / [Data Components](README.md)

This includes sources of current and expected devices on the network, including the manufacturer, model, and necessary identifiers (e.g., IP and hardware addresses)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0110)

## Log sources and channels

- **Asset** — None
- **assetinventory:MasterAddress** — command traffic uses master/station address not in registered master addresses
- **assetinventory:ProgramHash** — post-transfer program hash does not match last authorized program baseline
- **assetinventory:ProgramSize** — device program size/block count increases without corresponding change ticket reference

## Analytics using this component

- [AN1884 - Analytic 1884](../Analytics/AN1884.md)
- [AN1924 - Analytic 1924](../Analytics/AN1924.md)
- [AN2057 - Analytic 2057](../Analytics/AN2057.md)
