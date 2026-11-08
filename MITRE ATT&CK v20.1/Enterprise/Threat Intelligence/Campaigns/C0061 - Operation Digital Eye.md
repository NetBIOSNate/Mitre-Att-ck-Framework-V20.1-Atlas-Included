# C0061 - Operation Digital Eye

[Enterprise](../../README.md) / [Campaigns](README.md)

[Operation Digital Eye](https://attack.mitre.org/campaigns/C0061) was conducted in June and July of 2024 by suspected People's Republic of China (PRC)-nexus threat actors targeting business-to-business IT service providers in Southern Europe. [Operation Digital Eye](https://attack.mitre.org/campaigns/C0061) activity included the use of Visual Studio Code tunnels for command and control (C2) and custom lateral movement capabilities. Overlaps in tooling between Digital Eye and previous China-nexus campaigns, Operation Soft Cell and Operation Tainted Love, indicate the potential use of shared vendors or digital quartermasters.(Citation: sentinelone operationDigitalEye Dec 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0061)

## Software used

- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S9028 - PHPsert](../Software/Malware/S9028%20-%20PHPsert.md)
- [S0097 - Ping](../Software/Tools/S0097%20-%20Ping.md)
- [S0225 - sqlmap](../Software/Tools/S0225%20-%20sqlmap.md)

## Techniques used

- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1591 - Gather Victim Org Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1591%20-%20Gather%20Victim%20Org%20Information/README.md)
- [T1665 - Hide Infrastructure](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1665%20-%20Hide%20Infrastructure/README.md)
- [T1219.001 - IDE Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.001%20-%20IDE%20Tunneling/README.md)
- [T1087.001 - Local Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.001%20-%20Local%20Account/README.md)
- [T1069.001 - Local Groups](../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.001%20-%20Local%20Groups/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1106 - Native API](../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1003.002 - Security Account Manager](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.002%20-%20Security%20Account%20Manager/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1098.004 - SSH Authorized Keys](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.004%20-%20SSH%20Authorized%20Keys/README.md)
- [T1614.001 - System Language Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1614%20-%20System%20Location%20Discovery/T1614.001%20-%20System%20Language%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)

## Sources

- [sentinelone operationDigitalEye Dec 2024](https://www.sentinelone.com/labs/operation-digital-eye-chinese-apt-compromises-critical-digital-infrastructure-via-visual-studio-code-tunnels/)
