# M1047 - Audit

[Enterprise](../../README.md) / [Mitigations](README.md)

Auditing is the process of recording activity and systematically reviewing and analyzing the activity and system configurations. The primary purpose of auditing is to detect anomalies and identify potential threats or weaknesses in the environment. Proper auditing configurations can also help to meet compliance requirements. The process of auditing encompasses regular analysis of user behaviors and system logs in support of proactive security measures.

Auditing is applicable to all systems used within an organization, from the front door of a building to accessing a file on a fileserver. It is considered more critical for regulated industries such as, healthcare, finance and government where compliance requirements demand stringent tracking of user and system activates.This mitigation can be implemented through the following measures: 

System Audit:

- Use Case: Regularly assess system configurations to ensure compliance with organizational security policies.
- Implementation: Use tools to scan for deviations from established benchmarks.

Permission Audits:

- Use Case: Review file and folder permissions to minimize the risk of unauthorized access or privilege escalation.
- Implementation: Run access reviews to identify users or groups with excessive permissions.

Software Audits:

- Use Case: Identify outdated, unsupported, or insecure software that could serve as an attack vector.
- Implementation: Use inventory and vulnerability scanning tools to detect outdated versions and recommend secure alternatives.

Configuration Audits:

- Use Case: Evaluate system and network configurations to ensure secure settings (e.g., disabled SMBv1, enabled MFA).
- Implementation: Implement automated configuration scanning tools like SCAP (Security Content Automation Protocol) to identify non-compliant systems.

Network Audits:

- Use Case: Examine network traffic, firewall rules, and endpoint communications to identify unauthorized or insecure connections.
- Implementation: Utilize tools such as Wireshark, or Zeek to monitor and log suspicious network behavior.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1047)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1550.001 - Application Access Token](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1560 - Archive Collected Data](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/README.md)
- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1558.004 - AS-REP Roasting](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.004%20-%20AS-REP%20Roasting/README.md)
- [T1053.002 - At](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.002%20-%20At/README.md)
- [T1176.001 - Browser Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.001%20-%20Browser%20Extensions/README.md)
- [T1036.012 - Browser Fingerprint](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.012%20-%20Browser%20Fingerprint/README.md)
- [T1612 - Build Image on Host](../../Tactics/07%20TA0005%20-%20Stealth/T1612%20-%20Build%20Image%20on%20Host/README.md)
- [T1548.002 - Bypass User Account Control](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1558.005 - Ccache Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.005%20-%20Ccache%20Files/README.md)
- [T1552.008 - Chat Messages](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.008%20-%20Chat%20Messages/README.md)
- [T1070.008 - Clear Mailbox Data](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.008%20-%20Clear%20Mailbox%20Data/README.md)
- [T1087.004 - Cloud Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.004%20-%20Cloud%20Account/README.md)
- [T1671 - Cloud Application Integration](../../Tactics/05%20TA0003%20-%20Persistence/T1671%20-%20Cloud%20Application%20Integration/README.md)
- [T1686.001 - Cloud Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.001%20-%20Cloud%20Firewall/README.md)
- [T1213.003 - Code Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.003%20-%20Code%20Repositories/README.md)
- [T1593.003 - Code Repositories](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/T1593.003%20-%20Code%20Repositories/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1213.001 - Confluence](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.001%20-%20Confluence/README.md)
- [T1578.002 - Create Cloud Instance](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.002%20-%20Create%20Cloud%20Instance/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1578.001 - Create Snapshot](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.001%20-%20Create%20Snapshot/README.md)
- [T1552.001 - Credentials In Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1552.002 - Credentials in Registry](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.002%20-%20Credentials%20in%20Registry/README.md)
- [T1053.003 - Cron](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.003%20-%20Cron/README.md)
- [T1213.004 - Customer Relationship Management Software](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.004%20-%20Customer%20Relationship%20Management%20Software/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1213 - Data from Information Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1578.003 - Delete Cloud Instance](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.003%20-%20Delete%20Cloud%20Instance/README.md)
- [T1610 - Deploy Container](../../Tactics/04%20TA0002%20-%20Execution/T1610%20-%20Deploy%20Container/README.md)
- [T1685.004 - Disable or Modify Linux Audit System Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.004%20-%20Disable%20or%20Modify%20Linux%20Audit%20System%20Log/README.md)
- [T1686 - Disable or Modify System Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1685.001 - Disable or Modify Windows Event Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.001%20-%20Disable%20or%20Modify%20Windows%20Event%20Log/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1484 - Domain or Tenant Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/README.md)
- [T1482 - Domain Trust Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1114 - Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/README.md)
- [T1114.003 - Email Forwarding Rule](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.003%20-%20Email%20Forwarding%20Rule/README.md)
- [T1564.008 - Email Hiding Rules](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.008%20-%20Email%20Hiding%20Rules/README.md)
- [T1574.005 - Executable Installer File Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.005%20-%20Executable%20Installer%20File%20Permissions%20Weakness/README.md)
- [T1027.011 - Fileless Storage](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.011%20-%20Fileless%20Storage/README.md)
- [T1606 - Forge Web Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/README.md)
- [T1484.001 - Group Policy Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.001%20-%20Group%20Policy%20Modification/README.md)
- [T1552.006 - Group Policy Preferences](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.006%20-%20Group%20Policy%20Preferences/README.md)
- [T1564 - Hide Artifacts](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1556.007 - Hybrid Identity](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.007%20-%20Hybrid%20Identity/README.md)
- [T1176.002 - IDE Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.002%20-%20IDE%20Extensions/README.md)
- [T1505.004 - IIS Components](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.004%20-%20IIS%20Components/README.md)
- [T1685.007 - Impair Autonomous Defenses](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.007%20-%20Impair%20Autonomous%20Defenses/README.md)
- [T1525 - Implant Internal Image](../../Tactics/05%20TA0003%20-%20Persistence/T1525%20-%20Implant%20Internal%20Image/README.md)
- [T1543.004 - Launch Daemon](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.004%20-%20Launch%20Daemon/README.md)
- [T1546.006 - LC_LOAD_DYLIB Addition](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.006%20-%20LC_LOAD_DYLIB%20Addition/README.md)
- [T1059.011 - Lua](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.011%20-%20Lua/README.md)
- [T1204.003 - Malicious Image](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.003%20-%20Malicious%20Image/README.md)
- [T1036.010 - Masquerade Account Name](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.010%20-%20Masquerade%20Account%20Name/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1213.005 - Messaging Applications](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.005%20-%20Messaging%20Applications/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1578.005 - Modify Cloud Compute Configurations](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.005%20-%20Modify%20Cloud%20Compute%20Configurations/README.md)
- [T1578 - Modify Cloud Compute Infrastructure](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/README.md)
- [T1666 - Modify Cloud Resource Hierarchy](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1666%20-%20Modify%20Cloud%20Resource%20Hierarchy/README.md)
- [T1556.006 - Multi-Factor Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.006%20-%20Multi-Factor%20Authentication/README.md)
- [T1686.002 - Network Device Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.002%20-%20Network%20Device%20Firewall/README.md)
- [T1556.008 - Network Provider DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.008%20-%20Network%20Provider%20DLL/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1027 - Obfuscated Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1574.007 - Path Interception by PATH Environment Variable](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.007%20-%20Path%20Interception%20by%20PATH%20Environment%20Variable/README.md)
- [T1574.008 - Path Interception by Search Order Hijacking](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.008%20-%20Path%20Interception%20by%20Search%20Order%20Hijacking/README.md)
- [T1574.009 - Path Interception by Unquoted Path](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.009%20-%20Path%20Interception%20by%20Unquoted%20Path/README.md)
- [T1566 - Phishing](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/README.md)
- [T1653 - Power Settings](../../Tactics/05%20TA0003%20-%20Persistence/T1653%20-%20Power%20Settings/README.md)
- [T1542 - Pre-OS Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/README.md)
- [T1552.004 - Private Keys](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.004%20-%20Private%20Keys/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1021 - Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1542.004 - ROMMONkit](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.004%20-%20ROMMONkit/README.md)
- [T1564.006 - Run Virtual Instance](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.006%20-%20Run%20Virtual%20Instance/README.md)
- [T1606.002 - SAML Tokens](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/T1606.002%20-%20SAML%20Tokens/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1053 - Scheduled Task/Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/README.md)
- [T1593 - Search Open Websites/Domains](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1574.010 - Services File Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.010%20-%20Services%20File%20Permissions%20Weakness/README.md)
- [T1213.002 - Sharepoint](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.002%20-%20Sharepoint/README.md)
- [T1684 - Social Engineering](../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/README.md)
- [T1176 - Software Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1566.003 - Spearphishing via Service](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.003%20-%20Spearphishing%20via%20Service/README.md)
- [T1505.001 - SQL Stored Procedures](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.001%20-%20SQL%20Stored%20Procedures/README.md)
- [T1528 - Steal Application Access Token](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)
- [T1649 - Steal or Forge Authentication Certificates](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1649%20-%20Steal%20or%20Forge%20Authentication%20Certificates/README.md)
- [T1558 - Steal or Forge Kerberos Tickets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/README.md)
- [T1539 - Steal Web Session Cookie](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md)
- [T1548.006 - TCC Manipulation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.006%20-%20TCC%20Manipulation/README.md)
- [T1505.005 - Terminal Services DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.005%20-%20Terminal%20Services%20DLL/README.md)
- [T1542.005 - TFTP Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.005%20-%20TFTP%20Boot/README.md)
- [T1505.002 - Transport Agent](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.002%20-%20Transport%20Agent/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1550 - Use Alternate Authentication Material](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/README.md)
- [T1021.005 - VNC](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.005%20-%20VNC/README.md)
- [T1505.006 - vSphere Installation Bundles](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.006%20-%20vSphere%20Installation%20Bundles/README.md)
- [T1606.001 - Web Cookies](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/T1606.001%20-%20Web%20Cookies/README.md)
- [T1686.003 - Windows Host Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.003%20-%20Windows%20Host%20Firewall/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)
