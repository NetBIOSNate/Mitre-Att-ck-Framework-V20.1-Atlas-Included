# DC0036 - Image Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to a virtual machine image, including setting and/or control data (ex: Azure Compute Service Images PATCH)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0036)

## Log sources and channels

- **docker:registry** — push event of new image version from unrecognized user or context
- **AWS:CloudTrail** — ModifyImageAttribute

## Analytics using this component

- [AN0946 - Analytic 0946](../Analytics/AN0946.md)
- [AN0947 - Analytic 0947](../Analytics/AN0947.md)
