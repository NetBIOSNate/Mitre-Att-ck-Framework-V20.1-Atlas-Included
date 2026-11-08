# G1040 - Play

[Enterprise](../../README.md) / [Groups](README.md)

[Play](https://attack.mitre.org/groups/G1040) is a ransomware group that has been active since at least 2022 deploying  [Playcrypt](https://attack.mitre.org/software/S1162) ransomware against the business, government, critical infrastructure, healthcare, and media sectors in North America, South America, and Europe. [Play](https://attack.mitre.org/groups/G1040) actors employ a double-extortion model, encrypting systems after exfiltrating data, and are presumed by security researchers to operate as a closed group.(Citation: CISA Play Ransomware Advisory December 2023)(Citation: Trend Micro Ransomware Spotlight Play July 2023)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1040)

## Techniques used

- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1685.005 - Clear Windows Event Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1027.010 - Command Obfuscation](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.010%20-%20Command%20Obfuscation/README.md)
- [T1030 - Data Transfer Size Limits](../../Tactics/14%20TA0010%20-%20Exfiltration/T1030%20-%20Data%20Transfer%20Size%20Limits/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1048 - Exfiltration Over Alternative Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1057 - Process Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1518.001 - Security Software Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/T1518.001%20-%20Security%20Software%20Discovery/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Software used

- [S0552 - AdFind](../Software/Tools/S0552%20-%20AdFind.md)
- [S0521 - BloodHound](../Software/Tools/S0521%20-%20BloodHound.md)
- [S0154 - Cobalt Strike](../Software/Malware/S0154%20-%20Cobalt%20Strike.md)
- [S0363 - Empire](../Software/Tools/S0363%20-%20Empire.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S0359 - Nltest](../Software/Tools/S0359%20-%20Nltest.md)
- [S1162 - Playcrypt](../Software/Malware/S1162%20-%20Playcrypt.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S0645 - Wevtutil](../Software/Tools/S0645%20-%20Wevtutil.md)

## Sources

- [CISA Play Ransomware Advisory December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-352a)
- [Trend Micro Ransomware Spotlight Play July 2023](https://www.trendmicro.com/vinfo/us/security/news/ransomware-spotlight/ransomware-spotlight-play)
