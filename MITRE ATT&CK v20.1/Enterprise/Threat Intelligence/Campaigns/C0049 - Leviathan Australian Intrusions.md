# C0049 - Leviathan Australian Intrusions

[Enterprise](../../README.md) / [Campaigns](README.md)

[Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049) consisted of at least two long-term intrusions against victims in Australia by [Leviathan](https://attack.mitre.org/groups/G0065), relying on similar tradecraft such as external service exploitation followed by extensive credential capture and re-use to enable privilege escalation and lateral movement. [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049) were focused on exfiltrating sensitive data including valid credentials for the victim organizations.(Citation: CISA Leviathan 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0049)

## Techniques used

- [T1552.001 - Credentials In Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1686 - Disable or Modify System Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1482 - Domain Trust Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1212 - Exploitation for Credential Access](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1212%20-%20Exploitation%20for%20Credential%20Access/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1615 - Group Policy Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1615%20-%20Group%20Policy%20Discovery/README.md)
- [T1056 - Input Capture](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/README.md)
- [T1558.003 - Kerberoasting](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.003%20-%20Kerberoasting/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1111 - Multi-Factor Authentication Interception](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1111%20-%20Multi-Factor%20Authentication%20Interception/README.md)
- [T1135 - Network Share Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1135%20-%20Network%20Share%20Discovery/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1594 - Search Victim-Owned Websites](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1594%20-%20Search%20Victim-Owned%20Websites/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1021.004 - SSH](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.004%20-%20SSH/README.md)
- [T1528 - Steal Application Access Token](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1588.006 - Vulnerabilities](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.006%20-%20Vulnerabilities/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)

## Attributed groups

- [G0065 - Leviathan](../Groups/G0065%20-%20Leviathan.md)

## Sources

- [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
