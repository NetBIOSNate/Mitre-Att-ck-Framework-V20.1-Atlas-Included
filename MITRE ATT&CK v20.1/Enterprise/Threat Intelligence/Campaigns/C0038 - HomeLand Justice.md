# C0038 - HomeLand Justice

[Enterprise](../../README.md) / [Campaigns](README.md)

[HomeLand Justice](https://attack.mitre.org/campaigns/C0038) was a disruptive cyber campaign conducted by Iranian state-affiliated actors against Albanian government networks in July and September 2022. The activity combined ransomware, wiper malware, and data leak operations. Initial access for [HomeLand Justice](https://attack.mitre.org/campaigns/C0038) was established as early as May 2021, and threat actors moved laterally, exfiltrated sensitive information, and maintained persistence for approximately 14 months prior to the destructive phase of the operation. Responsibility was claimed by the "HomeLand Justice" front, which framed the campaign as retaliation against the Mujahedeen-e Khalq (MEK), an Iranian opposition group with a presence in Albania. Multiple Iran-nexus groups are assessed to have participated in the campaign, including [HEXANE](https://attack.mitre.org/groups/G1001) who probed victim infrastructure.(Citation: Mandiant ROADSWEEP August 2022)(Citation: Microsoft Albanian Government Attacks September 2022)(Citation: CISA Iran Albanian Attacks September 2022) A second wave of attacks was launched in September 2022 using similar tactics following public attribution of the previous activity to Iran and the severing of diplomatic ties between Iran and Albania.(Citation: CISA Iran Albanian Attacks September 2022)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0038)

## Attributed groups

- [G1055 - VOID MANTICORE](../Groups/G1055%20-%20VOID%20MANTICORE.md)

## Techniques used

- [T1098.002 - Additional Email Delegate Permissions](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.002%20-%20Additional%20Email%20Delegate%20Permissions/README.md)
- [T1588.003 - Code Signing Certificates](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.003%20-%20Code%20Signing%20Certificates/README.md)
- [T1486 - Data Encrypted for Impact](../../Tactics/15%20TA0040%20-%20Impact/T1486%20-%20Data%20Encrypted%20for%20Impact/README.md)
- [T1078.001 - Default Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.001%20-%20Default%20Accounts/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1685.001 - Disable or Modify Windows Event Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.001%20-%20Disable%20or%20Modify%20Windows%20Event%20Log/README.md)
- [T1561.002 - Disk Structure Wipe](../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.002%20-%20Disk%20Structure%20Wipe/README.md)
- [T1087.003 - Email Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.003%20-%20Email%20Account/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1114.002 - Remote Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.002%20-%20Remote%20Email%20Collection/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1134.001 - Token Impersonation/Theft](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/T1134.001%20-%20Token%20Impersonation%20-%20Theft/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Software used

- [S1149 - CHIMNEYSWEEP](../Software/Malware/S1149%20-%20CHIMNEYSWEEP.md)
- [S0095 - ftp](../Software/Tools/S0095%20-%20ftp.md)
- [S0357 - Impacket](../Software/Tools/S0357%20-%20Impacket.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S0364 - RawDisk](../Software/Tools/S0364%20-%20RawDisk.md)
- [S1150 - ROADSWEEP](../Software/Malware/S1150%20-%20ROADSWEEP.md)
- [S1151 - ZeroCleare](../Software/Malware/S1151%20-%20ZeroCleare.md)

## Sources

- [CISA Iran Albanian Attacks September 2022](https://www.cisa.gov/news-events/cybersecurity-advisories/aa22-264a)
- [Mandiant ROADSWEEP August 2022](https://cloud.google.com/blog/topics/threat-intelligence/likely-iranian-threat-actor-conducts-politically-motivated-disruptive-activity-against/)
- [Microsoft Albanian Government Attacks September 2022](https://www.microsoft.com/en-us/security/blog/2022/09/08/microsoft-investigates-iranian-attacks-against-the-albanian-government/)
