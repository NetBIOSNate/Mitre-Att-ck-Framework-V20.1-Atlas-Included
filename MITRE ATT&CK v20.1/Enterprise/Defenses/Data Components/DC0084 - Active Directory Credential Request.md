# DC0084 - Active Directory Credential Request

[Enterprise](../../README.md) / [Data Components](README.md)

Requests for authentication credentials via Kerberos or other methods like NTLM and LDAP queries. Examples:

- Kerberos TGT and Service Tickets (Event IDs 4768, 4769)
- NTLM Authentication Events
- LDAP Bind Requests.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0084)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4768
- **WinEventLog:Security** — EventCode=4769
- **WinEventLog:Kerberos** — Kerberos TGS-REQ anomalies without KDC validation (Silver Ticket behavior)
- **WinEventLog:Security** — EventCode=4929
- **linux:syslog** — Unusual kinit or klist activity

## Analytics using this component

- [AN0316 - Analytic 0316](../Analytics/AN0316.md)
- [AN0405 - Analytic 0405](../Analytics/AN0405.md)
- [AN0444 - Analytic 0444](../Analytics/AN0444.md)
- [AN0671 - Analytic 0671](../Analytics/AN0671.md)
- [AN0675 - Analytic 0675](../Analytics/AN0675.md)
- [AN0770 - Analytic 0770](../Analytics/AN0770.md)
- [AN1000 - Analytic 1000](../Analytics/AN1000.md)
- [AN1144 - Analytic 1144](../Analytics/AN1144.md)
- [AN1444 - Analytic 1444](../Analytics/AN1444.md)
