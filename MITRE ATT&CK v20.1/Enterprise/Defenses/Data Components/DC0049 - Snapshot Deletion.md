# DC0049 - Snapshot Deletion

[Enterprise](../../README.md) / [Data Components](README.md)

The removal of a point-in-time backup of a cloud storage volume, virtual machine (VM), or database.

*Data Collection Measures:*

- AWS CloudTrail
    - Logs `DeleteSnapshot` API calls in EC2, RDS, and EBS services.
- Azure Monitor Logs
    - Tracks snapshot deletions via `Microsoft.Compute/snapshots/delete` API calls.
- Google Cloud Logging
    - Detects snapshot removal through `compute.disks.deleteSnapshot` events.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0049)

## Log sources and channels

- **AWS:CloudTrail** — DeleteSnapshot
- **esxi:hostd** — snapshot.removeall or snapshot file deletion

## Analytics using this component

- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
- [AN0935 - Analytic 0935](../Analytics/AN0935.md)
- [AN0937 - Analytic 0937](../Analytics/AN0937.md)
