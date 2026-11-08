# DC0010 - User Account Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to an existing user, service, or machine account, including alterations to attributes, permissions, roles, authentication methods, or group memberships.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0010)

## Log sources and channels

- **auditd:SYSCALL** — usermod, groupmod, passwd
- **auditd:SYSCALL** — SYSCALL for usermod or /etc/group file modification
- **auditd:SYSCALL** — usermod, or account rename system calls
- **AWS:CloudTrail** — UpdateLoginProfile
- **AWS:CloudTrail** — AttachUserPolicy, CreatePolicyVersion, PutRolePolicy
- **AWS:CloudTrail** — AttachUserPolicy
- **AWS:CloudTrail** — CreateAccessKey
- **AWS:CloudTrail** — role privilege expansion detected
- **azure:audit** — Operation IN ("Add device", "Add registered users to device", "Add registered owner to device")
- **azure:audit** — Add member to role
- **azure:audit** — Rename user
- **azure:audit** — Add service principal credentials, app password added, app role assignment
- **azure:policy** — DisableMfaPolicy or change to ConditionalAccess rules
- **azure:signinlogs** — unusual role assumption or elevation path
- **gcp:audit** — Admin Activity > Role Change or Sharing Change
- **gcp:audit** — google.iam.admin.v1.RoleAssignment
- **gcp:audit** — Set Gmail Delegation
- **gcp:audit** — iam.serviceAccounts.keys.create, os-login.sshPublicKeys.add
- **gcp:audit** — API Key Created, OAuth Client Registered
- **idp:audit** — ASP added/created where exposed by provider
- **idp:audit** — Application-specific password created/added for account 
- **kubernetes:audit** — create or update events for RoleBinding or ClusterRoleBinding objects
- **linux:syslog** — sudo or su access prior to content change
- **m365:audit** — Add member to role, Add app role assignment
- **m365:unified** — Admin Activity > Role Change or Sharing Change
- **m365:unified** — Set-ADUser OR Set-ADAccountControl
- **m365:unified** — User excluded from MFA or MFA method registered
- **m365:unified** — Add member to role, Set-Mailbox
- **m365:unified** — Set-MailboxAuditBypassAssociation or disabling Advanced Auditing
- **m365:unified** — New agent registration by non-admin user
- **m365:unified** — Add-MailboxPermission, UpdateFolderPermissions
- **m365:unified** — Set-Mailbox, Set-InboxRule, Set-MailboxFolderPermission
- **macos:unifiedlog** — com.apple.accountsd, com.apple.opendirectoryd
- **macos:unifiedlog** — Process execution or directory service changes
- **Okta:SystemLog** — user.account.privilege.grant
- **saas:audit** — ASP creation/modification event where supported 
- **saas:okta** — User Attribute Modified / Role Assignment Changed
- **saas:okta** — user.lifecycle.deactivate, user.lifecycle.suspend, user.lifecycle.delete.initiated, user.lifecycle.delete.completed
- **saas:okta** — admin role granted outside approved workflows
- **saas:zoom** — DisableMFA or RegisterNewFactor
- **WinEventLog:Security** — EventCode=4738, 4728, 4670
- **WinEventLog:Security** — EventCode=4723, 4724, 4740
- **WinEventLog:Security** — EventCode=4704
- **WinEventLog:Security** — EventCode=4728, 4729, 4732, 4733, 4756, 4757

## Analytics using this component

- [AN0103 - Analytic 0103](../Analytics/AN0103.md)
- [AN0230 - Analytic 0230](../Analytics/AN0230.md)
- [AN0265 - Analytic 0265](../Analytics/AN0265.md)
- [AN0266 - Analytic 0266](../Analytics/AN0266.md)
- [AN0267 - Analytic 0267](../Analytics/AN0267.md)
- [AN0268 - Analytic 0268](../Analytics/AN0268.md)
- [AN0270 - Analytic 0270](../Analytics/AN0270.md)
- [AN0290 - Analytic 0290](../Analytics/AN0290.md)
- [AN0291 - Analytic 0291](../Analytics/AN0291.md)
- [AN0334 - Analytic 0334](../Analytics/AN0334.md)
- [AN0339 - Analytic 0339](../Analytics/AN0339.md)
- [AN0544 - Analytic 0544](../Analytics/AN0544.md)
- [AN0548 - Analytic 0548](../Analytics/AN0548.md)
- [AN0771 - Analytic 0771](../Analytics/AN0771.md)
- [AN0772 - Analytic 0772](../Analytics/AN0772.md)
- [AN0773 - Analytic 0773](../Analytics/AN0773.md)
- [AN0803 - Analytic 0803](../Analytics/AN0803.md)
- [AN0815 - Analytic 0815](../Analytics/AN0815.md)
- [AN0854 - Analytic 0854](../Analytics/AN0854.md)
- [AN0865 - Analytic 0865](../Analytics/AN0865.md)
- [AN0866 - Analytic 0866](../Analytics/AN0866.md)
- [AN0867 - Analytic 0867](../Analytics/AN0867.md)
- [AN0892 - Analytic 0892](../Analytics/AN0892.md)
- [AN0899 - Analytic 0899](../Analytics/AN0899.md)
- [AN0900 - Analytic 0900](../Analytics/AN0900.md)
- [AN0978 - Analytic 0978](../Analytics/AN0978.md)
- [AN0979 - Analytic 0979](../Analytics/AN0979.md)
- [AN1051 - Analytic 1051](../Analytics/AN1051.md)
- [AN1078 - Analytic 1078](../Analytics/AN1078.md)
- [AN1079 - Analytic 1079](../Analytics/AN1079.md)
- [AN1117 - Analytic 1117](../Analytics/AN1117.md)
- [AN1259 - Analytic 1259](../Analytics/AN1259.md)
- [AN1469 - Analytic 1469](../Analytics/AN1469.md)
- [AN1470 - Analytic 1470](../Analytics/AN1470.md)
- [AN1471 - Analytic 1471](../Analytics/AN1471.md)
- [AN1579 - Analytic 1579](../Analytics/AN1579.md)
- [AN1608 - Analytic 1608](../Analytics/AN1608.md)
- [AN2075 - Analytic 2075](../Analytics/AN2075.md)
- [AN2076 - Analytic 2076](../Analytics/AN2076.md)
- [AN2077 - Analytic 2077](../Analytics/AN2077.md)
