# DC0089 - Instance Stop

[Enterprise](../../README.md) / [Data Components](README.md)

The deactivation or shutdown of a virtual machine instance within a cloud infrastructure. This action typically involves stopping a running instance, which halts its operation and releases certain associated resources, such as CPU and memory. Examples: 

- Google Cloud Platform (GCP): `instance.stop` events recorded in GCP Audit Logs indicate the deactivation of an instance.
- Amazon Web Services (AWS): `StopInstances` actions in AWS CloudTrail indicate EC2 instances being stopped.
- Microsoft Azure: `Microsoft.Compute/virtualMachines/deallocate` or `stop` events in Azure Activity Logs represent a virtual machine being stopped or deallocated.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0089)

## Log sources and channels

- **AWS:CloudTrail** — TerminateInstances
- **AWS:CloudTrail** — StopInstances

## Analytics using this component

- [AN0234 - Analytic 0234](../Analytics/AN0234.md)
- [AN0853 - Analytic 0853](../Analytics/AN0853.md)
- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
- [AN0953 - Analytic 0953](../Analytics/AN0953.md)
