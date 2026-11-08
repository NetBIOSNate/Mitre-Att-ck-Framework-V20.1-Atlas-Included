# DC0023 - Cloud Storage Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud Storage Modification involves tracking changes made to cloud storage infrastructure, including updates to settings, permissions, or stored data. Examples include modifying object access control lists (ACLs), uploading new objects, or updating bucket policies. Examples: 

AWS S3: An object is uploaded or its ACL is modified.
- Azure Blob Storage: A blob's metadata or permissions are updated.
- Google Cloud Storage: An object's lifecycle policy is updated, or a bucket policy is changed.
- OpenStack Swift: Modifications to container settings or uploading of new objects.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0023)

## Log sources and channels

- **AWS:CloudTrail** — PutBucketLifecycle, PutLifecycleConfiguration, SetBucketLifecycle, storage.buckets.update
- **AWS:CloudTrail** — PutObject (with SSE-C), UploadPart (SSE-C)
- **AWS:CloudTrail** — PutBucketPolicy
- **m365:unified** — SharingSet
- **saas:googledrive** — drive.permission.add

## Analytics using this component

- [AN0117 - Analytic 0117](../Analytics/AN0117.md)
- [AN0606 - Analytic 0606](../Analytics/AN0606.md)
- [AN1580 - Analytic 1580](../Analytics/AN1580.md)
- [AN1581 - Analytic 1581](../Analytics/AN1581.md)
- [AN1582 - Analytic 1582](../Analytics/AN1582.md)
