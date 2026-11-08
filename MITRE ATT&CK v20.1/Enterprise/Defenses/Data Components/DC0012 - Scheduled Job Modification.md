# DC0012 - Scheduled Job Modification

[Enterprise](../../README.md) / [Data Components](README.md)

Changes made to an existing scheduled job, including modifications to its execution parameters, command payload, or execution timing.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0012)

## Log sources and channels

- **Scheduled Job** — None
- **auditd:CONFIG_CHANGE** — /var/log/audit/audit.log
- **m365:exchange** — Remove-InboxRule, Clear-Mailbox
- **WinEventLog:Security** — EventCode=4702

## Analytics using this component

- [AN0325 - Analytic 0325](../Analytics/AN0325.md)
- [AN0525 - Analytic 0525](../Analytics/AN0525.md)
- [AN1221 - Analytic 1221](../Analytics/AN1221.md)
