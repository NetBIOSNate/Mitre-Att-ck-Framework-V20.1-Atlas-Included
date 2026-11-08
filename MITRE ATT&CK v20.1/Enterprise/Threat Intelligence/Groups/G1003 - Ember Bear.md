# G1003 - Ember Bear

[Enterprise](../../README.md) / [Groups](README.md)

[Ember Bear](https://attack.mitre.org/groups/G1003) is a Russian state-sponsored cyber espionage group that has been active since at least 2020, linked to Russia's General Staff Main Intelligence Directorate (GRU) 161st Specialist Training Center (Unit 29155).(Citation: CISA GRU29155 2024) [Ember Bear](https://attack.mitre.org/groups/G1003) has primarily focused operations against Ukrainian government and telecommunication entities, but has also operated against critical infrastructure entities in Europe and the Americas.(Citation: Cadet Blizzard emerges as novel threat actor) [Ember Bear](https://attack.mitre.org/groups/G1003) conducted the [WhisperGate](https://attack.mitre.org/software/S0689) destructive wiper attacks against Ukraine in early 2022.(Citation: CrowdStrike Ember Bear Profile March 2022)(Citation: Mandiant UNC2589 March 2022)(Citation: CISA GRU29155 2024) There is some confusion as to whether [Ember Bear](https://attack.mitre.org/groups/G1003) overlaps with another Russian-linked entity referred to as [Saint Bear](https://attack.mitre.org/groups/G1031). At present available evidence strongly suggests these are distinct activities with different behavioral profiles.(Citation: Cadet Blizzard emerges as novel threat actor)(Citation: Palo Alto Unit 42 OutSteel SaintBot February 2022 )

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1003)

## Aliases

- UNC2589
- Bleeding Bear
- DEV-0586
- Cadet Blizzard
- Frozenvista
- UAC-0056

## Techniques used

- [T1583 - Acquire Infrastructure](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/README.md)
- [T1560 - Archive Collected Data](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/README.md)
- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1110 - Brute Force](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1552.001 - Credentials In Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1078.001 - Default Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.001%20-%20Default%20Accounts/README.md)
- [T1561.002 - Disk Structure Wipe](../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.002%20-%20Disk%20Structure%20Wipe/README.md)
- [T1071.004 - DNS](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.004%20-%20DNS/README.md)
- [T1114 - Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/README.md)
- [T1585 - Establish Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1210 - Exploitation of Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1588.005 - Exploits](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.005%20-%20Exploits/README.md)
- [T1491.002 - External Defacement](../../Tactics/15%20TA0040%20-%20Impact/T1491%20-%20Defacement/T1491.002%20-%20External%20Defacement/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1654 - Log Enumeration](../../Tactics/10%20TA0007%20-%20Discovery/T1654%20-%20Log%20Enumeration/README.md)
- [T1003.004 - LSA Secrets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.004%20-%20LSA%20Secrets/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1588.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.001%20-%20Malware/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1112 - Modify Registry](../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1571 - Non-Standard Port](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1003 - OS Credential Dumping](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1110.003 - Password Spraying](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1572 - Protocol Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1021 - Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1595.001 - Scanning IP Blocks](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.001%20-%20Scanning%20IP%20Blocks/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1195 - Supply Chain Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md)
- [T1125 - Video Capture](../../Tactics/12%20TA0009%20-%20Collection/T1125%20-%20Video%20Capture/README.md)
- [T1583.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.003%20-%20Virtual%20Private%20Server/README.md)
- [T1595.002 - Vulnerability Scanning](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.002%20-%20Vulnerability%20Scanning/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Software used

- [S0521 - BloodHound](../Software/Tools/S0521%20-%20BloodHound.md)
- [S0488 - CrackMapExec](../Software/Tools/S0488%20-%20CrackMapExec.md)
- [S0357 - Impacket](../Software/Tools/S0357%20-%20Impacket.md)
- [S0508 - ngrok](../Software/Tools/S0508%20-%20ngrok.md)
- [S0598 - P.A.S. Webshell](../Software/Malware/S0598%20-%20P.A.S.%20Webshell.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S1040 - Rclone](../Software/Tools/S1040%20-%20Rclone.md)
- [S1187 - reGeorg](../Software/Malware/S1187%20-%20reGeorg.md)
- [S0174 - Responder](../Software/Tools/S0174%20-%20Responder.md)
- [S1018 - Saint Bot](../Software/Malware/S1018%20-%20Saint%20Bot.md)
- [S0689 - WhisperGate](../Software/Malware/S0689%20-%20WhisperGate.md)

## Sources

- [CrowdStrike Ember Bear Profile March 2022](https://www.crowdstrike.com/blog/who-is-ember-bear/)
- [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/)
- [Mandiant UNC2589 March 2022](https://www.mandiant.com/resources/russia-invasion-ukraine-retaliation)
- [Palo Alto Unit 42 OutSteel SaintBot February 2022 ](https://unit42.paloaltonetworks.com/ukraine-targeted-outsteel-saintbot/)
- [CISA GRU29155 2024](https://www.cisa.gov/sites/default/files/2024-09/aa24-249a-russian-military-cyber-actors-target-us-and-global-critical-infrastructure.pdf)
