# DC0024 - Cloud Storage Creation

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud Storage Creation refers to the initial creation of a new cloud storage resource, such as buckets, containers, or directories, within a cloud environment. This action is critical to track as it might indicate the legitimate provisioning of resources or unauthorized actions taken by adversaries to stage, store, or exfiltrate data. Examples: 

- AWS S3 Bucket Creation: An AWS user creates a new S3 bucket using the `CreateBucket` API call.
- Azure Blob Storage Container Creation: A user creates a new container in Azure Blob Storage using the `Create Container` operation.
- Google Cloud Storage Bucket Creation: A Google Cloud user creates a new bucket using `storage.buckets.create`.
- OpenStack Swift Container Creation: A user creates a new container in OpenStack Swift using the `PUT` method.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0024)

## Log sources and channels

- **AWS:CloudTrail** — CreateBucket

## Analytics using this component

- [AN0690 - Analytic 0690](../Analytics/AN0690.md)
