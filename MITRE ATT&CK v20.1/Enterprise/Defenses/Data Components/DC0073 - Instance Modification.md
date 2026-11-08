# DC0073 - Instance Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to a virtual machine (VM) or compute instance, including alterations to its configuration, metadata, attached policies, or operational state. Such modifications can include updating metadata, attaching or detaching resource policies, resizing instances, or modifying network configurations. Examples:

- AWS: instance modifications include API actions like `ModifyInstanceAttribute`, `ModifyInstanceMetadataOptions`, or `RebootInstances`.
- Azure: modifications can be tracked through operations like `Microsoft.Compute/virtualMachines/write`.
- GCP: instance modification events include operations like `instances.setMetadata`, `instances.addResourcePolicies`, or `instances.resize`.

*Data Collection Measures:*

- AWS CloudTrail: Log Location: Stored in S3 or forwarded to CloudWatch.
- Azure Activity Logs: Log Location: Accessible via Azure Monitor or exported to a storage account.
- GCP Audit Logs: Log Location: Logs Explorer or BigQuery.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0073)

## Log sources and channels

- **AWS:CloudTrail** — RevertSnapshot
- **azure:activity** — MICROSOFT.COMPUTE/VIRTUALMACHINES/RESTORE
- **gcp:audit** — compute.instances.restore
- **AWS:CloudTrail** — ModifyInstanceAttribute

## Analytics using this component

- [AN0953 - Analytic 0953](../Analytics/AN0953.md)
- [AN2041 - Analytic 2041](../Analytics/AN2041.md)
