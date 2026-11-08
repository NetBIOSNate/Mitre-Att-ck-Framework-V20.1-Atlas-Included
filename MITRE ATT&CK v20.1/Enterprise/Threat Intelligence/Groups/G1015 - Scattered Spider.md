# G1015 - Scattered Spider

[Enterprise](../../README.md) / [Groups](README.md)

[Scattered Spider](https://attack.mitre.org/groups/G1015) is a native English-speaking cybercriminal group active since at least 2022. (Citation: CrowdStrike Scattered Spider Profile) (Citation: MSTIC Octo Tempest Operations October 2023) The group initially targeted customer relationship management (CRM) providers, business process outsourcing (BPO) firms, and telecommunications and technology companies before expanding in 2023 to gaming, hospitality, retail, managed service provider (MSP), manufacturing, and financial sectors. (Citation: MSTIC Octo Tempest Operations October 2023)
[Scattered Spider](https://attack.mitre.org/groups/G1015) relies heavily on social engineering, including impersonating IT and help-desk staff, to gain initial access, bypass multi-factor authentication (MFA), and compromise enterprise networks. The group has adapted its tooling to evade endpoint detection and response (EDR) defenses and used ransomware for financial gain. (Citation: CISA Scattered Spider Advisory November 2023) (Citation: CrowdStrike Scattered Spider BYOVD January 2023) (Citation: Crowdstrike TELCO BPO Campaign December 2022)
[Scattered Spider](https://attack.mitre.org/groups/G1015) had expanded into hybrid cloud and identity environments, using help-desk impersonation and MFA bypass to obtain administrator access in Okta, AWS, and Office 365. (Citation: Mandiant UNC3944 May 2025)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1015)

## Aliases

- Roasted 0ktapus
- Octo Tempest
- Storm-0875
- UNC3944

## Techniques used

- [T1087 - Account Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/README.md)
- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1098.003 - Additional Cloud Roles](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.003%20-%20Additional%20Cloud%20Roles/README.md)
- [T1217 - Browser Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1217%20-%20Browser%20Information%20Discovery/README.md)
- [T1070.008 - Clear Mailbox Data](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.008%20-%20Clear%20Mailbox%20Data/README.md)
- [T1078.004 - Cloud Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1580 - Cloud Infrastructure Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1580%20-%20Cloud%20Infrastructure%20Discovery/README.md)
- [T1538 - Cloud Service Dashboard](../../Tactics/10%20TA0007%20-%20Discovery/T1538%20-%20Cloud%20Service%20Dashboard/README.md)
- [T1021.007 - Cloud Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.007%20-%20Cloud%20Services/README.md)
- [T1213.003 - Code Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.003%20-%20Code%20Repositories/README.md)
- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1556.009 - Conditional Access Policies](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.009%20-%20Conditional%20Access%20Policies/README.md)
- [T1136 - Create Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md)
- [T1578.002 - Create Cloud Instance](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1578%20-%20Modify%20Cloud%20Compute%20Infrastructure/T1578.002%20-%20Create%20Cloud%20Instance/README.md)
- [T1552.001 - Credentials In Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1486 - Data Encrypted for Impact](../../Tactics/15%20TA0040%20-%20Impact/T1486%20-%20Data%20Encrypted%20for%20Impact/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1074 - Data Staged](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/README.md)
- [T1006 - Direct Volume Access](../../Tactics/07%20TA0005%20-%20Stealth/T1006%20-%20Direct%20Volume%20Access/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1087.002 - Domain Account](../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.002%20-%20Domain%20Account/README.md)
- [T1069.002 - Domain Groups](../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/T1069.002%20-%20Domain%20Groups/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1114 - Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/README.md)
- [T1114.003 - Email Forwarding Rule](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.003%20-%20Email%20Forwarding%20Rule/README.md)
- [T1564.008 - Email Hiding Rules](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.008%20-%20Email%20Hiding%20Rules/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1657 - Financial Theft](../../Tactics/15%20TA0040%20-%20Impact/T1657%20-%20Financial%20Theft/README.md)
- [T1589 - Gather Victim Identity Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1589%20-%20Gather%20Victim%20Identity%20Information/README.md)
- [T1684.001 - Impersonation](../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/T1684.001%20-%20Impersonation/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1490 - Inhibit System Recovery](../../Tactics/15%20TA0040%20-%20Impact/T1490%20-%20Inhibit%20System%20Recovery/README.md)
- [T1588.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.001%20-%20Malware/README.md)
- [T1213.005 - Messaging Applications](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.005%20-%20Messaging%20Applications/README.md)
- [T1556.006 - Multi-Factor Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.006%20-%20Multi-Factor%20Authentication/README.md)
- [T1621 - Multi-Factor Authentication Request Generation](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1621%20-%20Multi-Factor%20Authentication%20Request%20Generation/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1555.005 - Password Managers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.005%20-%20Password%20Managers/README.md)
- [T1069 - Permission Groups Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/README.md)
- [T1598 - Phishing for Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1552.004 - Private Keys](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.004%20-%20Private%20Keys/README.md)
- [T1572 - Protocol Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1219.002 - Remote Desktop Software](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.002%20-%20Remote%20Desktop%20Software/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1585.001 - Social Media Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.001%20-%20Social%20Media%20Accounts/README.md)
- [T1598.003 - Spearphishing Link](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/T1598.003%20-%20Spearphishing%20Link/README.md)
- [T1598.004 - Spearphishing Voice](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/T1598.004%20-%20Spearphishing%20Voice/README.md)
- [T1021.004 - SSH](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.004%20-%20SSH/README.md)
- [T1539 - Steal Web Session Cookie](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1484.002 - Trust Modification](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1484%20-%20Domain%20or%20Tenant%20Policy%20Modification/T1484.002%20-%20Trust%20Modification/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1204 - User Execution](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)

## Software used

- [S1068 - BlackCat](../Software/Malware/S1068%20-%20BlackCat.md)
- [S0591 - ConnectWise](../Software/Tools/S0591%20-%20ConnectWise.md)
- [S0349 - LaZagne](../Software/Tools/S0349%20-%20LaZagne.md)
- [S0002 - Mimikatz](../Software/Tools/S0002%20-%20Mimikatz.md)
- [S0508 - ngrok](../Software/Tools/S0508%20-%20ngrok.md)
- [S1148 - Raccoon Stealer](../Software/Malware/S1148%20-%20Raccoon%20Stealer.md)
- [S1040 - Rclone](../Software/Tools/S1040%20-%20Rclone.md)
- [S0183 - Tor](../Software/Tools/S0183%20-%20Tor.md)
- [S9050 - Vidar](../Software/Malware/S9050%20-%20Vidar.md)
- [S0670 - WarzoneRAT](../Software/Malware/S0670%20-%20WarzoneRAT.md)

## Attributed campaigns

- [C0027 - C0027](../Campaigns/C0027%20-%20C0027.md)

## Sources

- [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a)
- [CrowdStrike Scattered Spider BYOVD January 2023](https://www.crowdstrike.com/blog/scattered-spider-attempts-to-avoid-detection-with-bring-your-own-vulnerable-driver-tactic/)
- [CrowdStrike Scattered Spider Profile](https://www.crowdstrike.com/adversaries/scattered-spider/)
- [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944)
- [Mandiant UNC3944 May 2025](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations)
- [Microsoft Threat Actor Naming July 2023](https://learn.microsoft.com/en-us/microsoft-365/security/intelligence/microsoft-threat-actor-naming?view=o365-worldwide)
- [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)
- [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
