# M1026 - Privileged Account Management

[Enterprise](../../README.md) / [Mitigations](README.md)

Privileged Account Management focuses on implementing policies, controls, and tools to securely manage privileged accounts (e.g., SYSTEM, root, or administrative accounts). This includes restricting access, limiting the scope of permissions, monitoring privileged account usage, and ensuring accountability through logging and auditing.This mitigation can be implemented through the following measures:

Account Permissions and Roles:

- Implement RBAC and least privilege principles to allocate permissions securely.
- Use tools like Active Directory Group Policies to enforce access restrictions.

Credential Security:

- Deploy password vaulting tools like CyberArk, HashiCorp Vault, or KeePass for secure storage and rotation of credentials.
- Enforce password policies for complexity, uniqueness, and expiration using tools like Microsoft Group Policy Objects (GPO).

Multi-Factor Authentication (MFA):

- Enforce MFA for all privileged accounts using Duo Security, Okta, or Microsoft Azure AD MFA.

Privileged Access Management (PAM):

- Use PAM solutions like CyberArk, BeyondTrust, or Thycotic to manage, monitor, and audit privileged access.

Auditing and Monitoring:

- Integrate activity monitoring into your SIEM (e.g., Splunk or QRadar) to detect and alert on anomalous privileged account usage.

Just-In-Time Access:

- Deploy JIT solutions like Azure Privileged Identity Management (PIM) or configure ephemeral roles in AWS and GCP to grant time-limited elevated permissions.

*Tools for Implementation*

Privileged Access Management (PAM):

- CyberArk, BeyondTrust, Thycotic, HashiCorp Vault.

Credential Management:

- Microsoft LAPS (Local Admin Password Solution), Password Safe, HashiCorp Vault, KeePass.

Multi-Factor Authentication:

- Duo Security, Okta, Microsoft Azure MFA, Google Authenticator.

Linux Privilege Management:

- sudo configuration, SELinux, AppArmor.

Just-In-Time Access:

- Azure Privileged Identity Management (PIM), AWS IAM Roles with session constraints, GCP Identity-Aware Proxy.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1026)

## Mitigated techniques

- [T1003.008 - /etc/passwd and /etc/shadow](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.008%20-%20etc%20-%20passwd%20and%20-%20etc%20-%20shadow/README.md)
- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1134 - Access Token Manipulation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/README.md)
- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1098.001 - Additional Cloud Credentials](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.001%20-%20Additional%20Cloud%20Credentials/README.md)
- [T1098.003 - Additional Cloud Roles](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.003%20-%20Additional%20Cloud%20Roles/README.md)
- [T1098.002 - Additional Email Delegate Permissions](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.002%20-%20Additional%20Email%20Delegate%20Permissions/README.md)
- [T1053.002 - At](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.002%20-%20At/README.md)
- [T1542.003 - Bootkit](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.003%20-%20Bootkit/README.md)
- [T1612 - Build Image on Host](../../Tactics/07%20TA0005%20-%20Stealth/T1612%20-%20Build%20Image%20on%20Host/README.md)
- [T1548.002 - Bypass User Account Control](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1003.005 - Cached Domain Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.005%20-%20Cached%20Domain%20Credentials/README.md)
- [T1136.003 - Cloud Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.003%20-%20Cloud%20Account/README.md)
- [T1078.004 - Cloud Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1651 - Cloud Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1651%20-%20Cloud%20Administration%20Command/README.md)
- [T1059.009 - Cloud API](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.009%20-%20Cloud%20API/README.md)
- [T1555.006 - Cloud Secrets Management Stores](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.006%20-%20Cloud%20Secrets%20Management%20Stores/README.md)
- [T1021.007 - Cloud Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.007%20-%20Cloud%20Services/README.md)
- [T1553.006 - Code Signing Policy Modification](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.006%20-%20Code%20Signing%20Policy%20Modification/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1559.001 - Component Object Model](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.001%20-%20Component%20Object%20Model/README.md)
- [T1609 - Container Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1609%20-%20Container%20Administration%20Command/README.md)
- [T1552.007 - Container API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.007%20-%20Container%20API/README.md)
- [T1059.013 - Container CLI/API](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.013%20-%20Container%20CLI%20-%20API/README.md)
- [T1053.007 - Container Orchestration Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.007%20-%20Container%20Orchestration%20Job/README.md)
- [T1136 - Create Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1134.002 - Create Process with Token](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.002%20-%20Create%20Process%20with%20Token/README.md)
- [T1555 - Credentials from Password Stores](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1552.002 - Credentials in Registry](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.002%20-%20Credentials%20in%20Registry/README.md)
- [T1003.006 - DCSync](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.006%20-%20DCSync/README.md)
- [T1699 - Direct Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1699%20-%20Direct%20Prompt%20Injection/README.md)
- [T1021.003 - Distributed Component Object Model](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.003%20-%20Distributed%20Component%20Object%20Model/README.md)
- [T1136.002 - Domain Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1556.001 - Domain Controller Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.001%20-%20Domain%20Controller%20Authentication/README.md)
- [T1484 - Domain or Tenant Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/README.md)
- [T1601.002 - Downgrade System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.002%20-%20Downgrade%20System%20Image/README.md)
- [T1611 - Escape to Host](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md)
- [T1546 - Event Triggered Execution](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1210 - Exploitation of Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1222 - File and Directory Permissions Modification](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/README.md)
- [T1495 - Firmware Corruption](../../Tactics/15%20TA0040%20-%20Impact/T1495%20-%20Firmware%20Corruption/README.md)
- [T1606 - Forge Web Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/README.md)
- [T1558.001 - Golden Ticket](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.001%20-%20Golden%20Ticket/README.md)
- [T1556.007 - Hybrid Identity](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.007%20-%20Hybrid%20Identity/README.md)
- [T1505.004 - IIS Components](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.004%20-%20IIS%20Components/README.md)
- [T1685.007 - Impair Autonomous Defenses](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.007%20-%20Impair%20Autonomous%20Defenses/README.md)
- [T1525 - Implant Internal Image](../../Tactics/05%20TA0003%20-%20Persistence/T1525%20-%20Implant%20Internal%20Image/README.md)
- [T1698 - Indirect Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1698%20-%20Indirect%20Prompt%20Injection/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1558.003 - Kerberoasting](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.003%20-%20Kerberoasting/README.md)
- [T1547.006 - Kernel Modules and Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.006%20-%20Kernel%20Modules%20and%20Extensions/README.md)
- [T1222.002 - Linux and Mac Permissions](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/T1222.002%20-%20Linux%20and%20Mac%20Permissions/README.md)
- [T1136.001 - Local Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.001%20-%20Local%20Account/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1003.004 - LSA Secrets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.004%20-%20LSA%20Secrets/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1134.003 - Make and Impersonate Token](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.003%20-%20Make%20and%20Impersonate%20Token/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1601 - Modify System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/README.md)
- [T1218.007 - Msiexec](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.007%20-%20Msiexec/README.md)
- [T1599.001 - Network Address Translation Traversal](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/T1599.001%20-%20Network%20Address%20Translation%20Traversal/README.md)
- [T1599 - Network Boundary Bridging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/README.md)
- [T1556.004 - Network Device Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.004%20-%20Network%20Device%20Authentication/README.md)
- [T1059.008 - Network Device CLI](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.008%20-%20Network%20Device%20CLI/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1003 - OS Credential Dumping](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1550.003 - Pass the Ticket](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.003%20-%20Pass%20the%20Ticket/README.md)
- [T1601.001 - Patch System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.001%20-%20Patch%20System%20Image/README.md)
- [T1556.003 - Pluggable Authentication Modules](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.003%20-%20Pluggable%20Authentication%20Modules/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1542 - Pre-OS Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/README.md)
- [T1003.007 - Proc Filesystem](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.007%20-%20Proc%20Filesystem/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1055.008 - Ptrace System Calls](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.008%20-%20Ptrace%20System%20Calls/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1563 - Remote Service Session Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/README.md)
- [T1556.005 - Reversible Encryption](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.005%20-%20Reversible%20Encryption/README.md)
- [T1688 - Safe Mode Boot](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1688%20-%20Safe%20Mode%20Boot/README.md)
- [T1606.002 - SAML Tokens](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/T1606.002%20-%20SAML%20Tokens/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1053 - Scheduled Task/Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1558.002 - Silver Ticket](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.002%20-%20Silver%20Ticket/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1505.001 - SQL Stored Procedures](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.001%20-%20SQL%20Stored%20Procedures/README.md)
- [T1563.001 - SSH Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.001%20-%20SSH%20Hijacking/README.md)
- [T1558 - Steal or Forge Kerberos Tickets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/README.md)
- [T1553 - Subvert Trust Controls](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/README.md)
- [T1548.003 - Sudo and Sudo Caching](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.003%20-%20Sudo%20and%20Sudo%20Caching/README.md)
- [T1218 - System Binary Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1542.001 - System Firmware](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.001%20-%20System%20Firmware/README.md)
- [T1569 - System Services](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1053.006 - Systemd Timers](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.006%20-%20Systemd%20Timers/README.md)
- [T1548.006 - TCC Manipulation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.006%20-%20TCC%20Manipulation/README.md)
- [T1542.005 - TFTP Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.005%20-%20TFTP%20Boot/README.md)
- [T1134.001 - Token Impersonation/Theft](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.001%20-%20Token%20Impersonation%20-%20Theft/README.md)
- [T1505.002 - Transport Agent](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.002%20-%20Transport%20Agent/README.md)
- [T1484.002 - Trust Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.002%20-%20Trust%20Modification/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1550 - Use Alternate Authentication Material](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1056.003 - Web Portal Capture](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.003%20-%20Web%20Portal%20Capture/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)
- [T1222.001 - Windows Permissions](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/T1222.001%20-%20Windows%20Permissions/README.md)
- [T1021.006 - Windows Remote Management](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.006%20-%20Windows%20Remote%20Management/README.md)
