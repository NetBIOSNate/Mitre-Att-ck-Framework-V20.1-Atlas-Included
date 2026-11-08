# S0488 - CrackMapExec

[Enterprise](../../../README.md) / [Tools](README.md)

[CrackMapExec](https://attack.mitre.org/software/S0488), or CME, is a post-exploitation tool developed in Python and designed for penetration testing against networks. [CrackMapExec](https://attack.mitre.org/software/S0488) collects Active Directory information to conduct lateral movement through targeted networks.(Citation: CME Github September 2018)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0488)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1053.002 - At](../../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.002%20-%20At/README.md)
- [T1110 - Brute Force](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1087.002 - Domain Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1069.002 - Domain Groups](../../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.002%20-%20Domain%20Groups/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1680 - Local Storage Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1680%20-%20Local%20Storage%20Discovery/README.md)
- [T1003.004 - LSA Secrets](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.004%20-%20LSA%20Secrets/README.md)
- [T1112 - Modify Registry](../../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1135 - Network Share Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1135%20-%20Network%20Share%20Discovery/README.md)
- [T1003.003 - NTDS](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1550.002 - Pass the Hash](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1110.001 - Password Guessing](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.001%20-%20Password%20Guessing/README.md)
- [T1201 - Password Policy Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1201%20-%20Password%20Policy%20Discovery/README.md)
- [T1110.003 - Password Spraying](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1059.001 - PowerShell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1018 - Remote System Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1003.002 - Security Account Manager](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1047 - Windows Management Instrumentation](../../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Used by

- [G0087 - APT39](../../Groups/G0087%20-%20APT39.md)
- [C0029 - Cutting Edge](../../Campaigns/C0029%20-%20Cutting%20Edge.md)
- [G0035 - Dragonfly](../../Groups/G0035%20-%20Dragonfly.md)
- [G1003 - Ember Bear](../../Groups/G1003%20-%20Ember%20Bear.md)
- [G0046 - FIN7](../../Groups/G0046%20-%20FIN7.md)
- [G0069 - MuddyWater](../../Groups/G0069%20-%20MuddyWater.md)

## Sources

- [CME Github September 2018](https://github.com/byt3bl33d3r/CrackMapExec/wiki/SMB-Command-Reference)
