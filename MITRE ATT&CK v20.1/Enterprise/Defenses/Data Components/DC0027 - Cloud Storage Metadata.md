# DC0027 - Cloud Storage Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud Storage Metadata provides contextual information about cloud storage infrastructure and its associated activity. This data may include attributes such as storage name, size, owner, permissions, creation date, region, and activity metadata. It is essential for monitoring, auditing, and identifying anomalies in cloud storage environments. Examples: 

- AWS S3 Bucket Metadata: Metadata about an S3 bucket includes the bucket name, region, creation date, owner, storage class, and permissions.
- Azure Blob Storage Metadata: Metadata for an Azure Blob container includes container name, access level (e.g., private or public), size, and tags.
- Google Cloud Storage Metadata: Metadata includes bucket name, storage class, location, labels, lifecycle policies, and versioning status.
- OpenStack Swift Metadata: Metadata for a Swift container includes name, access level, quota, and custom attributes.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0027)

## Log sources and channels

- **AWS:CloudTrail** — Post-authentication metadata enumeration from GUI session
- **m365:unified** — AnonymousLinkCreated
- **saas:box** — collaboration.invite
- **saas:dropbox** — Shared link created to external account

## Analytics using this component

- [AN0808 - Analytic 0808](../Analytics/AN0808.md)
- [AN1581 - Analytic 1581](../Analytics/AN1581.md)
- [AN1582 - Analytic 1582](../Analytics/AN1582.md)
