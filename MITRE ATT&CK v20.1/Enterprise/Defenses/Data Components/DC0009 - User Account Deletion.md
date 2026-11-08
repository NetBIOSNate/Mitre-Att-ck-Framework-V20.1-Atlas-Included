# DC0009 - User Account Deletion

[Enterprise](../../README.md) / [Data Components](README.md)

The removal of a user, service, or machine account from an operating system, cloud identity management system, or directory service.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0009)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4726, 4657
- **esxi:hostd** — method=RemoveUser or esxcli system account remove invocation
- **m365:unified** — Remove-Mailbox, Set-Mailbox

## Analytics using this component

- [AN0113 - Analytic 0113](../Analytics/AN0113.md)
- [AN0337 - Analytic 0337](../Analytics/AN0337.md)
- [AN0338 - Analytic 0338](../Analytics/AN0338.md)
