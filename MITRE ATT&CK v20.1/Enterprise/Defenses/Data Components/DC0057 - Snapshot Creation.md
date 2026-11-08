# DC0057 - Snapshot Creation

[Enterprise](../../README.md) / [Data Components](README.md)

The process of taking a point-in-time copy of a cloud storage volume (files, settings, configurations, etc.), virtual machine (VM), or database that can be created and deployed in cloud environments.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0057)

## Log sources and channels

- **esxi:vmkernel** — snapshot create/write events
- **AWS:CloudTrail** — CreateSnapshot
- **azure:activity** — MICROSOFT.COMPUTE/SNAPSHOTS/WRITE

## Analytics using this component

- [AN0727 - Analytic 0727](../Analytics/AN0727.md)
- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
- [AN1187 - Analytic 1187](../Analytics/AN1187.md)
- [AN1580 - Analytic 1580](../Analytics/AN1580.md)
