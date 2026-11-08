# DC0092 - Volume Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to a cloud volume, including its settings and control data (ex: AWS modify-volume)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0092)

## Log sources and channels

- **kubernetes:apiserver** — Pod spec with hostPath or privileged securityContext
- **AWS:CloudTrail** — ModifyVolume

## Analytics using this component

- [AN0612 - Analytic 0612](../Analytics/AN0612.md)
- [AN0861 - Analytic 0861](../Analytics/AN0861.md)
