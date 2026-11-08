# DC0012 - Scheduled Job Modification

[ICS](../../README.md) / [Data Components](README.md)

Changes made to an existing scheduled job, including modifications to its execution parameters, command payload, or execution timing.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0012)

## Log sources and channels

- **Scheduled Job** — None
- **auditd:CONFIG_CHANGE** — /var/log/audit/audit.log
- **m365:exchange** — Remove-InboxRule, Clear-Mailbox
- **WinEventLog:Security** — EventCode=4702
