# S0413 - MailSniper

[Enterprise](../../../README.md) / [Tools](README.md)

MailSniper is a penetration testing tool for searching through email in a Microsoft Exchange environment for specific terms (passwords, insider intel, network architecture information, etc.). It can be used by a non-administrative user to search their own email, or by an Exchange administrator to search the mailboxes of every user in a domain.(Citation: GitHub MailSniper)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0413)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Techniques used

- [T1087.003 - Email Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.003%20-%20Email%20Account/README.md)
- [T1110.003 - Password Spraying](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1114.002 - Remote Email Collection](../../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.002%20-%20Remote%20Email%20Collection/README.md)

## Used by

- [G0077 - Leafminer](../../Groups/G0077%20-%20Leafminer.md)

## Sources

- [GitHub MailSniper](https://github.com/dafthack/MailSniper)
