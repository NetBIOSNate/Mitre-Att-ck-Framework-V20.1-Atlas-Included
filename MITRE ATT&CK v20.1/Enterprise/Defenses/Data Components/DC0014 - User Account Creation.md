# DC0014 - User Account Creation

[Enterprise](../../README.md) / [Data Components](README.md)

The initial establishment of a new user, service, or machine account within an operating system, cloud environment, or identity management system.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0014)

## Log sources and channels

- **WinEventLog:Security** — EventCode=4720
- **azure:audit** — Add user
- **AWS:CloudTrail** — CreateUser
- **saas:zoom** — New user created
- **saas:slack** — admin.user.create
- **m365:unified** — Add user
- **auditd:SYSCALL** — adduser
- **docker:daemon** — ExecCreate + usermod or useradd
- **auditd:SYSCALL** — useradd or adduser executed
- **networkdevice:syslog** — username <user> privilege <level>
- **saas:okta** — user.lifecycle.create

## Analytics using this component

- [AN0006 - Analytic 0006](../Analytics/AN0006.md)
- [AN0899 - Analytic 0899](../Analytics/AN0899.md)
- [AN0900 - Analytic 0900](../Analytics/AN0900.md)
- [AN0901 - Analytic 0901](../Analytics/AN0901.md)
- [AN0902 - Analytic 0902](../Analytics/AN0902.md)
- [AN1001 - Analytic 1001](../Analytics/AN1001.md)
- [AN1077 - Analytic 1077](../Analytics/AN1077.md)
- [AN1078 - Analytic 1078](../Analytics/AN1078.md)
- [AN1079 - Analytic 1079](../Analytics/AN1079.md)
- [AN1080 - Analytic 1080](../Analytics/AN1080.md)
- [AN1235 - Analytic 1235](../Analytics/AN1235.md)
- [AN1236 - Analytic 1236](../Analytics/AN1236.md)
- [AN1240 - Analytic 1240](../Analytics/AN1240.md)
- [AN1604 - Analytic 1604](../Analytics/AN1604.md)
- [AN1605 - Analytic 1605](../Analytics/AN1605.md)
- [AN1607 - Analytic 1607](../Analytics/AN1607.md)
- [AN1608 - Analytic 1608](../Analytics/AN1608.md)
