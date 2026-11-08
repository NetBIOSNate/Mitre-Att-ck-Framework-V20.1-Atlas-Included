# DC0080 - Instance Start

[Enterprise](../../README.md) / [Data Components](README.md)

The initiation or activation of a virtual machine instance within a cloud infrastructure. This action typically involves starting an existing instance that had been stopped or paused, allowing it to resume operation. Examples: 

- Google Cloud Platform (GCP): Starting an instance through `instance.start` API activity.
- AWS: Logging of `StartInstances` in AWS CloudTrail for EC2 instances.
- Azure: `Microsoft.Compute/virtualMachines/start` entries indicate a VM instance being started.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0080)

## Log sources and channels

- **AWS:CloudTrail** — StartInstances
- **AWS:CloudTrail** — RunInstances

## Analytics using this component

- [AN0084 - Analytic 0084](../Analytics/AN0084.md)
- [AN0587 - Analytic 0587](../Analytics/AN0587.md)
- [AN0690 - Analytic 0690](../Analytics/AN0690.md)
- [AN0692 - Analytic 0692](../Analytics/AN0692.md)
- [AN0744 - Analytic 0744](../Analytics/AN0744.md)
- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
- [AN0947 - Analytic 0947](../Analytics/AN0947.md)
- [AN0953 - Analytic 0953](../Analytics/AN0953.md)
- [AN1242 - Analytic 1242](../Analytics/AN1242.md)
- [AN1318 - Analytic 1318](../Analytics/AN1318.md)
- [AN1493 - Analytic 1493](../Analytics/AN1493.md)
