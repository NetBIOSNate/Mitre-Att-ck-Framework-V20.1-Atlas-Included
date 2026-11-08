# DC0088 - Logon Session Metadata

[ICS](../../README.md) / [Data Components](README.md)

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

- [AN1857 - Analytic 1857](../Analytics/AN1857.md)
- [AN1928 - Analytic 1928](../Analytics/AN1928.md)
- [AN1935 - Analytic 1935](../Analytics/AN1935.md)
- [AN2256 - Analytic 2256](../Analytics/AN2256.md)
- [AN2257 - Analytic 2257](../Analytics/AN2257.md)
- [AN2261 - Analytic 2261](../Analytics/AN2261.md)
