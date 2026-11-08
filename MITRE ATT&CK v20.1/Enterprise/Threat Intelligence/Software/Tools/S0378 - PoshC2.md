# S0378 - PoshC2

[Enterprise](../../../README.md) / [Tools](README.md)

[PoshC2](https://attack.mitre.org/software/S0378) is an open source remote administration and post-exploitation framework that is publicly available on GitHub. The server-side components of the tool are primarily written in Python, while the implants are written in [PowerShell](https://attack.mitre.org/techniques/T1059/001). Although [PoshC2](https://attack.mitre.org/software/S0378) is primarily focused on Windows implantation, it does contain a basic Python dropper for Linux/macOS.(Citation: GitHub PoshC2)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0378)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md)

## Techniques used

- [T1134 - Access Token Manipulation](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/README.md)
- [T1560.001 - Archive via Utility](../../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1119 - Automated Collection](../../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1110 - Brute Force](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1548.002 - Bypass User Account Control](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1134.002 - Create Process with Token](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.002%20-%20Create%20Process%20with%20Token/README.md)
- [T1555 - Credentials from Password Stores](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1552.001 - Credentials In Files](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1087.002 - Domain Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1482 - Domain Trust Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1210 - Exploitation of Remote Services](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1056.001 - Keylogging](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1087.001 - Local Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.001%20-%20Local%20Account/README.md)
- [T1069.001 - Local Groups](../../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.001%20-%20Local%20Groups/README.md)
- [T1003.001 - LSASS Memory](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1557.001 - Name Resolution Poisoning and SMB Relay](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.001%20-%20Name%20Resolution%20Poisoning%20and%20SMB%20Relay/README.md)
- [T1046 - Network Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1040 - Network Sniffing](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1550.002 - Pass the Hash](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1201 - Password Policy Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1201%20-%20Password%20Policy%20Discovery/README.md)
- [T1055 - Process Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1090 - Proxy](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1569.002 - Service Execution](../../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1007 - System Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1007%20-%20System%20Service%20Discovery/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1047 - Windows Management Instrumentation](../../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](../../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)

## Used by

- [G0064 - APT33](../../Groups/G0064%20-%20APT33.md)
- [G1001 - HEXANE](../../Groups/G1001%20-%20HEXANE.md)
- [G0034 - Sandworm Team](../../Groups/G0034%20-%20Sandworm%20Team.md)

## Sources

- [GitHub PoshC2](https://github.com/nettitude/PoshC2_Python)
