# M1042 - Disable or Remove Feature or Program

[Enterprise](../../README.md) / [Mitigations](README.md)

Disable or remove unnecessary and potentially vulnerable software, features, or services to reduce the attack surface and prevent abuse by adversaries. This involves identifying software or features that are no longer needed or that could be exploited and ensuring they are either removed or properly disabled. This mitigation can be implemented through the following measures: 

Remove Legacy Software:

- Use Case: Disable or remove older versions of software that no longer receive updates or security patches (e.g., legacy Java, Adobe Flash).
- Implementation: A company removes Flash Player from all employee systems after it has reached its end-of-life date.

Disable Unused Features:

- Use Case: Turn off unnecessary operating system features like SMBv1, Telnet, or RDP if they are not required.
- Implementation: Disable SMBv1 in a Windows environment to mitigate vulnerabilities like EternalBlue.

Control Applications Installed by Users:

- Use Case: Prevent users from installing unauthorized software via group policies or other management tools.
- Implementation: Block user installations of unauthorized file-sharing applications (e.g., BitTorrent clients) in an enterprise environment.

Remove Unnecessary Services:

- Use Case: Identify and disable unnecessary default services running on endpoints, servers, or network devices.
- Implementation: Disable unused administrative shares (e.g., C$, ADMIN$) on workstations.

Restrict Add-ons and Plugins:

- Use Case: Remove or disable browser plugins and add-ons that are not needed for business purposes.
- Implementation: Disable Java and ActiveX plugins in web browsers to prevent drive-by attacks.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1042)

## Mitigated techniques

- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1098.001 - Additional Cloud Credentials](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.001%20-%20Additional%20Cloud%20Credentials/README.md)
- [T1098.002 - Additional Email Delegate Permissions](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.002%20-%20Additional%20Email%20Delegate%20Permissions/README.md)
- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1557.002 - ARP Cache Poisoning](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.002%20-%20ARP%20Cache%20Poisoning/README.md)
- [T1127.002 - ClickOnce](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.002%20-%20ClickOnce/README.md)
- [T1671 - Cloud Application Integration](../../Tactics/05%20TA0003%20-%20Persistence/T1671%20-%20Cloud%20Application%20Integration/README.md)
- [T1552.005 - Cloud Instance Metadata API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.005%20-%20Cloud%20Instance%20Metadata%20API/README.md)
- [T1218.003 - CMSTP](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.003%20-%20CMSTP/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1092 - Communication Through Removable Media](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1092%20-%20Communication%20Through%20Removable%20Media/README.md)
- [T1609 - Container Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1609%20-%20Container%20Administration%20Command/README.md)
- [T1021.008 - Direct Cloud VM Connections](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.008%20-%20Direct%20Cloud%20VM%20Connections/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1021.003 - Distributed Component Object Model](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.003%20-%20Distributed%20Component%20Object%20Model/README.md)
- [T1689 - Downgrade Attack](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1689%20-%20Downgrade%20Attack/README.md)
- [T1559.002 - Dynamic Data Exchange](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.002%20-%20Dynamic%20Data%20Exchange/README.md)
- [T1218.015 - Electron Applications](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.015%20-%20Electron%20Applications/README.md)
- [T1114.003 - Email Forwarding Rule](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.003%20-%20Email%20Forwarding%20Rule/README.md)
- [T1546.014 - Emond](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.014%20-%20Emond/README.md)
- [T1611 - Escape to Host](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md)
- [T1011.001 - Exfiltration Over Bluetooth](../../Tactics/14%20TA0010%20-%20Exfiltration/T1011%20-%20Exfiltration%20Over%20Other%20Network%20Medium/T1011.001%20-%20Exfiltration%20Over%20Bluetooth/README.md)
- [T1011 - Exfiltration Over Other Network Medium](../../Tactics/14%20TA0010%20-%20Exfiltration/T1011%20-%20Exfiltration%20Over%20Other%20Network%20Medium/README.md)
- [T1052 - Exfiltration Over Physical Medium](../../Tactics/14%20TA0010%20-%20Exfiltration/T1052%20-%20Exfiltration%20Over%20Physical%20Medium/README.md)
- [T1052.001 - Exfiltration over USB](../../Tactics/14%20TA0010%20-%20Exfiltration/T1052%20-%20Exfiltration%20Over%20Physical%20Medium/T1052.001%20-%20Exfiltration%20over%20USB/README.md)
- [T1210 - Exploitation of Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1218.004 - InstallUtil](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.004%20-%20InstallUtil/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1127.003 - JamPlus](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.003%20-%20JamPlus/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1553.005 - Mark-of-the-Web Bypass](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.005%20-%20Mark-of-the-Web%20Bypass/README.md)
- [T1218.013 - Mavinject](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.013%20-%20Mavinject/README.md)
- [T1218.014 - MMC](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.014%20-%20MMC/README.md)
- [T1127.001 - MSBuild](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.001%20-%20MSBuild/README.md)
- [T1218.005 - Mshta](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.005%20-%20Mshta/README.md)
- [T1218.007 - Msiexec](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.007%20-%20Msiexec/README.md)
- [T1557.001 - Name Resolution Poisoning and SMB Relay](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.001%20-%20Name%20Resolution%20Poisoning%20and%20SMB%20Relay/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1218.008 - Odbcconf](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.008%20-%20Odbcconf/README.md)
- [T1137 - Office Application Startup](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/README.md)
- [T1137.001 - Office Template Macros](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.001%20-%20Office%20Template%20Macros/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1547.007 - Re-opened Applications](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.007%20-%20Re-opened%20Applications/README.md)
- [T1218.009 - Regsvcs/Regasm](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.009%20-%20Regsvcs%20-%20Regasm/README.md)
- [T1219 - Remote Access Tools](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1219.002 - Remote Desktop Software](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.002%20-%20Remote%20Desktop%20Software/README.md)
- [T1563 - Remote Service Session Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/README.md)
- [T1021 - Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1091 - Replication Through Removable Media](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1091%20-%20Replication%20Through%20Removable%20Media/README.md)
- [T1564.006 - Run Virtual Instance](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.006%20-%20Run%20Virtual%20Instance/README.md)
- [T1546.002 - Screensaver](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.002%20-%20Screensaver/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1021.004 - SSH](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.004%20-%20SSH/README.md)
- [T1098.004 - SSH Authorized Keys](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.004%20-%20SSH%20Authorized%20Keys/README.md)
- [T1563.001 - SSH Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.001%20-%20SSH%20Hijacking/README.md)
- [T1697 - Steal Application Specific Passwords](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1697%20-%20Steal%20Application%20Specific%20Passwords/README.md)
- [T1649 - Steal or Forge Authentication Certificates](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1649%20-%20Steal%20or%20Forge%20Authentication%20Certificates/README.md)
- [T1218 - System Binary Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1221 - Template Injection](../../Tactics/07%20TA0005%20-%20Stealth/T1221%20-%20Template%20Injection/README.md)
- [T1205 - Traffic Signaling](../../Tactics/05%20TA0003%20-%20Persistence/T1205%20-%20Traffic%20Signaling/README.md)
- [T1127 - Trusted Developer Utilities Proxy Execution](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/README.md)
- [T1564.007 - VBA Stomping](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.007%20-%20VBA%20Stomping/README.md)
- [T1218.012 - Verclsid](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.012%20-%20Verclsid/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1021.005 - VNC](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.005%20-%20VNC/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1555.004 - Windows Credential Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.004%20-%20Windows%20Credential%20Manager/README.md)
- [T1021.006 - Windows Remote Management](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.006%20-%20Windows%20Remote%20Management/README.md)
- [T1595.003 - Wordlist Scanning](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.003%20-%20Wordlist%20Scanning/README.md)
