# DC0066 - Active Directory Object Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes to AD objects (e.g., users, groups, OUs) are logged as Event ID 5136 (Object Modification) or 5163 (Attribute Changes). Examples:

- User Account: Modifying attributes (e.g., group membership, enabling/disabling accounts).
- Group Membership: Adding/removing members.
- OU: Changing properties/permissions (e.g., delegation).
- Service Account: Modifying SPNs or other attributes.
- Object Attributes: Changes to passwords, logon hours, or control flags.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0066)

## Log sources and channels

- **azure:activity** — Update conditionalAccessPolicy
- **esxi:vpxa** — vim.SessionManager.login / vim.AccountManager.createUser
- **WinEventLog:Security** — EventCode=5163
- **WinEventLog:Security** — EventCode=4739
- **azure:signinlogs** — Add certificate credential, Update certificate credential
- **m365:dirsync** — Replication cookie changes involving Configuration partition with new server/nTDSDSA objects.
- **WinEventLog:Security** — EventCode=5136
- **WinEventLog:Security** — EventCode=4663, 4670, 4656
- **esxi:vpxd** — permission change operations on datastores or VMs
- **m365:unified** — Set-Mailbox, Set-AppPassword, Add-MailboxPermission
- **m365:unified** — Add app role assignment grant to user: Consent to application by privileged or unexpected accounts

## Analytics using this component

- [AN0088 - Analytic 0088](../Analytics/AN0088.md)
- [AN0269 - Analytic 0269](../Analytics/AN0269.md)
- [AN0383 - Analytic 0383](../Analytics/AN0383.md)
- [AN0543 - Analytic 0543](../Analytics/AN0543.md)
- [AN0674 - Analytic 0674](../Analytics/AN0674.md)
- [AN0755 - Analytic 0755](../Analytics/AN0755.md)
- [AN0770 - Analytic 0770](../Analytics/AN0770.md)
- [AN0786 - Analytic 0786](../Analytics/AN0786.md)
- [AN0814 - Analytic 0814](../Analytics/AN0814.md)
- [AN0834 - Analytic 0834](../Analytics/AN0834.md)
- [AN0837 - Analytic 0837](../Analytics/AN0837.md)
- [AN0854 - Analytic 0854](../Analytics/AN0854.md)
- [AN1177 - Analytic 1177](../Analytics/AN1177.md)
- [AN1253 - Analytic 1253](../Analytics/AN1253.md)
- [AN1259 - Analytic 1259](../Analytics/AN1259.md)
- [AN1471 - Analytic 1471](../Analytics/AN1471.md)
- [AN1487 - Analytic 1487](../Analytics/AN1487.md)
- [AN1621 - Analytic 1621](../Analytics/AN1621.md)
