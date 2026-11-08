# C0025 - 2016 Ukraine Electric Power Attack

[Enterprise](../../README.md) / [Campaigns](README.md)

[2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025) was a [Sandworm Team](https://attack.mitre.org/groups/G0034) campaign during which they used [Industroyer](https://attack.mitre.org/software/S0604) malware to target and disrupt distribution substations within the Ukrainian power grid. This campaign was the second major public attack conducted against Ukraine by [Sandworm Team](https://attack.mitre.org/groups/G0034).(Citation: ESET Industroyer)(Citation: Dragos Crashoverride 2018)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0025)

## Techniques used

- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1110 - Brute Force](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1554 - Compromise Host Software Binary](../../Tactics/05%20TA0003%20-%20Persistence/T1554%20-%20Compromise%20Host%20Software%20Binary/README.md)
- [T1136 - Create Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md)
- [T1685.001 - Disable or Modify Windows Event Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.001%20-%20Disable%20or%20Modify%20Windows%20Event%20Log/README.md)
- [T1136.002 - Domain Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1036.010 - Masquerade Account Name](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.010%20-%20Masquerade%20Account%20Name/README.md)
- [T1036.008 - Masquerade File Type](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.008%20-%20Masquerade%20File%20Type/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1027 - Obfuscated Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1027.002 - Software Packing](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.002%20-%20Software%20Packing/README.md)
- [T1505.001 - SQL Stored Procedures](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.001%20-%20SQL%20Stored%20Procedures/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)

## Software used

- [S0604 - Industroyer](../Software/Malware/S0604%20-%20Industroyer.md)

## Attributed groups

- [G0034 - Sandworm Team](../Groups/G0034%20-%20Sandworm%20Team.md)

## Sources

- [ESET Industroyer](https://www.welivesecurity.com/wp-content/uploads/2017/06/Win32_Industroyer.pdf)
- [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
