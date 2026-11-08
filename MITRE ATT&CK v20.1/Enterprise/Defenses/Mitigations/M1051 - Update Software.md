# M1051 - Update Software

[Enterprise](../../README.md) / [Mitigations](README.md)

Software updates ensure systems are protected against known vulnerabilities by applying patches and upgrades provided by vendors. Regular updates reduce the attack surface and prevent adversaries from exploiting known security gaps. This includes patching operating systems, applications, drivers, and firmware. This mitigation can be implemented through the following measures:

Regular Operating System Updates

- Implementation: Apply the latest Windows security updates monthly using WSUS (Windows Server Update Services) or a similar patch management solution. Configure systems to check for updates automatically and schedule reboots during maintenance windows.
- Use Case: Prevents exploitation of OS vulnerabilities such as privilege escalation or remote code execution.

Application Patching

- Implementation: Monitor Apache's update release notes for security patches addressing vulnerabilities. Schedule updates for off-peak hours to avoid downtime while maintaining security compliance.
- Use Case: Prevents exploitation of web application vulnerabilities, such as those leading to unauthorized access or data breaches.

Firmware Updates

- Implementation: Regularly check the vendor’s website for firmware updates addressing vulnerabilities. Plan for update deployment during scheduled maintenance to minimize business disruption.
- Use Case: Protects against vulnerabilities that adversaries could exploit to gain access to network devices or inject malicious traffic.

Emergency Patch Deployment

- Implementation: Use the emergency patch deployment feature of the organization's patch management tool to apply updates to all affected Exchange servers within 24 hours.
- Use Case: Reduces the risk of exploitation by rapidly addressing critical vulnerabilities.

Centralized Patch Management

- Implementation: Implement a centralized patch management system, such as SCCM or ManageEngine, to automate and track patch deployment across all environments. Generate regular compliance reports to ensure all systems are updated.
- Use Case: Streamlines patching processes and ensures no critical systems are missed.

*Tools for Implementation*

Patch Management Tools:

- WSUS: Manage and deploy Microsoft updates across the organization.
- ManageEngine Patch Manager Plus: Automate patch deployment for OS and third-party apps.
- Ansible: Automate updates across multiple platforms, including Linux and Windows.

Vulnerability Scanning Tools:

- OpenVAS: Open-source vulnerability scanning to identify missing patches.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1051)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1546.010 - AppInit DLLs](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.010%20-%20AppInit%20DLLs/README.md)
- [T1546.011 - Application Shimming](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.011%20-%20Application%20Shimming/README.md)
- [T1176.001 - Browser Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.001%20-%20Browser%20Extensions/README.md)
- [T1548.002 - Bypass User Account Control](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1542.002 - Component Firmware](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.002%20-%20Component%20Firmware/README.md)
- [T1195.001 - Compromise Software Dependencies and Development Tools](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.001%20-%20Compromise%20Software%20Dependencies%20and%20Development%20Tools/README.md)
- [T1195.002 - Compromise Software Supply Chain](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.002%20-%20Compromise%20Software%20Supply%20Chain/README.md)
- [T1555 - Credentials from Password Stores](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1555.003 - Credentials from Web Browsers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1602 - Data from Configuration Repository](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1189 - Drive-by Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md)
- [T1611 - Escape to Host](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md)
- [T1546 - Event Triggered Execution](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1212 - Exploitation for Credential Access](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1212%20-%20Exploitation%20for%20Credential%20Access/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1211 - Exploitation for Stealth](../../Tactics/07%20TA0005%20-%20Stealth/T1211%20-%20Exploitation%20for%20Stealth/README.md)
- [T1210 - Exploitation of Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1495 - Firmware Corruption](../../Tactics/15%20TA0040%20-%20Impact/T1495%20-%20Firmware%20Corruption/README.md)
- [T1552.006 - Group Policy Preferences](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.006%20-%20Group%20Policy%20Preferences/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1176.002 - IDE Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.002%20-%20IDE%20Extensions/README.md)
- [T1602.002 - Network Device Configuration Dump](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.002%20-%20Network%20Device%20Configuration%20Dump/README.md)
- [T1686.002 - Network Device Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.002%20-%20Network%20Device%20Firewall/README.md)
- [T1137 - Office Application Startup](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/README.md)
- [T1137.003 - Outlook Forms](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.003%20-%20Outlook%20Forms/README.md)
- [T1137.004 - Outlook Home Page](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.004%20-%20Outlook%20Home%20Page/README.md)
- [T1137.005 - Outlook Rules](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.005%20-%20Outlook%20Rules/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1110.001 - Password Guessing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.001%20-%20Password%20Guessing/README.md)
- [T1555.005 - Password Managers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.005%20-%20Password%20Managers/README.md)
- [T1542 - Pre-OS Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/README.md)
- [T1602.001 - SNMP (MIB Dump)](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.001%20-%20SNMP%20%28MIB%20Dump%29/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1176 - Software Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/README.md)
- [T1539 - Steal Web Session Cookie](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md)
- [T1195 - Supply Chain Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md)
- [T1542.001 - System Firmware](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.001%20-%20System%20Firmware/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
