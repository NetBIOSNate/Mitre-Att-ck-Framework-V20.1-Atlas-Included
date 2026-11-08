# S0192 - Pupy

[Enterprise](../../../README.md) / [Tools](README.md)

[Pupy](https://attack.mitre.org/software/S0192) is an open source, cross-platform (Windows, Linux, OSX, Android) remote administration and post-exploitation tool. (Citation: GitHub Pupy) It is written in Python and can be generated as a payload in several different ways (Windows exe, Python file, PowerShell oneliner/file, Linux elf, APK, Rubber Ducky, etc.). (Citation: GitHub Pupy) [Pupy](https://attack.mitre.org/software/S0192) is publicly available on GitHub. (Citation: GitHub Pupy)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0192)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), Android

## Techniques used

- [T1560.001 - Archive via Utility](../../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1573.002 - Asymmetric Cryptography](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1123 - Audio Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1123%20-%20Audio%20Capture/README.md)
- [T1548.002 - Bypass User Account Control](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1003.005 - Cached Domain Credentials](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.005%20-%20Cached%20Domain%20Credentials/README.md)
- [T1685.005 - Clear Windows Event Logs](../../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1555 - Credentials from Password Stores](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1555.003 - Credentials from Web Browsers](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1552.001 - Credentials In Files](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1136.002 - Domain Account](../../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1055.001 - Dynamic-link Library Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.001%20-%20Dynamic-link%20Library%20Injection/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1056.001 - Keylogging](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1087.001 - Local Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.001%20-%20Local%20Account/README.md)
- [T1136.001 - Local Account](../../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.001%20-%20Local%20Account/README.md)
- [T1114.001 - Local Email Collection](../../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1003.004 - LSA Secrets](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.004%20-%20LSA%20Secrets/README.md)
- [T1003.001 - LSASS Memory](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1557.001 - Name Resolution Poisoning and SMB Relay](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.001%20-%20Name%20Resolution%20Poisoning%20and%20SMB%20Relay/README.md)
- [T1046 - Network Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1135 - Network Share Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1135%20-%20Network%20Share%20Discovery/README.md)
- [T1550.003 - Pass the Ticket](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.003%20-%20Pass%20the%20Ticket/README.md)
- [T1059.001 - PowerShell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1059.006 - Python](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1021.001 - Remote Desktop Protocol](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1113 - Screen Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1569.002 - Service Execution](../../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1497.001 - System Checks](../../../Tactics/07%20TA0005%20-%20Stealth/T1497%20-%20Virtualization%20-%20Sandbox%20Evasion/T1497.001%20-%20System%20Checks/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1543.002 - Systemd Service](../../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1134.001 - Token Impersonation/Theft](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.001%20-%20Token%20Impersonation%20-%20Theft/README.md)
- [T1125 - Video Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1125%20-%20Video%20Capture/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1547.013 - XDG Autostart Entries](../../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.013%20-%20XDG%20Autostart%20Entries/README.md)

## Used by

- [G0064 - APT33](../../Groups/G0064%20-%20APT33.md)
- [G0059 - Magic Hound](../../Groups/G0059%20-%20Magic%20Hound.md)

## Sources

- [GitHub Pupy](https://github.com/n1nj4sec/pupy)
