# DC0098 - Volume Deletion

[Enterprise](../../README.md) / [Data Components](README.md)

The removal of a cloud-based or on-premise block storage volume. This action permanently deletes the allocated storage and may result in data loss if not backed up.

*Data Collection Measures:*

- Cloud Logging & APIs
    - AWS CloudTrail Logs
        - `eventName: DeleteVolume` (tracks volume deletions)
    - Azure Monitor Logs
        - `operationName: Microsoft.Compute/disks/delete`
        - `status: Success | Failure` (flag unauthorized delete attempts)
    - Google Cloud Audit Logs
        - `protoPayload.methodName: "v1.compute.disks.delete"`
        - `authenticationInfo.principalEmail` (identifies the user deleting the volume)
- System & Host-Based Logging
    - Linux & macOS Logs:
        - `/var/log/syslog` or `/var/log/messages` for volume detach/deletion actions
    - Windows Event Logs:
        - Event ID 98 (Storage Class Memory)
        - Event ID 225 (Volume Removal Detected)
        - Event ID 12 (Disk Removal Notification)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0098)

## Log sources and channels

- **esxi:vmkernel** — file delete|datastore purge
- **AWS:CloudTrail** — DeleteVolume

## Analytics using this component

- [AN0415 - Analytic 0415](../Analytics/AN0415.md)
- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
