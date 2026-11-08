# M1018 - User Account Management

[Enterprise](../../README.md) / [Mitigations](README.md)

User Account Management involves implementing and enforcing policies for the lifecycle of user accounts, including creation, modification, and deactivation. Proper account management reduces the attack surface by limiting unauthorized access, managing account privileges, and ensuring accounts are used according to organizational policies. This mitigation can be implemented through the following measures:

Enforcing the Principle of Least Privilege

- Implementation: Assign users only the minimum permissions required to perform their job functions. Regularly audit accounts to ensure no excess permissions are granted.
- Use Case: Reduces the risk of privilege escalation by ensuring accounts cannot perform unauthorized actions.

Implementing Strong Password Policies

- Implementation: Enforce password complexity requirements (e.g., length, character types). Require password expiration every 90 days and disallow password reuse.
- Use Case: Prevents adversaries from gaining unauthorized access through password guessing or brute force attacks.

Managing Dormant and Orphaned Accounts

- Implementation: Implement automated workflows to disable accounts after a set period of inactivity (e.g., 30 days). Remove orphaned accounts (e.g., accounts without an assigned owner) during regular account audits.
- Use Case: Eliminates dormant accounts that could be exploited by attackers.

Account Lockout Policies

- Implementation: Configure account lockout thresholds (e.g., lock accounts after five failed login attempts). Set lockout durations to a minimum of 15 minutes.
- Use Case: Mitigates automated attack techniques that rely on repeated login attempts.

Multi-Factor Authentication (MFA) for High-Risk Accounts

- Implementation: Require MFA for all administrative accounts and high-risk users. Use MFA mechanisms like hardware tokens, authenticator apps, or biometrics.
- Use Case: Prevents unauthorized access, even if credentials are stolen.

Restricting Interactive Logins

- Implementation: Restrict interactive logins for privileged accounts to specific secure systems or management consoles. Use group policies to enforce logon restrictions.
- Use Case: Protects sensitive accounts from misuse or exploitation.

*Tools for Implementation*

Built-in Tools:

- Microsoft Active Directory (AD): Centralized account management and RBAC enforcement.
- Group Policy Object (GPO): Enforce password policies, logon restrictions, and account lockout policies.

Identity and Access Management (IAM) Tools:

- Okta: Centralized user provisioning, MFA, and SSO integration.
- Microsoft Azure Active Directory: Provides advanced account lifecycle management, role-based access, and conditional access policies.

Privileged Account Management (PAM):
- CyberArk, BeyondTrust, Thycotic: Manage and monitor privileged account usage, enforce session recording, and JIT access.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1018)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1134 - Access Token Manipulation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/README.md)
- [T1087 - Account Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/README.md)
- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1098.001 - Additional Cloud Credentials](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.001%20-%20Additional%20Cloud%20Credentials/README.md)
- [T1098.003 - Additional Cloud Roles](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.003%20-%20Additional%20Cloud%20Roles/README.md)
- [T1098.006 - Additional Container Cluster Roles](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.006%20-%20Additional%20Container%20Cluster%20Roles/README.md)
- [T1053.002 - At](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.002%20-%20At/README.md)
- [T1197 - BITS Jobs](../../Tactics/04%20TA0002%20-%20Execution/T1197%20-%20BITS%20Jobs/README.md)
- [T1185 - Browser Session Hijacking](../../Tactics/12%20TA0009%20-%20Collection/T1185%20-%20Browser%20Session%20Hijacking/README.md)
- [T1110 - Brute Force](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1087.004 - Cloud Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.004%20-%20Cloud%20Account/README.md)
- [T1078.004 - Cloud Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1686.001 - Cloud Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.001%20-%20Cloud%20Firewall/README.md)
- [T1580 - Cloud Infrastructure Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1580%20-%20Cloud%20Infrastructure%20Discovery/README.md)
- [T1538 - Cloud Service Dashboard](../../Tactics/10%20TA0007%20-%20Discovery/T1538%20-%20Cloud%20Service%20Dashboard/README.md)
- [T1619 - Cloud Storage Object Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1619%20-%20Cloud%20Storage%20Object%20Discovery/README.md)
- [T1213.003 - Code Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.003%20-%20Code%20Repositories/README.md)
- [T1556.009 - Conditional Access Policies](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.009%20-%20Conditional%20Access%20Policies/README.md)
- [T1213.001 - Confluence](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.001%20-%20Confluence/README.md)
- [T1609 - Container Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1609%20-%20Container%20Administration%20Command/README.md)
- [T1613 - Container and Resource Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1613%20-%20Container%20and%20Resource%20Discovery/README.md)
- [T1552.007 - Container API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.007%20-%20Container%20API/README.md)
- [T1053.007 - Container Orchestration Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.007%20-%20Container%20Orchestration%20Job/README.md)
- [T1543.005 - Container Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.005%20-%20Container%20Service/README.md)
- [T1574.012 - COR_PROFILER](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.012%20-%20COR_PROFILER/README.md)
- [T1578.002 - Create Cloud Instance](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.002%20-%20Create%20Cloud%20Instance/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1134.002 - Create Process with Token](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.002%20-%20Create%20Process%20with%20Token/README.md)
- [T1578.001 - Create Snapshot](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.001%20-%20Create%20Snapshot/README.md)
- [T1110.004 - Credential Stuffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.004%20-%20Credential%20Stuffing/README.md)
- [T1555.003 - Credentials from Web Browsers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1053.003 - Cron](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.003%20-%20Cron/README.md)
- [T1213.004 - Customer Relationship Management Software](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.004%20-%20Customer%20Relationship%20Management%20Software/README.md)
- [T1485 - Data Destruction](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1213 - Data from Information Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1578.003 - Delete Cloud Instance](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.003%20-%20Delete%20Cloud%20Instance/README.md)
- [T1610 - Deploy Container](../../Tactics/04%20TA0002%20-%20Execution/T1610%20-%20Deploy%20Container/README.md)
- [T1021.008 - Direct Cloud VM Connections](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.008%20-%20Direct%20Cloud%20VM%20Connections/README.md)
- [T1699 - Direct Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1699%20-%20Direct%20Prompt%20Injection/README.md)
- [T1006 - Direct Volume Access](../../Tactics/07%20TA0005%20-%20Stealth/T1006%20-%20Direct%20Volume%20Access/README.md)
- [T1685.002 - Disable or Modify Cloud Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.002%20-%20Disable%20or%20Modify%20Cloud%20Log/README.md)
- [T1685.004 - Disable or Modify Linux Audit System Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.004%20-%20Disable%20or%20Modify%20Linux%20Audit%20System%20Log/README.md)
- [T1686 - Disable or Modify System Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1685.001 - Disable or Modify Windows Event Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.001%20-%20Disable%20or%20Modify%20Windows%20Event%20Log/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1484 - Domain or Tenant Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/README.md)
- [T1675 - ESXi Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1675%20-%20ESXi%20Administration%20Command/README.md)
- [T1574.005 - Executable Installer File Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.005%20-%20Executable%20Installer%20File%20Permissions%20Weakness/README.md)
- [T1048 - Exfiltration Over Alternative Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/README.md)
- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1606 - Forge Web Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/README.md)
- [T1484.001 - Group Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.001%20-%20Group%20Policy%20Modification/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1685.007 - Impair Autonomous Defenses](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.007%20-%20Impair%20Autonomous%20Defenses/README.md)
- [T1698 - Indirect Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1698%20-%20Indirect%20Prompt%20Injection/README.md)
- [T1490 - Inhibit System Recovery](../../Tactics/15%20TA0040%20-%20Impact/T1490%20-%20Inhibit%20System%20Recovery/README.md)
- [T1547.006 - Kernel Modules and Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.006%20-%20Kernel%20Modules%20and%20Extensions/README.md)
- [T1543.004 - Launch Daemon](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.004%20-%20Launch%20Daemon/README.md)
- [T1569.001 - Launchctl](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.001%20-%20Launchctl/README.md)
- [T1485.001 - Lifecycle-Triggered Deletion](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/T1485.001%20-%20Lifecycle-Triggered%20Deletion/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1654 - Log Enumeration](../../Tactics/10%20TA0007%20-%20Discovery/T1654%20-%20Log%20Enumeration/README.md)
- [T1134.003 - Make and Impersonate Token](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.003%20-%20Make%20and%20Impersonate%20Token/README.md)
- [T1036.010 - Masquerade Account Name](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.010%20-%20Masquerade%20Account%20Name/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1578.005 - Modify Cloud Compute Configurations](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.005%20-%20Modify%20Cloud%20Compute%20Configurations/README.md)
- [T1578 - Modify Cloud Compute Infrastructure](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/README.md)
- [T1666 - Modify Cloud Resource Hierarchy](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1666%20-%20Modify%20Cloud%20Resource%20Hierarchy/README.md)
- [T1556.006 - Multi-Factor Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.006%20-%20Multi-Factor%20Authentication/README.md)
- [T1059.008 - Network Device CLI](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.008%20-%20Network%20Device%20CLI/README.md)
- [T1686.002 - Network Device Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.002%20-%20Network%20Device%20Firewall/README.md)
- [T1040 - Network Sniffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1550.003 - Pass the Ticket](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.003%20-%20Pass%20the%20Ticket/README.md)
- [T1555.005 - Password Managers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.005%20-%20Password%20Managers/README.md)
- [T1677 - Poisoned Pipeline Execution](../../Tactics/04%20TA0002%20-%20Execution/T1677%20-%20Poisoned%20Pipeline%20Execution/README.md)
- [T1547.012 - Print Processors](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.012%20-%20Print%20Processors/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1563 - Remote Service Session Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/README.md)
- [T1021 - Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1606.002 - SAML Tokens](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/T1606.002%20-%20SAML%20Tokens/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1053 - Scheduled Task/Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1648 - Serverless Execution](../../Tactics/04%20TA0002%20-%20Execution/T1648%20-%20Serverless%20Execution/README.md)
- [T1489 - Service Stop](../../Tactics/15%20TA0040%20-%20Impact/T1489%20-%20Service%20Stop/README.md)
- [T1574.010 - Services File Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.010%20-%20Services%20File%20Permissions%20Weakness/README.md)
- [T1213.002 - Sharepoint](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.002%20-%20Sharepoint/README.md)
- [T1547.009 - Shortcut Modification](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.009%20-%20Shortcut%20Modification/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1566.003 - Spearphishing via Service](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.003%20-%20Spearphishing%20via%20Service/README.md)
- [T1021.004 - SSH](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.004%20-%20SSH/README.md)
- [T1098.004 - SSH Authorized Keys](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.004%20-%20SSH%20Authorized%20Keys/README.md)
- [T1528 - Steal Application Access Token](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)
- [T1697 - Steal Application Specific Passwords](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1697%20-%20Steal%20Application%20Specific%20Passwords/README.md)
- [T1195 - Supply Chain Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md)
- [T1569 - System Services](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/README.md)
- [T1569.003 - Systemctl](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.003%20-%20Systemctl/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1053.006 - Systemd Timers](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.006%20-%20Systemd%20Timers/README.md)
- [T1548.005 - Temporary Elevated Cloud Access](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.005%20-%20Temporary%20Elevated%20Cloud%20Access/README.md)
- [T1134.001 - Token Impersonation/Theft](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.001%20-%20Token%20Impersonation%20-%20Theft/README.md)
- [T1020.001 - Traffic Duplication](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/T1020.001%20-%20Traffic%20Duplication/README.md)
- [T1537 - Transfer Data to Cloud Account](../../Tactics/14%20TA0010%20-%20Exfiltration/T1537%20-%20Transfer%20Data%20to%20Cloud%20Account/README.md)
- [T1484.002 - Trust Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.002%20-%20Trust%20Modification/README.md)
- [T1199 - Trusted Relationship](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1199%20-%20Trusted%20Relationship/README.md)
- [T1550 - Use Alternate Authentication Material](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1686.003 - Windows Host Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.003%20-%20Windows%20Host%20Firewall/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)
- [T1547.004 - Winlogon Helper DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.004%20-%20Winlogon%20Helper%20DLL/README.md)
- [T1547.013 - XDG Autostart Entries](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.013%20-%20XDG%20Autostart%20Entries/README.md)
