# M1033 - Limit Software Installation

[Enterprise](../../README.md) / [Mitigations](README.md)

Prevent users or groups from installing unauthorized or unapproved software to reduce the risk of introducing malicious or vulnerable applications. This can be achieved through allowlists, software restriction policies, endpoint management tools, and least privilege access principles. This mitigation can be implemented through the following measures:

Application Whitelisting

- Implement Microsoft AppLocker or Windows Defender Application Control (WDAC) to create and enforce allowlists for approved software.
- Whitelist applications based on file hash, path, or digital signatures.

Restrict User Permissions

- Remove local administrator rights for all non-IT users.
- Use Role-Based Access Control (RBAC) to restrict installation permissions to privileged accounts only.

Software Restriction Policies (SRP)

- Use GPO to configure SRP to deny execution of binaries from directories such as `%AppData%`, `%Temp%`, and external drives.
- Restrict specific file types (`.exe`, `.bat`, `.msi`, `.js`, `.vbs`) to trusted directories only.

Endpoint Management Solutions

- Deploy tools like Microsoft Intune, SCCM, or Jamf for centralized software management.
- Maintain a list of approved software, versions, and updates across the enterprise.

Monitor Software Installation Events

- Enable logging of software installation events and monitor Windows Event ID 4688 and Event ID 11707 for software installs.
- Use SIEM or EDR tools to alert on attempts to install unapproved software.

Implement Software Inventory Management

- Use tools like OSQuery or Wazuh to scan for unauthorized software on endpoints and servers.
- Conduct regular audits to detect and remove unapproved software.

*Tools for Implementation*

Application Whitelisting:

- Microsoft AppLocker
- Windows Defender Application Control (WDAC)

Endpoint Management:

- Microsoft Intune
- SCCM (System Center Configuration Manager)
- Jamf Pro (macOS)
- Puppet or Ansible for automation

Software Restriction Policies:

- Group Policy Object (GPO)
- Microsoft Software Restriction Policies (SRP)

Monitoring and Logging:

- Splunk
- OSQuery
- Wazuh (open-source SIEM and XDR)
- EDRs

Inventory Management and Auditing:

- OSQuery
- Wazuh

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1033)

## Mitigated techniques

- [T1176.001 - Browser Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.001%20-%20Browser%20Extensions/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1195.001 - Compromise Software Dependencies and Development Tools](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.001%20-%20Compromise%20Software%20Dependencies%20and%20Development%20Tools/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1564.003 - Hidden Window](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.003%20-%20Hidden%20Window/README.md)
- [T1564 - Hide Artifacts](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/README.md)
- [T1176.002 - IDE Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.002%20-%20IDE%20Extensions/README.md)
- [T1059.011 - Lua](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.011%20-%20Lua/README.md)
- [T1204.005 - Malicious Library](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.005%20-%20Malicious%20Library/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1176 - Software Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/README.md)
- [T1195 - Supply Chain Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1204 - User Execution](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md)
- [T1021.005 - VNC](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.005%20-%20VNC/README.md)
- [T1547.013 - XDG Autostart Entries](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.013%20-%20XDG%20Autostart%20Entries/README.md)
