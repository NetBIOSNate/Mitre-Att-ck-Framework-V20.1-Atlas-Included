# G1024 - Akira

[Enterprise](../../README.md) / [Groups](README.md)

[Akira](https://attack.mitre.org/groups/G1024) is a ransomware variant and ransomware deployment entity active since at least March 2023.(Citation: Arctic Wolf Akira 2023) [Akira](https://attack.mitre.org/groups/G1024) uses compromised credentials to access single-factor external access mechanisms such as VPNs for initial access, then various publicly-available tools and techniques for lateral movement.(Citation: Arctic Wolf Akira 2023)(Citation: Secureworks GOLD SAHARA) [Akira](https://attack.mitre.org/groups/G1024) operations are associated with "double extortion" ransomware activity, where data is exfiltrated from victim environments prior to encryption, with threats to publish files if a ransom is not paid. Technical analysis of [Akira](https://attack.mitre.org/software/S1129) ransomware indicates variants capable of targeting Windows or VMWare ESXi hypervisors and multiple overlaps with [Conti](https://attack.mitre.org/software/S0575) ransomware.(Citation: BushidoToken Akira 2023)(Citation: CISA Akira Ransomware APR 2024)(Citation: Cisco Akira Ransomware OCT 2024)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1024)

## Aliases

- GOLD SAHARA
- PUNK SPIDER
- Howling Scorpius

## Techniques used

- [T1531 - Account Access Removal](../../Tactics/15%20TA0040%20-%20Impact/T1531%20-%20Account%20Access%20Removal/README.md)
- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1027.001 - Binary Padding](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.001%20-%20Binary%20Padding/README.md)
- [T1486 - Data Encrypted for Impact](../../Tactics/15%20TA0040%20-%20Impact/T1486%20-%20Data%20Encrypted%20for%20Impact/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1482 - Domain Trust Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1219 - Remote Access Tools](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1213.002 - Sharepoint](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.002%20-%20Sharepoint/README.md)
- [T1558 - Steal or Forge Kerberos Tickets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)

## Software used

- [S0552 - AdFind](../Software/Tools/S0552%20-%20AdFind.md)
- [S1129 - Akira](../Software/Malware/S1129%20-%20Akira.md)
- [S1194 - Akira _v2](../Software/Malware/S1194%20-%20Akira%20_v2.md)
- [S0349 - LaZagne](../Software/Tools/S0349%20-%20LaZagne.md)
- [S1191 - Megazord](../Software/Malware/S1191%20-%20Megazord.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S1040 - Rclone](../Software/Tools/S1040%20-%20Rclone.md)

## Sources

- [CISA Akira Ransomware APR 2024](https://www.cisa.gov/sites/default/files/2024-04/aa24-109a-stopransomware-akira-ransomware_2.pdf)
- [CrowdStrike PUNK SPIDER](https://www.crowdstrike.com/adversaries/punk-spider/)
- [Cisco Akira Ransomware OCT 2024](https://blog.talosintelligence.com/akira-ransomware-continues-to-evolve/)
- [Secureworks GOLD SAHARA](https://www.secureworks.com/research/threat-profiles/gold-sahara)
- [Arctic Wolf Akira 2023](https://arcticwolf.com/resources/blog/conti-and-akira-chained-together/)
- [BushidoToken Akira 2023](https://blog.bushidotoken.net/2023/09/tracking-adversaries-akira-another.html)
- [Palo Alto Howling Scorpius DEC 2024](https://unit42.paloaltonetworks.com/threat-assessment-howling-scorpius-akira-ransomware/)
