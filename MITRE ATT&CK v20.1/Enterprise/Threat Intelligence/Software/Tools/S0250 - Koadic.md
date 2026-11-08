# S0250 - Koadic

[Enterprise](../../../README.md) / [Tools](README.md)

[Koadic](https://attack.mitre.org/software/S0250) is a Windows post-exploitation framework and penetration testing tool that is publicly available on GitHub. [Koadic](https://attack.mitre.org/software/S0250) has several options for staging payloads and creating implants, and performs most of its operations using Windows Script Host.(Citation: Github Koadic)(Citation: Palo Alto Sofacy 06-2018)(Citation: MalwareBytes LazyScripter Feb 2021)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0250)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1573.002 - Asymmetric Cryptography](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1548.002 - Bypass User Account Control](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1115 - Clipboard Data](../../../Tactics/12%20TA0009%20-%20Collection/T1115%20-%20Clipboard%20Data/README.md)
- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1055.001 - Dynamic-link Library Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.001%20-%20Dynamic-link%20Library%20Injection/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1564.003 - Hidden Window](../../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.003%20-%20Hidden%20Window/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1218.005 - Mshta](../../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.005%20-%20Mshta/README.md)
- [T1046 - Network Service Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1135 - Network Share Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1135%20-%20Network%20Share%20Discovery/README.md)
- [T1003.003 - NTDS](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1059.001 - PowerShell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1218.010 - Regsvr32](../../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.010%20-%20Regsvr32/README.md)
- [T1021.001 - Remote Desktop Protocol](../../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1218.011 - Rundll32](../../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.011%20-%20Rundll32/README.md)
- [T1053.005 - Scheduled Task](../../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1003.002 - Security Account Manager](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1569.002 - Service Execution](../../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1059.005 - Visual Basic](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1059.003 - Windows Command Shell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Used by

- [G0007 - APT28](../../Groups/G0007%20-%20APT28.md)
- [G0140 - LazyScripter](../../Groups/G0140%20-%20LazyScripter.md)
- [G0069 - MuddyWater](../../Groups/G0069%20-%20MuddyWater.md)
- [G0121 - Sidewinder](../../Groups/G0121%20-%20Sidewinder.md)

## Sources

- [MalwareBytes LazyScripter Feb 2021](https://web.archive.org/web/20211003035156/https://www.malwarebytes.com/resources/files/2021/02/lazyscripter.pdf)
- [Palo Alto Sofacy 06-2018](https://researchcenter.paloaltonetworks.com/2018/06/unit42-sofacy-groups-parallel-attacks/)
- [Github Koadic](https://github.com/offsecginger/koadic)
