# G0108 - Blue Mockingbird

[Enterprise](../../README.md) / [Groups](README.md)

[Blue Mockingbird](https://attack.mitre.org/groups/G0108) is a cluster of observed activity involving Monero cryptocurrency-mining payloads in dynamic-link library (DLL) form on Windows systems. The earliest observed Blue Mockingbird tools were created in December 2019.(Citation: RedCanary Mockingbird May 2020)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0108)

## Techniques used

- [T1134 - Access Token Manipulation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/README.md)
- [T1496.001 - Compute Hijacking](../../Tactics/15%20TA0040%20-%20Impact/T1496%20-%20Resource%20Hijacking/T1496.001%20-%20Compute%20Hijacking/README.md)
- [T1574.012 - COR_PROFILER](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.012%20-%20COR_PROFILER/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1112 - Modify Registry](../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1218.010 - Regsvr32](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.010%20-%20Regsvr32/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1218.011 - Rundll32](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.011%20-%20Rundll32/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)

## Software used

- [S1144 - FRP](../Software/Tools/S1144%20-%20FRP.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)

## Sources

- [RedCanary Mockingbird May 2020](https://redcanary.com/blog/blue-mockingbird-cryptominer/)
