# DC0025 - Cloud Storage Access

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud storage access refers to the retrieval or interaction with data stored in cloud infrastructure. This data component includes activities such as reading, downloading, or accessing files and objects within cloud storage systems. Common examples include API calls like GetObject in AWS S3, which retrieves objects from cloud buckets. Examples: 

- AWS S3 Access: An adversary uses the `GetObject` API to retrieve sensitive data from an AWS S3 bucket.
- Azure Blob Storage Access: A user accesses a blob in Azure Storage using `Get Blob` or `Get Blob Properties`.
- Google Cloud Storage Access: An adversary uses `storage.objects.get` to download objects from - OpenStack Swift Storage Access: A user retrieves an object from OpenStack Swift using the `GET` method.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0025)

## Log sources and channels

- **AWS:CloudTrail** — GetObject, CopyObject
- **AWS:CloudTrail** — PutObject: S3 writes with .sql/.csv extension by same identity or within 5 min of DB access
- **m365:unified** — Accessed SharePoint files or pages
- **m365:unified** — FileAccessed, FileDownloaded, ConsentGranted
- **gcp:workspaceaudit** — download, authorization_grant
- **m365:sharepoint** — AnonymousLinkCreated, FileDownloaded
- **m365:unified** — App-only or delegated access patterns where client_id != known enterprise apps
- **saas:github** — Artifact generated includes base64/encoded exfil payload or URL

## Analytics using this component

- [AN0043 - Analytic 0043](../Analytics/AN0043.md)
- [AN0198 - Analytic 0198](../Analytics/AN0198.md)
- [AN0370 - Analytic 0370](../Analytics/AN0370.md)
- [AN0666 - Analytic 0666](../Analytics/AN0666.md)
- [AN0679 - Analytic 0679](../Analytics/AN0679.md)
- [AN1160 - Analytic 1160](../Analytics/AN1160.md)
- [AN1328 - Analytic 1328](../Analytics/AN1328.md)
- [AN1329 - Analytic 1329](../Analytics/AN1329.md)
- [AN1330 - Analytic 1330](../Analytics/AN1330.md)
- [AN1426 - Analytic 1426](../Analytics/AN1426.md)
- [AN1473 - Analytic 1473](../Analytics/AN1473.md)
- [AN1594 - Analytic 1594](../Analytics/AN1594.md)
- [AN1625 - Analytic 1625](../Analytics/AN1625.md)
