# DC0013 - User Account Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual data about an account, which may include a username, user ID, environmental data, etc.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0013)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4720, 4738
- **WinEventLog:Security** — EventCode=4673
- **AWS:CloudTrail** — AssumeRole
- **auditd:SYSCALL** — open,openat,read
- **macos:MDM** — profiles -P|getaccountpolicies
- **AWS:CloudTrail** — GetAccountPasswordPolicy
- **azure:audit** — operation contains 'Get*Password*Policy' OR 'List*Authentication*Policy' OR 'Get-ADDefaultDomainPasswordPolicy'
- **m365:unified** — Workload=AzureActiveDirectory OR Exchange AND (Operation=Cmdlet AND Parameters contains 'Password' AND (CmdletName='Get-*' OR CmdletName='Get-OrganizationConfig'))
- **saas:auth** — Refresh token issuance or refresh token usage from new IPs or user agents
- **gcp:audit** — Directory API Access: users.list or groups.list
- **CloudTrail:GetCallerIdentity** — GetCallerIdentity
- **vpxd.log** — vCenter Management
- **macos:unifiedlog** — Creation of user account with UID <500
- **WinEventLog:Security** — EventCode=4674
- **windows:osquery** — User enumeration with creation/last modified timestamps
- **linux:osquery** — Listing of /etc/passwd and /etc/shadow metadata
- **saas:okta** — User lifecycle events
- **Microsoft Entra ID Audit Logs** — RoleManagement.Read.Directory or Directory.Read.All
- **azure:activity** — Azure CLI Operation: Microsoft.Graph/users/read
- **gcp:audit** — IAM API call: serviceAccounts.list or projects.getIamPolicy
- **Microsoft Graph API Logs** — users.list, directoryObjects.getByIds
- **Defender for Identity** — Suspicious Enumeration of Cloud Directory
- **Google Admin Audit** — users.list, groups.list
- **AWS:CloudTrail** — PassRole
- **gcp:iam** — PrincipalEmail with serviceAccountTokenCreator impersonating new identity
- **AWS:CloudTrail** — AssumeRole: Discovery actions tied to assumed identities outside of normal context
- **saas:okta** — User Enumeration Events
- **gcp:audit** — Directory API Access
- **macos:unifiedlog** — DirectoryService queries retrieving account information

## Analytics using this component

- [AN0383 - Analytic 0383](../Analytics/AN0383.md)
- [AN0384 - Analytic 0384](../Analytics/AN0384.md)
- [AN0417 - Analytic 0417](../Analytics/AN0417.md)
- [AN0456 - Analytic 0456](../Analytics/AN0456.md)
- [AN0457 - Analytic 0457](../Analytics/AN0457.md)
- [AN0458 - Analytic 0458](../Analytics/AN0458.md)
- [AN0459 - Analytic 0459](../Analytics/AN0459.md)
- [AN0460 - Analytic 0460](../Analytics/AN0460.md)
- [AN0501 - Analytic 0501](../Analytics/AN0501.md)
- [AN0642 - Analytic 0642](../Analytics/AN0642.md)
- [AN0690 - Analytic 0690](../Analytics/AN0690.md)
- [AN0827 - Analytic 0827](../Analytics/AN0827.md)
- [AN0849 - Analytic 0849](../Analytics/AN0849.md)
- [AN0882 - Analytic 0882](../Analytics/AN0882.md)
- [AN0958 - Analytic 0958](../Analytics/AN0958.md)
- [AN0960 - Analytic 0960](../Analytics/AN0960.md)
- [AN1003 - Analytic 1003](../Analytics/AN1003.md)
- [AN1030 - Analytic 1030](../Analytics/AN1030.md)
- [AN1077 - Analytic 1077](../Analytics/AN1077.md)
- [AN1078 - Analytic 1078](../Analytics/AN1078.md)
- [AN1079 - Analytic 1079](../Analytics/AN1079.md)
- [AN1087 - Analytic 1087](../Analytics/AN1087.md)
- [AN1088 - Analytic 1088](../Analytics/AN1088.md)
- [AN1089 - Analytic 1089](../Analytics/AN1089.md)
- [AN1090 - Analytic 1090](../Analytics/AN1090.md)
- [AN1105 - Analytic 1105](../Analytics/AN1105.md)
- [AN1106 - Analytic 1106](../Analytics/AN1106.md)
- [AN1127 - Analytic 1127](../Analytics/AN1127.md)
- [AN1328 - Analytic 1328](../Analytics/AN1328.md)
- [AN1398 - Analytic 1398](../Analytics/AN1398.md)
- [AN1614 - Analytic 1614](../Analytics/AN1614.md)
- [AN1616 - Analytic 1616](../Analytics/AN1616.md)
- [AN1618 - Analytic 1618](../Analytics/AN1618.md)
