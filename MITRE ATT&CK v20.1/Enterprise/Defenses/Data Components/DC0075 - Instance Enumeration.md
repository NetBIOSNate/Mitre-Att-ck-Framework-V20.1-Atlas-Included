# DC0075 - Instance Enumeration

[Enterprise](../../README.md) / [Data Components](README.md)

The process of retrieving or querying a list of virtual machine instances or compute instances within a cloud infrastructure. This activity provides a view of all available or running instances, typically including their associated metadata such as instance ID, name, state, and configuration details. Examples:

- AWS: instance enumeration involves the `DescribeInstances` API call, which retrieves information about running or stopped EC2 instances.
- Azure: VM enumeration can be monitored via the `Microsoft.Compute/virtualMachines/read` operation.
- GCP: instance enumeration is logged as an `instance.list` operation within GCP Audit Logs.

*Data Collection Measures:*

- AWS CloudTrail: CloudTrail logs stored in S3 or forwarded to CloudWatch.
- Azure Activity Logs: Accessible via Azure Monitor or exported to a storage account.
- GCP Audit Logs: Logs Explorer or BigQuery.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0075)

## Log sources and channels

- **AWS:CloudTrail** — DescribeDBInstances
- **azure:activity** — MICROSOFT.COMPUTE/VIRTUALMACHINES/LIST
- **gcp:audit** — compute.instances.list OR storage.buckets.list
- **AWS:CloudTrail** — DescribeInstances, GetConsoleOutput, DescribeImages
- **azure:activity** — Microsoft.Compute/virtualMachines/read

## Analytics using this component

- [AN0481 - Analytic 0481](../Analytics/AN0481.md)
- [AN1456 - Analytic 1456](../Analytics/AN1456.md)
