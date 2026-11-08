# DC0069 - Cloud Service Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Cloud service modification refers to changes made to the configuration, settings, or data of a cloud service. These modifications can include administrative changes such as enabling or disabling features, altering permissions, or deleting critical components. Monitoring these changes is critical to detect potential misconfigurations or malicious activity. Examples: 

- AWS Cloud Service Modifications: A user disables AWS CloudTrail logging (StopLogging) or deletes a CloudWatch configuration rule (DeleteConfigRule).
- Azure Cloud Service Modifications: Changes to Azure Role-Based Access Control (RBAC) roles, such as adding a new Contributor role to a sensitive resource.
- Google Cloud Service Modifications: Deletion of a Google Cloud Storage bucket or disabling a Google Cloud Function.
- Office 365 Cloud Service Modifications: Altering mailbox permissions or disabling auditing in Microsoft 365.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0069)

## Log sources and channels

- **AWS:CloudTrail** — CreateFunction
- **m365:unified** — Creation of Power Automate flow triggered by OneDrive or Exchange event
- **AWS:CloudTrail** — PutUserPolicy, PutGroupPolicy, PutRolePolicy, CreatePolicyVersion
- **AWS:CloudTrail** — Condition block updated in IAM policy (e.g., aws:SourceIp, aws:RequestedRegion)
- **azure:activity** — operationName: Write, Access Review, RoleAssignment
- **azure:policy** — UpdatePolicy
- **AWS:CloudTrail** — UpdateAccountPasswordPolicy
- **AWS:CloudTrail** — PutIdentityPolicy
- **AWS:CloudTrail** — LeaveOrganization: API calls severing accounts from AWS Organizations
- **AWS:CloudTrail** — CreateAccount: API calls creating new accounts in AWS Organizations
- **azure:audit** — Tenant subscription transfers or new management group creation
- **AWS:CloudTrail** — UpdateIdentityPolicy or DisableMFA
- **m365:unified** — SendMessage
- **gcp:config** — UpdateSink request modifying log export destinations
- **azure:policy** — DisableAuditLogs or ConditionalAccess logging changes
- **AWS:CloudTrail** — UpdateFederationSettings or RegisterHybridConnector
- **AWS:CloudTrail** — CreateTrafficMirrorSession / ModifyTrafficMirrorTarget
- **azure:activity** — Microsoft.Network/networkWatchers/flowLogSettings/write
- **gcp:audit** — compute.packetMirroring.insert
- **AWS:CloudTrail** — CreateFunction / UpdateFunctionConfiguration: Function creation, role assignment, or configuration change events
- **m365:unified** — AddFlow / UpdateFlow: New automation or workflow creation events
- **saas:appsscript** — Create / Update: Deployment of scripts with event-driven triggers
- **saas:slack** — Exported file or accessed admin API
- **AWS:CloudTrail** — RequestServiceQuotaIncrease
- **azure:activity** — MICROSOFT.AUTHORIZATION/POLICIES/WRITE
- **gcp:audit** — projects.updateQuota or orgPolicies.updatePolicy
- **AWS:CloudTrail** — Delete* / Stop*: DeleteAlarms, StopLogging, or DisableMonitoring API calls
- **AWS:CloudTrail** — Use of temporary credentials issued from IMDS access
- **saas:github** — Workflow triggered via pull_request_target from forked repo
- **azure:audit** — Consent to application: OAuth application consent granted to service principal
- **saas:integration** — New or modified third-party application integrations with elevated permissions

## Analytics using this component

- [AN0027 - Analytic 0027](../Analytics/AN0027.md)
- [AN0028 - Analytic 0028](../Analytics/AN0028.md)
- [AN0087 - Analytic 0087](../Analytics/AN0087.md)
- [AN0215 - Analytic 0215](../Analytics/AN0215.md)
- [AN0290 - Analytic 0290](../Analytics/AN0290.md)
- [AN0291 - Analytic 0291](../Analytics/AN0291.md)
- [AN0417 - Analytic 0417](../Analytics/AN0417.md)
- [AN0442 - Analytic 0442](../Analytics/AN0442.md)
- [AN0545 - Analytic 0545](../Analytics/AN0545.md)
- [AN0746 - Analytic 0746](../Analytics/AN0746.md)
- [AN0801 - Analytic 0801](../Analytics/AN0801.md)
- [AN0802 - Analytic 0802](../Analytics/AN0802.md)
- [AN0816 - Analytic 0816](../Analytics/AN0816.md)
- [AN0878 - Analytic 0878](../Analytics/AN0878.md)
- [AN1053 - Analytic 1053](../Analytics/AN1053.md)
- [AN1054 - Analytic 1054](../Analytics/AN1054.md)
- [AN1055 - Analytic 1055](../Analytics/AN1055.md)
- [AN1162 - Analytic 1162](../Analytics/AN1162.md)
- [AN1356 - Analytic 1356](../Analytics/AN1356.md)
- [AN1372 - Analytic 1372](../Analytics/AN1372.md)
- [AN1424 - Analytic 1424](../Analytics/AN1424.md)
- [AN1473 - Analytic 1473](../Analytics/AN1473.md)
- [AN1487 - Analytic 1487](../Analytics/AN1487.md)
- [AN1488 - Analytic 1488](../Analytics/AN1488.md)
