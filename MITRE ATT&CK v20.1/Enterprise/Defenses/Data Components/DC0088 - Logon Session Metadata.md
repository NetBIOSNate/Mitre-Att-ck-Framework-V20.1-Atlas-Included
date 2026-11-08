# DC0088 - Logon Session Metadata

[Enterprise](../../README.md) / [Data Components](README.md)

Contextual data about a logon session, such as username, logon type, access tokens (security context, user SIDs, logon identifiers, and logon SID), and any activity associated within it

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0088)

## Log sources and channels

- **Logon Session** — None
- **WinEventLog:Security** — EventCode=4672
- **macos:unifiedlog** — LoginWindow context with associated PID linked to reopened plist paths
- **WinEventLog:Security** — EventCode=4672, 4634
- **azure:signinlogs** — SAML-based login with anomalous issuer or NotOnOrAfter lifetime
- **m365:unified** — Abnormal user claims or unexpected elevated role assignment in SAML assertion
- **macos:unifiedlog** — authd generating multiple MFA token requests
- **linux:syslog** — None
- **WinEventLog:Security** — EventCode=4624, 4625, 4768, 4769
- **linux:syslog** — sssd / sudo logs
- **esxi:hostd** — /var/log/hostd.log
- **WinEventLog:Security** — EventCode=4778, EventCode=4779
- **auditd:SYSCALL** — ssh logins or execve of remote commands
- **macos:unifiedlog** — Remote login (ssh) or screen sharing authentication attempts
- **kubernetes:audit** — Unauthorized container creation or kubelet exec logs
- **auditd:USER_LOGIN** — USER_LOGIN
- **macos:unifiedlog** — loginwindow or sshd
- **WinEventLog:Security** — EventCode=4800, 4801
- **WinEventLog:Security** — EventCode=4776, 4771, 4770
- **auditd:SYSCALL** — execve,socket,connect,openat
- **macos:unifiedlog** — Group membership change for admin or wheel
- **azure:audit** — Add delegated admin / Assign admin roles / Update application consent
- **saas:okta** — user.session.start, app.oauth2.as.authorize, policy.mfa.bypass
- **gcp:audit** — google.iam.credentials.generateAccessToken / serviceAccountTokenCreator
- **saas:salesforce** — ConnectedApp OAuth policy change / Login as user
- **macos:unifiedlog** — Unusual Kerberos TGS-REQ without TGT or anomalous ticket lifetime
- **saas:okta** — user.authentication.sso
- **m365:unified** — FileAccessed, SharingSet
- **m365:signinlogs** — UserLogin
- **macos:unifiedlog** — loginwindow, sshd
- **NSM:Connections** — Successful sudo or ssh from unknown IPs
- **macos:unifiedlog** — loginwindow or sshd events with external IP
- **macos:unifiedlog** — process = 'sshd'
- **esxi:auth** — None
- **vpn:authlog** — Industrial Control Systems (ICS)-role account authentication from source geolocation/Autonomous System Number (ASN) not in approved remote access origins or outside expected session pattern
- **syslog:auth** — authentication attempt or success from internet-sourced Internet Protocol (IP) address not in organizational IP space
- **syslog:auth** — Secure Shell (SSH) session from Virtual Private Network (VPN)-assigned Internet Protocol (IP) address correlated with remote access authentication anomaly
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4672 for Industrial Control Systems (ICS)-role account from anomalous session
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4672 for Industrial Control Systems (ICS)-role account without corresponding admin-group logon in preceding session
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: inbound authentication attempt or successful session from internet-sourced Internet Protocol (IP) address to Industrial Control Systems (ICS) application port

## Analytics using this component

- [AN0061 - Analytic 0061](../Analytics/AN0061.md)
- [AN0147 - Analytic 0147](../Analytics/AN0147.md)
- [AN0170 - Analytic 0170](../Analytics/AN0170.md)
- [AN0349 - Analytic 0349](../Analytics/AN0349.md)
- [AN0405 - Analytic 0405](../Analytics/AN0405.md)
- [AN0418 - Analytic 0418](../Analytics/AN0418.md)
- [AN0421 - Analytic 0421](../Analytics/AN0421.md)
- [AN0444 - Analytic 0444](../Analytics/AN0444.md)
- [AN0454 - Analytic 0454](../Analytics/AN0454.md)
- [AN0505 - Analytic 0505](../Analytics/AN0505.md)
- [AN0590 - Analytic 0590](../Analytics/AN0590.md)
- [AN0591 - Analytic 0591](../Analytics/AN0591.md)
- [AN0593 - Analytic 0593](../Analytics/AN0593.md)
- [AN0675 - Analytic 0675](../Analytics/AN0675.md)
- [AN0786 - Analytic 0786](../Analytics/AN0786.md)
- [AN0871 - Analytic 0871](../Analytics/AN0871.md)
- [AN0931 - Analytic 0931](../Analytics/AN0931.md)
- [AN0975 - Analytic 0975](../Analytics/AN0975.md)
- [AN1005 - Analytic 1005](../Analytics/AN1005.md)
- [AN1006 - Analytic 1006](../Analytics/AN1006.md)
- [AN1007 - Analytic 1007](../Analytics/AN1007.md)
- [AN1094 - Analytic 1094](../Analytics/AN1094.md)
- [AN1137 - Analytic 1137](../Analytics/AN1137.md)
- [AN1138 - Analytic 1138](../Analytics/AN1138.md)
- [AN1139 - Analytic 1139](../Analytics/AN1139.md)
- [AN1182 - Analytic 1182](../Analytics/AN1182.md)
- [AN1253 - Analytic 1253](../Analytics/AN1253.md)
- [AN1284 - Analytic 1284](../Analytics/AN1284.md)
- [AN1344 - Analytic 1344](../Analytics/AN1344.md)
- [AN1345 - Analytic 1345](../Analytics/AN1345.md)
- [AN1346 - Analytic 1346](../Analytics/AN1346.md)
- [AN1347 - Analytic 1347](../Analytics/AN1347.md)
- [AN1348 - Analytic 1348](../Analytics/AN1348.md)
- [AN1349 - Analytic 1349](../Analytics/AN1349.md)
- [AN1375 - Analytic 1375](../Analytics/AN1375.md)
- [AN1398 - Analytic 1398](../Analytics/AN1398.md)
- [AN1419 - Analytic 1419](../Analytics/AN1419.md)
- [AN1443 - Analytic 1443](../Analytics/AN1443.md)
- [AN1445 - Analytic 1445](../Analytics/AN1445.md)
- [AN1503 - Analytic 1503](../Analytics/AN1503.md)
- [AN1505 - Analytic 1505](../Analytics/AN1505.md)
- [AN1506 - Analytic 1506](../Analytics/AN1506.md)
- [AN1545 - Analytic 1545](../Analytics/AN1545.md)
- [AN1623 - Analytic 1623](../Analytics/AN1623.md)
- [AN1624 - Analytic 1624](../Analytics/AN1624.md)
- [AN1639 - Analytic 1639](../Analytics/AN1639.md)
- [AN1640 - Analytic 1640](../Analytics/AN1640.md)
