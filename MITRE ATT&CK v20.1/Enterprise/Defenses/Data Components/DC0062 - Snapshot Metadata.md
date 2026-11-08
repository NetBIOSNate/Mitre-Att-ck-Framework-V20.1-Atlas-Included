# DC0062 - Snapshot Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual data about a snapshot, which may include information such as ID, type, and status

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0062)

## Log sources and channels

- **AWS:CloudTrail** — DescribeSnapshots
- **gcp:audit** — compute.disks.insert with sourceSnapshot parameter
- **AWS:CloudTrail** — CopySnapshot

## Analytics using this component

- [AN1187 - Analytic 1187](../Analytics/AN1187.md)
- [AN1580 - Analytic 1580](../Analytics/AN1580.md)
