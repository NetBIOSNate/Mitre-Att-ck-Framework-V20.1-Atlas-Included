# G0093 - GALLIUM

[Enterprise](../../README.md) / [Groups](README.md)

[GALLIUM](https://attack.mitre.org/groups/G0093) is a cyberespionage group that has been active since at least 2012, primarily targeting telecommunications companies, financial institutions, and government entities in Afghanistan, Australia, Belgium, Cambodia, Malaysia, Mozambique, the Philippines, Russia, and Vietnam. This group is particularly known for launching Operation Soft Cell, a long-term campaign targeting telecommunications providers.(Citation: Cybereason Soft Cell June 2019) Security researchers have identified [GALLIUM](https://attack.mitre.org/groups/G0093) as a likely Chinese state-sponsored group, based in part on tools used and TTPs commonly associated with Chinese threat actors.(Citation: Cybereason Soft Cell June 2019)(Citation: Microsoft GALLIUM December 2019)(Citation: Unit 42 PingPull Jun 2022)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0093)

## Aliases

- Granite Typhoon

## Software used

- [S0110 - at](../Software/Tools/S0110%20-%20at.md)
- [S0564 - BlackMould](../Software/Malware/S0564%20-%20BlackMould.md)
- [S0020 - China Chopper](../Software/Malware/S0020%20-%20China%20Chopper.md)
- [S0106 - cmd](../Software/Tools/S0106%20-%20cmd.md)
- [S0040 - HTRAN](../Software/Tools/S0040%20-%20HTRAN.md)
- [S0100 - ipconfig](../Software/Tools/S0100%20-%20ipconfig.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S0590 - NBTscan](../Software/Tools/S0590%20-%20NBTscan.md)
- [S0039 - Net](../Software/Tools/S0039%20-%20Net.md)
- [S0097 - Ping](../Software/Tools/S0097%20-%20Ping.md)
- [S1031 - PingPull](../Software/Malware/S1031%20-%20PingPull.md)
- [S0013 - PlugX](../Software/Malware/S0013%20-%20PlugX.md)
- [S0012 - PoisonIvy](../Software/Malware/S0012%20-%20PoisonIvy.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S0075 - Reg](../Software/Tools/S0075%20-%20Reg.md)
- [S0005 - Windows Credential Editor](../Software/Tools/S0005%20-%20Windows%20Credential%20Editor.md)

## Techniques used

- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1136.002 - Domain Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1090.002 - External Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.002%20-%20External%20Proxy/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1027.005 - Indicator Removal from Tools](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.005%20-%20Indicator%20Removal%20from%20Tools/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1027 - Obfuscated Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1036.003 - Rename Legitimate Utilities](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.003%20-%20Rename%20Legitimate%20Utilities/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1583.004 - Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.004%20-%20Server/README.md)
- [T1027.002 - Software Packing](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.002%20-%20Software%20Packing/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Sources

- [Cybereason Soft Cell June 2019](https://www.cybereason.com/blog/operation-soft-cell-a-worldwide-campaign-against-telecommunications-providers)
- [Microsoft Threat Actor Naming July 2023](https://learn.microsoft.com/en-us/microsoft-365/security/intelligence/microsoft-threat-actor-naming?view=o365-worldwide)
- [Microsoft GALLIUM December 2019](https://www.microsoft.com/security/blog/2019/12/12/gallium-targeting-global-telecom/)
- [Unit 42 PingPull Jun 2022](https://unit42.paloaltonetworks.com/pingpull-gallium/)
