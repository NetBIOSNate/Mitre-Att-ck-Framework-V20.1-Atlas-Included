# DC0090 - Cloud Service Disable

[Enterprise](../../README.md) / [Data Components](README.md)

This data component refers to monitoring actions that deactivate or stop a cloud service in a cloud control plane. Examples include disabling essential logging services like AWS CloudTrail (`StopLogging` API call), Microsoft Azure Monitor Logs, or Google Cloud's Operations Suite (formerly Stackdriver). Disabling such services can hinder visibility into adversary activities within the cloud environment. Examples: 

- AWS CloudTrail StopLogging: This action stops logging of API activity for a particular trail, effectively reducing the monitoring and visibility of AWS resources and activities.
- Microsoft Azure Monitor Logs: Disabling these logs hinders the organization’s ability to detect anomalous activities and trace malicious actions.
- Google Cloud Logging: Disabling cloud logging removes visibility into resource activity, preventing monitoring of service access or configuration changes.
- SaaS Applications: Stopping logging removes visibility into user activities, such as email access or file downloads, enabling undetected malicious behavior.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0090)

## Log sources and channels

- **AWS:CloudTrail** — Stop logging for an existing CloudTrail
- **AWS:CloudTrail** — Removal of CloudTrail trail
- **azure:activity** — az monitor diagnostic-settings delete
- **saas:audit** — Log export integration removed or disabled
- **AWS:CloudTrail** — StopLogging, DeleteTrail, or DisableSecurityService

## Analytics using this component

- [AN0801 - Analytic 0801](../Analytics/AN0801.md)
- [AN0804 - Analytic 0804](../Analytics/AN0804.md)
- [AN0891 - Analytic 0891](../Analytics/AN0891.md)
- [AN2041 - Analytic 2041](../Analytics/AN2041.md)
