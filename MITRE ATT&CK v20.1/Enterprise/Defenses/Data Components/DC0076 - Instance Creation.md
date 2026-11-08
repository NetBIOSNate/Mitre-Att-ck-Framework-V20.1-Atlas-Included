# DC0076 - Instance Creation

[Enterprise](../../README.md) / [Data Components](README.md)

The initial provisioning and construction of a virtual machine (VM) or compute instance within a cloud infrastructure environment. This activity involves defining and allocating resources such as CPU, memory, storage, and networking to spin up a new compute instance. Examples:

- AWS: creating an EC2 instance using RunInstances API calls.
- Azure, creating a VM through the Azure Resource Manager (ARM).
- GCP, an `instance.insert` action recorded.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0076)

## Log sources and channels

- **azure:activity** — Microsoft.Compute/virtualMachines/write: imageReference publisher NOT IN allowlist OR plan is new/unknown
- **gcp:audit** — compute.instances.insert: sourceImage not in approved projects OR has external image link
- **azure:activity** — MICROSOFT.COMPUTE/VIRTUALMACHINES/WRITE
- **gcp:audit** — compute.instances.insert
- **AWS:CloudTrail** — RunInstances,CreateImage

## Analytics using this component

- [AN0692 - Analytic 0692](../Analytics/AN0692.md)
- [AN1242 - Analytic 1242](../Analytics/AN1242.md)
- [AN1318 - Analytic 1318](../Analytics/AN1318.md)
