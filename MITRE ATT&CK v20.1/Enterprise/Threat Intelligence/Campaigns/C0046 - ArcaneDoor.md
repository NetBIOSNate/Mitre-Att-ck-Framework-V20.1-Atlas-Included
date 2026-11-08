# C0046 - ArcaneDoor

[Enterprise](../../README.md) / [Campaigns](README.md)

[ArcaneDoor](https://attack.mitre.org/campaigns/C0046) is a campaign targeting networking devices from Cisco and other vendors between July 2023 and April 2024, primarily focused on government and critical infrastructure networks. [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) is associated with the deployment of the custom backdoors [Line Runner](https://attack.mitre.org/software/S1188) and [Line Dancer](https://attack.mitre.org/software/S1186). [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) is attributed to a group referred to as UAT4356 or STORM-1849, and is assessed to be a state-sponsored campaign.(Citation: Cisco ArcaneDoor 2024)(Citation: CCCS ArcaneDoor 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0046)

## Techniques used

- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1020 - Automated Exfiltration](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/README.md)
- [T1037 - Boot or Logon Initialization Scripts](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1587.003 - Digital Certificates](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.003%20-%20Digital%20Certificates/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1040 - Network Sniffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1102.003 - One-Way Communication](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/T1102.003%20-%20One-Way%20Communication/README.md)
- [T1653 - Power Settings](../../Tactics/05%20TA0003%20-%20Persistence/T1653%20-%20Power%20Settings/README.md)
- [T1690 - Prevent Command History Logging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1690%20-%20Prevent%20Command%20History%20Logging/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1014 - Rootkit](../../Tactics/07%20TA0005%20-%20Stealth/T1014%20-%20Rootkit/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1583.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.003%20-%20Virtual%20Private%20Server/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1583.006 - Web Services](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.006%20-%20Web%20Services/README.md)

## Software used

- [S1186 - Line Dancer](../Software/Malware/S1186%20-%20Line%20Dancer.md)
- [S1188 - Line Runner](../Software/Malware/S1188%20-%20Line%20Runner.md)

## Sources

- [CCCS ArcaneDoor 2024](https://www.cyber.gc.ca/en/news-events/cyber-activity-impacting-cisco-asa-vpns)
- [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
