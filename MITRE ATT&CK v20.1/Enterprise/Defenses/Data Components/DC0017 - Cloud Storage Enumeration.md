# DC0017 - Cloud Storage Enumeration

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud Storage Enumeration involves retrieving a list of available cloud storage infrastructure, such as buckets, containers, or objects, within a cloud environment. This activity may be performed for legitimate administrative purposes or malicious reconnaissance by adversaries seeking to identify accessible storage resources.Examples:

- AWS S3 Bucket Enumeration: An AWS user lists all buckets using the `ListBuckets` API call.
- Azure Blob Storage Container Enumeration: A user retrieves a list of all containers within a storage account using the Azure Storage SDK or API.
- Google Cloud Storage Bucket Enumeration: A Google Cloud user lists all buckets within a project using the `storage.buckets.list` API.
- OpenStack Swift Container Enumeration: A user retrieves a list of containers in OpenStack Swift using the `GET` method on the storage endpoint.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0017)

## Log sources and channels

- **AWS:CloudTrail** — ListBuckets
- **AWS:CloudTrail** — ListObjectsV2
- **azure:activity** — List Blobs
- **gcp:storage** — storage.objects.list

## Analytics using this component

- [AN0481 - Analytic 0481](../Analytics/AN0481.md)
- [AN1594 - Analytic 1594](../Analytics/AN1594.md)
- [AN1625 - Analytic 1625](../Analytics/AN1625.md)
