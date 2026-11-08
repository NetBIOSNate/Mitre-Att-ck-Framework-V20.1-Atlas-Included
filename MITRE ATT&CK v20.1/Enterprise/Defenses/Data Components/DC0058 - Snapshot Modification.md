# DC0058 - Snapshot Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to a cloud snapshot's metadata, attributes, or control settings. These modifications may involve adjusting access permissions, changing retention policies, or altering encryption settings. 

*Data Collection Measures:*

- AWS CloudTrail
    - Tracks API calls such as `ModifySnapshotAttribute`, `ResetSnapshotAttribute`, and `ModifySnapshotTier`.
- Azure Monitor Logs
    - Logs changes via `Microsoft.Compute/snapshots/write`.
- Google Cloud Logging
    - Captures modifications through `compute.snapshots.setIamPolicy` and `compute.snapshots.patch`.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0058)

## Log sources and channels

- **AWS:CloudTrail** — ModifySnapshotAttribute

## Analytics using this component

- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
- [AN1580 - Analytic 1580](../Analytics/AN1580.md)
