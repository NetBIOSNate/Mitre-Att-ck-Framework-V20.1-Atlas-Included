# DC0067 - Logon Session Creation

[ICS](../../README.md) / [Data Components](README.md)

The successful establishment of a new user session following a successful authentication attempt. This typically signifies that a user has provided valid credentials or authentication tokens, and the system has initiated a session associated with that user account. This data is crucial for tracking authentication events and identifying potential unauthorized access. Examples: 

- Windows Systems
    - Event ID: 4624
        - Logon Type: 2 (Interactive) or 10 (Remote Interactive via RDP).
        - Account Name: JohnDoe
        - Source Network Address: 192.168.1.100
        - Authentication Package: NTLM
- Linux Systems
    - /var/log/utmp or /var/log/wtmp:
        - Log format: login user [tty] from [source_ip]
        - User: jane
        - IP: 10.0.0.5
        - Timestamp: 2024-12-28 08:30:00
- macOS Systems
    - /var/log/asl.log or unified logging framework:
        - Log: com.apple.securityd: Authentication succeeded for user 'admin'
- Cloud Environments
    - Azure Sign-In Logs:
        - Activity: Sign-in successful
        - Client App: Browser
        - Location: Unknown (Country: X)
- Google Workspace
    - Activity: Login
        - Event Type: successful_login
        - Source IP: 203.0.113.55

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0067)

## Log sources and channels

- **device:auth** — SSH/Telnet/console or vendor remote-management session 
- **auditd:SYSCALL** — capset or setns
- **AWS:CloudTrail** — ConsoleLogin, AssumeRole, ListResources
- **AWS:CloudTrail** — ConsoleLogin
- **AWS:CloudTrail** — Web console logins using session cookies without corresponding MFA event
- **AWS:CloudTrail** — ConsoleLogin: If IdP backed by cloud provider, Console login from new IP/agent after correlated endpoint compromise
- **AWS:CloudTrail** — SendSSHPublicKey, StartSession (SSM), EC2InstanceConnect
- **AWS:CloudTrail** — Temporary security credentials used to authenticate into management console or APIs
- **AWS:CloudTrail** — AWS ConsoleLogin, StartSession
- **AWS:CloudTrail** — GetConsoleOutput
- **AWS:CloudTrail** — sudden role assumption after credential file access
- **AWS:CloudTrail** — AssumeRole,AssumeRoleWithSAML,AssumeRoleWithWebIdentity
- **azure:ad** — SignInEvents
- **azure:signin** — UserLoginSuccess, TokenIssued
- **azure:signin** — Microsoft.Compute/virtualMachines/serialConsole/connect/action
- **azure:signinlogs** — Abnormal sign-in from scripting tools (PowerShell, AADInternals)
- **azure:signinlogs** — Suspicious login to cloud mailbox system
- **azure:signinlogs** — Failed MFA attempts, unusual conditional access triggers, login attempts from unexpected IP ranges
- **azure:signinlogs** — InteractiveUserLogin: Discovery behavior linked to privileged logins from atypical IP ranges
- **azure:signinlogs** — InteractiveUser, ServicePrincipalSignIn
- **azure:signinlogs** — InteractiveUser, NonInteractiveUser
- **azure:signinlogs** — UserLogin, ConditionalAccessPolicyEvaluated
- **CloudTrail:Signin** — SAML login without corresponding IdP authentication log
- **esxi:auth** — Shell login or escalation
- **esxi:vmkernel** — vim.fault.*, DCUI login, SSH shell
- **gcp:audit** — LoginAudit, DriveAudit
- **gcp:audit** — cloud.ssh.publicKey.inserted, compute.instances.osLogin
- **gcp:audit** — admin.googleapis.com
- **idp:session ** — New session established from source/device inconsistent with account baseline 
- **linux:auth** — User login event followed by unexpected process tree
- **linux:syslog** — auth.log/secure.log; SSH or console session context 
- **linux:syslog** — sshd: Accepted password/publickey
- **linux:syslog** — authentication success after file access
- **linux:syslog** — auth.log / secure.log
- **linux:syslog** — Accepted publickey/password for * from * port * ssh2
- **linux:syslog** — None
- **Logon Session** — None
- **m365:sharepoint** — File access with forged or anomalous SAML claims
- **m365:signinlogs** — SignInSuccess, RoleAssignmentRead
- **m365:signinlogs** — Token usage events with device/user mismatch
- **m365:signinlogs** — UserLogin: Discovery operations shortly after account logins from new geolocations
- **m365:signinlogs** — UserLoggedIn
- **m365:unified** — UserLoggedIn
- **m365:unified** — ViewAdminReport
- **macos:unifiedlog** — UserLoggedIn
- **macos:unifiedlog** — Authentication inconsistencies where commands are executed without corresponding login events
- **macos:unifiedlog** — authentication
- **macos:unifiedlog** — Session reuse without new auth event
- **macos:unifiedlog** — Access to Keychain items or browser credential stores
- **macos:unifiedlog** — eventMessage CONTAINS 'screensharingd' or 'AuthorizationRefCreate'
- **macos:unifiedlog** — Keychain or user login post-access
- **macos:unifiedlog** — authentication plugin load or modification events
- **macos:unifiedlog** — loginwindow or sshd successful login events
- **networkdevice:auth** — SSH/Telnet/console authentication and session creation
- **networkdevice:Firewall** — Login from untrusted IP, or new admin account accessing firewall console/API
- **NSM:Connections** — Mismatch between recorded user logon and active sessions (e.g., wtmp/utmp entries without corresponding authentication in auth.log)
- **NSM:Connections** — Missing new login event but session activity continues
- **NSM:Connections** — Accepted publickey for user from unusual IP or without tty
- **NSM:Connections** — simultaneous or anomalous logon sessions across multiple systems
- **Okta:SystemLog** — user.authentication.sso, app.oauth.grant
- **saas:access** — Multiple concurrent logins using same cookie from different locations
- **saas:auth** — LoginSuccess, APIKeyUse, AdminAction
- **saas:auth** — Login, TokenGranted: Discovery actions tied to anomalous login sessions or tokens
- **saas:confluence** — logon
- **saas:github** — Login from unusual IP, device fingerprint, or location; access token creation from new client
- **saas:okta** — user.session.start
- **saas:okta** — session.token.reuse
- **saas:session ** — New authenticated session associated with changed source/client context 
- **saas:zoom** — Zoom Admin Dashboard accessed from unfamiliar IP/device
- **WinEventLog:Security** — EventCode=4624, 4648
- **WinEventLog:Security** — Anomalous logon without MFA enforcement
- **WinEventLog:Security** — EventCode=4624
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): sudo/su success for Industrial Control Systems (ICS) service account UID without the expected automated invocation pattern
- **syslog:auth** — Secure Shell (SSH) session between Industrial Control Systems (ICS) hosts not in approved lateral movement pairs
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624 by account not in authorized engineer accounts
- **wireless:radius** — Extensible Authentication Protocol (EAP) authentication success for device Media Access Control (MAC)/certificate not in approved wireless device inventory
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624 from a device Media Access Control (MAC) address/hardware-ID first observed on the network, not in approved device inventory
- **syslog:auth** — sshd Accepted for username matching default vendor credential list from source not in approved admin Classless Inter-Domain Routing (CIDR) subnet
- **syslog:auth** — sshd Accepted for username matching default or hardcoded credential patterns from source not in approved admin Classless Inter-Domain Routing (CIDR) subnet
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624 for Industrial Control Systems (ICS)-role account from workstation not in approved host list or outside office hours window
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624 for account matching default vendor credential list from source not in approved host list
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624, Type 2/10 to Industrial Control Systems (ICS) host from source not in approved operator workstations or account not in approved operator list
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624 for Industrial Control Systems (ICS)-role account from Virtual Private Network (VPN)-assigned Internet Protocol (IP) address correlated with remote access authentication anomaly
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624, Type 3/10 between Industrial Control Systems (ICS) hosts not in approved lateral movement pairs
- **WinEventLog:Security** — Windows Security Event ID 4624/4625: EventCode=4624 for account matching default or hardcoded credential patterns from source not in approved host list

## Analytics using this component

- [AN1857 - Analytic 1857](../Analytics/AN1857.md)
- [AN1859 - Analytic 1859](../Analytics/AN1859.md)
- [AN1877 - Analytic 1877](../Analytics/AN1877.md)
- [AN1886 - Analytic 1886](../Analytics/AN1886.md)
- [AN1888 - Analytic 1888](../Analytics/AN1888.md)
- [AN1904 - Analytic 1904](../Analytics/AN1904.md)
- [AN1936 - Analytic 1936](../Analytics/AN1936.md)
- [AN2048 - Analytic 2048](../Analytics/AN2048.md)
- [AN2088 - Analytic 2088](../Analytics/AN2088.md)
- [AN2089 - Analytic 2089](../Analytics/AN2089.md)
- [AN2090 - Analytic 2090](../Analytics/AN2090.md)
- [AN2122 - Analytic 2122](../Analytics/AN2122.md)
- [AN2159 - Analytic 2159](../Analytics/AN2159.md)
- [AN2255 - Analytic 2255](../Analytics/AN2255.md)
- [AN2258 - Analytic 2258](../Analytics/AN2258.md)
- [AN2265 - Analytic 2265](../Analytics/AN2265.md)
