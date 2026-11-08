# G0019 - Naikon

[Enterprise](../../README.md) / [Groups](README.md)

[Naikon](https://attack.mitre.org/groups/G0019) is assessed to be a state-sponsored cyber espionage group attributed to the Chinese People’s Liberation Army’s (PLA) Chengdu Military Region Second Technical Reconnaissance Bureau (Military Unit Cover Designator 78020).(Citation: CameraShy) Active since at least 2010, [Naikon](https://attack.mitre.org/groups/G0019) has primarily conducted operations against government, military, and civil organizations in Southeast Asia, as well as against international bodies such as the United Nations Development Programme (UNDP) and the Association of Southeast Asian Nations (ASEAN).(Citation: CameraShy)(Citation: Baumgartner Naikon 2015) 

While [Naikon](https://attack.mitre.org/groups/G0019) shares some characteristics with [APT30](https://attack.mitre.org/groups/G0013), the two groups do not appear to be exact matches.(Citation: Baumgartner Golovkin Naikon 2015)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0019)

## Software used

- [S0456 - Aria-body](../Software/Malware/S0456%20-%20Aria-body.md)
- [S0095 - ftp](../Software/Tools/S0095%20-%20ftp.md)
- [S0061 - HDoor](../Software/Malware/S0061%20-%20HDoor.md)
- [S0630 - Nebulae](../Software/Malware/S0630%20-%20Nebulae.md)
- [S0039 - Net](../Software/Tools/S0039%20-%20Net.md)
- [S0108 - netsh](../Software/Tools/S0108%20-%20netsh.md)
- [S0097 - Ping](../Software/Tools/S0097%20-%20Ping.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S0629 - RainyDay](../Software/Malware/S0629%20-%20RainyDay.md)
- [S0055 - RARSTONE](../Software/Malware/S0055%20-%20RARSTONE.md)
- [S0058 - SslMM](../Software/Malware/S0058%20-%20SslMM.md)
- [S0060 - Sys10](../Software/Malware/S0060%20-%20Sys10.md)
- [S0096 - Systeminfo](../Software/Tools/S0096%20-%20Systeminfo.md)
- [S0057 - Tasklist](../Software/Tools/S0057%20-%20Tasklist.md)
- [S0059 - WinMM](../Software/Malware/S0059%20-%20WinMM.md)

## Techniques used

- [T1137.006 - Add-ins](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.006%20-%20Add-ins/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1036.004 - Masquerade Task or Service](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.004%20-%20Masquerade%20Task%20or%20Service/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1518.001 - Security Software Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/T1518.001%20-%20Security%20Software%20Discovery/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Sources

- [CameraShy](http://cdn2.hubspot.net/hubfs/454298/Project_CAMERASHY_ThreatConnect_Copyright_2015.pdf)
- [Baumgartner Naikon 2015](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/07205555/TheNaikonAPT-MsnMM1.pdf)
- [Baumgartner Golovkin Naikon 2015](https://securelist.com/the-naikon-apt/69953/)
