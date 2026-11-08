# G1035 - Winter Vivern

[Enterprise](../../README.md) / [Groups](README.md)

Winter Vivern is a group linked to Russian and Belorussian interests active since at least 2020 targeting various European government and NGO entities, along with sporadic targeting of Indian and US victims. The group leverages a combination of document-based phishing activity and server-side exploitation for initial access, leveraging adversary-controlled and -created infrastructure for follow-on command and control.(Citation: DomainTools WinterVivern 2021)(Citation: SentinelOne WinterVivern 2023)(Citation: CERT-UA WinterVivern 2023)(Citation: ESET WinterVivern 2023)(Citation: Proofpoint WinterVivern 2023)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1035)

## Aliases

- TA473
- UAC-0114

## Techniques used

- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1020 - Automated Exfiltration](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1189 - Drive-by Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1114.001 - Local Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1204.001 - Malicious Link](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.001%20-%20Malicious%20Link/README.md)
- [T1036.004 - Masquerade Task or Service](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.004%20-%20Masquerade%20Task%20or%20Service/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1113 - Screen Capture](../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1033 - System Owner/User Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1033%20-%20System%20Owner%20-%20User%20Discovery/README.md)
- [T1583.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.003%20-%20Virtual%20Private%20Server/README.md)
- [T1595.002 - Vulnerability Scanning](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.002%20-%20Vulnerability%20Scanning/README.md)
- [T1056.003 - Web Portal Capture](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.003%20-%20Web%20Portal%20Capture/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1584.006 - Web Services](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.006%20-%20Web%20Services/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Sources

- [CERT-UA WinterVivern 2023](https://cert.gov.ua/article/3761104)
- [DomainTools WinterVivern 2021](https://www.domaintools.com/resources/blog/winter-vivern-a-look-at-re-crafted-government-maldocs/)
- [ESET WinterVivern 2023](https://www.welivesecurity.com/en/eset-research/winter-vivern-exploits-zero-day-vulnerability-roundcube-webmail-servers/)
- [Proofpoint WinterVivern 2023](https://www.proofpoint.com/us/blog/threat-insight/exploitation-dish-best-served-cold-winter-vivern-uses-known-zimbra-vulnerability)
- [SentinelOne WinterVivern 2023](https://www.sentinelone.com/labs/winter-vivern-uncovering-a-wave-of-global-espionage/)
