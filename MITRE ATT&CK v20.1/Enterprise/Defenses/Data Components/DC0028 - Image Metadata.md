# DC0028 - Image Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

contextual information associated with a virtual machine image, such as its name, resource group, status (active or inactive), type (custom or prebuilt), size, creation date, and permissions. This metadata is critical for understanding the state and configuration of virtual machine images in cloud environments. Examples: 

- Azure Compute Service Image Metadata Example:
    - Name: MyCustomImage
    - Resource Group: MyResourceGroup
    - State: Available
    - Type: Managed Image
- AWS EC2 AMI Metadata Example:
    - Image ID: ami-1234567890abcdef0
    - Name: ProdImage
    - State: Available
    - Platform: Windows
- Google Cloud Compute Engine Image Metadata Example:
    - Image Name: webserver-image
    - Project: my-project-id
    - Family: webserver
    - Source Disk: my-disk-id
- VMware vSphere Template Metadata Example:
    - Name: LinuxTemplate
    - Disk Size: 40GB
    - Network Adapter: VM Network

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0028)

## Log sources and channels

- **docker:events** — docker.events.json
- **esxi:vmkernel** — VMX startup messages without associated vCenter inventory records
- **kubernetes:apiserver** — Resource creation and update logs

## Analytics using this component

- [AN0358 - Analytic 0358](../Analytics/AN0358.md)
- [AN0912 - Analytic 0912](../Analytics/AN0912.md)
- [AN0986 - Analytic 0986](../Analytics/AN0986.md)
