# C0002 - Night Dragon

[Enterprise](../../README.md) / [Campaigns](README.md)

[Night Dragon](https://attack.mitre.org/campaigns/C0002) was a cyber espionage campaign that targeted oil, energy, and petrochemical companies, along with individuals and executives in Kazakhstan, Taiwan, Greece, and the United States. The unidentified threat actors searched for information related to oil and gas field production systems, financials, and collected data from SCADA systems. Based on the observed techniques, tools, and network activities, security researchers assessed the campaign involved a threat group based in China.(Citation: McAfee Night Dragon)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0002)

## Techniques used

- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1568 - Dynamic Resolution](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1568%20-%20Dynamic%20Resolution/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1008 - Fallback Channels](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1008%20-%20Fallback%20Channels/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1114.001 - Local Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1204.001 - Malicious Link](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.001%20-%20Malicious%20Link/README.md)
- [T1588.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.001%20-%20Malware/README.md)
- [T1112 - Modify Registry](../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1110.002 - Password Cracking](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.002%20-%20Password%20Cracking/README.md)
- [T1219 - Remote Access Tools](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/README.md)
- [T1074.002 - Remote Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.002%20-%20Remote%20Data%20Staging/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1583.004 - Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.004%20-%20Server/README.md)
- [T1584.004 - Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.004%20-%20Server/README.md)
- [T1027.002 - Software Packing](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.002%20-%20Software%20Packing/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1033 - System Owner/User Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1608.001 - Upload Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1608%20-%20Stage%20Capabilities/T1608.001%20-%20Upload%20Malware/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Software used

- [S0073 - ASPXSpy](../Software/Malware/S0073%20-%20ASPXSpy.md)
- [S0110 - at](../Software/Tools/S0110%20-%20at.md)
- [S0008 - gsecdump](../Software/Tools/S0008%20-%20gsecdump.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S0350 - zwShell](../Software/Malware/S0350%20-%20zwShell.md)

## Sources

- [McAfee Night Dragon](https://scadahacker.com/library/Documents/Cyber_Events/McAfee%20-%20Night%20Dragon%20-%20Global%20Energy%20Cyberattacks.pdf)
