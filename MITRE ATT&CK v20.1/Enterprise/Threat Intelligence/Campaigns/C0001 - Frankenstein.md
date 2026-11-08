# C0001 - Frankenstein

[Enterprise](../../README.md) / [Campaigns](README.md)

[Frankenstein](https://attack.mitre.org/campaigns/C0001) was described by security researchers as a highly-targeted campaign conducted by moderately sophisticated and highly resourceful threat actors in early 2019. The unidentified actors primarily relied on open source tools, including [Empire](https://attack.mitre.org/software/S0363). The campaign name refers to the actors' ability to piece together several unrelated open-source tool components.(Citation: Talos Frankenstein June 2019)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0001)

## Techniques used

- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1020 - Automated Exfiltration](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/README.md)
- [T1027.010 - Command Obfuscation](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.010%20-%20Command%20Obfuscation/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1036.004 - Masquerade Task or Service](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.004%20-%20Masquerade%20Task%20or%20Service/README.md)
- [T1127.001 - MSBuild](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.001%20-%20MSBuild/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1057 - Process Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1518.001 - Security Software Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/T1518.001%20-%20Security%20Software%20Discovery/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1573.001 - Symmetric Cryptography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.001%20-%20Symmetric%20Cryptography/README.md)
- [T1497.001 - System Checks](../../Tactics/07%20TA0005%20-%20Stealth/T1497%20-%20Virtualization%20-%20Sandbox%20Evasion/T1497.001%20-%20System%20Checks/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1221 - Template Injection](../../Tactics/07%20TA0005%20-%20Stealth/T1221%20-%20Template%20Injection/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Software used

- [S0363 - Empire](../Software/Tools/S0363%20-%20Empire.md)

## Sources

- [Talos Frankenstein June 2019](https://blog.talosintelligence.com/2019/06/frankenstein-campaign.html)
