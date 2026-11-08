# G1017 - Volt Typhoon

[Enterprise](../../README.md) / [Groups](README.md)

[Volt Typhoon](https://attack.mitre.org/groups/G1017) is a People's Republic of China (PRC) state-sponsored actor that has been active since at least 2021, primarily targeting critical infrastructure organizations in the US and its territories including Guam. [Volt Typhoon](https://attack.mitre.org/groups/G1017)'s targeting and pattern of behavior have been assessed as pre-positioning to enable lateral movement to operational technology (OT) assets for potential destructive or disruptive attacks. [Volt Typhoon](https://attack.mitre.org/groups/G1017) has emphasized stealth in operations using web shells, living-off-the-land (LOTL) binaries, hands on keyboard activities, and stolen credentials.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024)(Citation: Microsoft Volt Typhoon May 2023)(Citation: Joint Cybersecurity Advisory Volt Typhoon June 2023)(Citation: Secureworks BRONZE SILHOUETTE May 2023). The group has leveraged compromised SOHO routers to proxy command and control traffic and obscure its infrastructure, activity associated with the KV botnet.(Citation: DOJ KVBotnet 2024). 

Reporting indicates a separate initial access cluster, SYLVANITE, has been observed exploiting internet-facing edge devices and transferring access to [Volt Typhoon](https://attack.mitre.org/groups/G1017), also tracked as VOLTZITE, for follow-on operations. (Citation: Dragos 2025 Year in Review)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1017)

## Aliases

- BRONZE SILHOUETTE
- Vanguard Panda
- DEV-0391
- UNC3236
- Voltzite
- Insidious Taurus
- DazedToad

## Techniques used

- [T1010 - Application Window Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1010%20-%20Application%20Window%20Discovery/README.md)
- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1584.005 - Botnet](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.005%20-%20Botnet/README.md)
- [T1217 - Browser Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1217%20-%20Browser%20Information%20Discovery/README.md)
- [T1070.007 - Clear Network Connection History and Configurations](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.007%20-%20Clear%20Network%20Connection%20History%20and%20Configurations/README.md)
- [T1685.005 - Clear Windows Event Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1555 - Credentials from Password Stores](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/README.md)
- [T1555.003 - Credentials from Web Browsers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1074 - Data Staged](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1006 - Direct Volume Access](../../Tactics/07%20TA0005%20-%20Stealth/T1006%20-%20Direct%20Volume%20Access/README.md)
- [T1087.002 - Domain Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1069.002 - Domain Groups](../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.002%20-%20Domain%20Groups/README.md)
- [T1589.002 - Email Addresses](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1589%20-%20Gather%20Victim%20Identity%20Information/T1589.002%20-%20Email%20Addresses/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1587.004 - Exploits](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.004%20-%20Exploits/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1592 - Gather Victim Host Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1592%20-%20Gather%20Victim%20Host%20Information/README.md)
- [T1589 - Gather Victim Identity Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1589%20-%20Gather%20Victim%20Identity%20Information/README.md)
- [T1590 - Gather Victim Network Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1590%20-%20Gather%20Victim%20Network%20Information/README.md)
- [T1591 - Gather Victim Org Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1591%20-%20Gather%20Victim%20Org%20Information/README.md)
- [T1591.004 - Identify Roles](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1591%20-%20Gather%20Victim%20Org%20Information/T1591.004%20-%20Identify%20Roles/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1090.001 - Internal Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.001%20-%20Internal%20Proxy/README.md)
- [T1016.001 - Internet Connection Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/T1016.001%20-%20Internet%20Connection%20Discovery/README.md)
- [T1056.001 - Keylogging](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1087.001 - Local Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.001%20-%20Local%20Account/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1069.001 - Local Groups](../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.001%20-%20Local%20Groups/README.md)
- [T1680 - Local Storage Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1680%20-%20Local%20Storage%20Discovery/README.md)
- [T1654 - Log Enumeration](../../Tactics/10%20TA0007%20-%20Discovery/T1654%20-%20Log%20Enumeration/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1036.008 - Masquerade File Type](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.008%20-%20Masquerade%20File%20Type/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1112 - Modify Registry](../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1584.008 - Network Devices](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.008%20-%20Network%20Devices/README.md)
- [T1590.006 - Network Security Appliances](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1590%20-%20Gather%20Victim%20Network%20Information/T1590.006%20-%20Network%20Security%20Appliances/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1590.004 - Network Topology](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1590%20-%20Gather%20Victim%20Network%20Information/T1590.004%20-%20Network%20Topology/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1120 - Peripheral Device Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1120%20-%20Peripheral%20Device%20Discovery/README.md)
- [T1069 - Permission Groups Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1552.004 - Private Keys](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.004%20-%20Private%20Keys/README.md)
- [T1057 - Process Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1012 - Query Registry](../../Tactics/10%20TA0007%20-%20Discovery/T1012%20-%20Query%20Registry/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1596.005 - Scan Databases](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1596%20-%20Search%20Open%20Technical%20Databases/T1596.005%20-%20Scan%20Databases/README.md)
- [T1113 - Screen Capture](../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1593 - Search Open Websites/Domains](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/README.md)
- [T1594 - Search Victim-Owned Websites](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1594%20-%20Search%20Victim-Owned%20Websites/README.md)
- [T1584.004 - Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.004%20-%20Server/README.md)
- [T1518 - Software Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/README.md)
- [T1027.002 - Software Packing](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.002%20-%20Software%20Packing/README.md)
- [T1573.001 - Symmetric Cryptography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.001%20-%20Symmetric%20Cryptography/README.md)
- [T1218 - System Binary Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1497.001 - System Checks](../../Tactics/07%20TA0005%20-%20Stealth/T1497%20-%20Virtualization%20-%20Sandbox%20Evasion/T1497.001%20-%20System%20Checks/README.md)
- [T1614 - System Location Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1614%20-%20System%20Location%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1007 - System Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1007%20-%20System%20Service%20Discovery/README.md)
- [T1124 - System Time Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1124%20-%20System%20Time%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1584.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.003%20-%20Virtual%20Private%20Server/README.md)
- [T1588.006 - Vulnerabilities](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.006%20-%20Vulnerabilities/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Software used

- [S0160 - certutil](../Software/Tools/S0160%20-%20certutil.md)
- [S0106 - cmd](../Software/Tools/S0106%20-%20cmd.md)
- [S1144 - FRP](../Software/Tools/S1144%20-%20FRP.md)
- [S0357 - Impacket](../Software/Tools/S0357%20-%20Impacket.md)
- [S0100 - ipconfig](../Software/Tools/S0100%20-%20ipconfig.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S0039 - Net](../Software/Tools/S0039%20-%20Net.md)
- [S0108 - netsh](../Software/Tools/S0108%20-%20netsh.md)
- [S0104 - netstat](../Software/Tools/S0104%20-%20netstat.md)
- [S0359 - Nltest](../Software/Tools/S0359%20-%20Nltest.md)
- [S0097 - Ping](../Software/Tools/S0097%20-%20Ping.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S0075 - Reg](../Software/Tools/S0075%20-%20Reg.md)
- [S0096 - Systeminfo](../Software/Tools/S0096%20-%20Systeminfo.md)
- [S0057 - Tasklist](../Software/Tools/S0057%20-%20Tasklist.md)
- [S1154 - VersaMem](../Software/Malware/S1154%20-%20VersaMem.md)
- [S0645 - Wevtutil](../Software/Tools/S0645%20-%20Wevtutil.md)

## Attributed campaigns

- [C0035 - KV Botnet Activity](../Campaigns/C0035%20-%20KV%20Botnet%20Activity.md)
- [C0039 - Versa Director Zero Day Exploitation](../Campaigns/C0039%20-%20Versa%20Director%20Zero%20Day%20Exploitation.md)

## Sources

- [Cloudflare 2026 Threat Report New Threat Actors March 2026](https://blog.cloudflare.com/2026-threat-report/)
- [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)
- [Secureworks BRONZE SILHOUETTE May 2023](https://web.archive.org/web/20230601025540/https://www.secureworks.com/blog/chinese-cyberespionage-group-bronze-silhouette-targets-us-government-and-defense-organizations)
- [Dragos 2025 Year in Review](https://5943619.hs-sites.com/hubfs/312-Year-in-Review/2026/Dragos-2026-OT-Cybersecurity-Report-A-Year-in-Review.pdf?hsCtaAttrib=205683189348)
- [Microsoft Volt Typhoon May 2023](https://www.microsoft.com/en-us/security/blog/2023/05/24/volt-typhoon-targets-us-critical-infrastructure-with-living-off-the-land-techniques/)
- [Joint Cybersecurity Advisory Volt Typhoon June 2023](https://media.defense.gov/2023/May/24/2003229517/-1/-1/0/CSA_Living_off_the_Land.PDF)
- [DOJ KVBotnet 2024](https://www.justice.gov/opa/pr/us-government-disrupts-botnet-peoples-republic-china-used-conceal-hacking-critical)
