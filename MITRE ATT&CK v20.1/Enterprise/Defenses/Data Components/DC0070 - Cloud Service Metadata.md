# DC0070 - Cloud Service Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud service metadata refers to the contextual and descriptive information about cloud services, including their name, type, purpose, configuration, and activity around them. This metadata is essential for understanding the roles and functions of cloud services, their operational status, and their potential misuse. Examples: 

- Azure Service Metadata: Metadata describing a resource in Azure, such as an Azure Storage Account or a Virtual Machine.
- AWS Cloud Service Metadata: Metadata for an AWS EC2 instance collected using the `DescribeInstances` API call.
- Google Cloud Service Metadata: Metadata for a Google Compute Engine instance collected using `gcloud compute instances describe`.
- Office 365 Metadata: Metadata about an Office 365 SharePoint site.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0070)

## Log sources and channels

- **AWS:CloudTrail** — GetInstanceIdentityDocument
- **AWS:CloudTrail** — rds:ExecuteStatement: Large data access via RDS or Aurora with unknown session context
- **saas:github** — repo.download, repo.clone, oauth.authorize, repo.getContent
- **AWS:CloudWatch** — unexpected IAM user or role assuming privileges for instance/snapshot operations
- **AWS:CloudTrail** — GetSecretValue
- **AWS:CloudTrail** — InvokeFunction
- **m365:sharepoint** — Multiple file download operations on a site by a privileged account in a short time window
- **saas:github** — CI/CD secret accessed or exported
- **m365:exchange** — Cmdlet - New-InboxRule
- **m365:unified** — New-InboxRule, Set-InboxRule

## Analytics using this component

- [AN0001 - Analytic 0001](../Analytics/AN0001.md)
- [AN0679 - Analytic 0679](../Analytics/AN0679.md)
- [AN0732 - Analytic 0732](../Analytics/AN0732.md)
- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
- [AN1157 - Analytic 1157](../Analytics/AN1157.md)
- [AN1168 - Analytic 1168](../Analytics/AN1168.md)
- [AN1380 - Analytic 1380](../Analytics/AN1380.md)
- [AN1473 - Analytic 1473](../Analytics/AN1473.md)
- [AN1589 - Analytic 1589](../Analytics/AN1589.md)
- [AN1591 - Analytic 1591](../Analytics/AN1591.md)
