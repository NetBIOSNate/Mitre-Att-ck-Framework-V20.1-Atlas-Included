# DC0087 - Active Directory Object Creation

[Enterprise](../../README.md) / [Data Components](README.md)

Creating new objects in AD, such as user accounts, groups, organizational units (OUs), or trust relationships. Logged as Event ID 5137. Examples:

- User Account Creation: New user account.
- Group Creation: New security/distribution group.
- OU Creation: New organizational unit.
- Service Account Creation: New service account for automation or malicious tasks.
- Trust Object Creation: Trust relationship with another domain.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0087)

## Log sources and channels

- **azure:audit** — New device object creation
- **WinEventLog:Security** — Device Object Creation
- **WinEventLog:Security** — EventCode=4928
- **AWS:CloudTrail** — CreateAccessKey, ImportKeyPair, CreateLoginProfile, CreateKeyPair

## Analytics using this component

- [AN0103 - Analytic 0103](../Analytics/AN0103.md)
- [AN0104 - Analytic 0104](../Analytics/AN0104.md)
- [AN0770 - Analytic 0770](../Analytics/AN0770.md)
- [AN1470 - Analytic 1470](../Analytics/AN1470.md)
