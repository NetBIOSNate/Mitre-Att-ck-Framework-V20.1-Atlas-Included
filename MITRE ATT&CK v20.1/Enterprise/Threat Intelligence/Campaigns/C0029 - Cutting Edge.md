# C0029 - Cutting Edge

[Enterprise](../../README.md) / [Campaigns](README.md)

[Cutting Edge](https://attack.mitre.org/campaigns/C0029) was a campaign conducted by suspected China-nexus espionage actors, variously identified as UNC5221/UTA0178 and UNC5325, that began as early as December 2023 with the exploitation of zero-day vulnerabilities in Ivanti Connect Secure (previously Pulse Secure) VPN appliances. [Cutting Edge](https://attack.mitre.org/campaigns/C0029) targeted the U.S. defense industrial base and multiple sectors globally including  telecommunications, financial, aerospace, and technology. [Cutting Edge](https://attack.mitre.org/campaigns/C0029) featured the use of defense evasion and living-off-the-land (LoTL) techniques along with the deployment of web shells and other custom malware.(Citation: Mandiant Cutting Edge January 2024)(Citation: Volexity Ivanti Zero-Day Exploitation January 2024)(Citation: Volexity Ivanti Global Exploitation January 2024)(Citation: Mandiant Cutting Edge Part 2 January 2024)(Citation: Mandiant Cutting Edge Part 3 February 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0029)

## Techniques used

- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1554 - Compromise Host Software Binary](../../Tactics/05%20TA0003%20-%20Persistence/T1554%20-%20Compromise%20Host%20Software%20Binary/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1071.004 - DNS](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.004%20-%20DNS/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1070 - Indicator Removal](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1056.001 - Keylogging](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1584.008 - Network Devices](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.008%20-%20Network%20Devices/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1572 - Protocol Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1594 - Search Victim-Owned Websites](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1594%20-%20Search%20Victim-Owned%20Websites/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1021.004 - SSH](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.004%20-%20SSH/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1070.006 - Timestomp](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.006%20-%20Timestomp/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1205 - Traffic Signaling](../../Tactics/05%20TA0003%20-%20Persistence/T1205%20-%20Traffic%20Signaling/README.md)
- [T1595.002 - Vulnerability Scanning](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1595%20-%20Active%20Scanning/T1595.002%20-%20Vulnerability%20Scanning/README.md)
- [T1056.003 - Web Portal Capture](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.003%20-%20Web%20Portal%20Capture/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)

## Software used

- [S1118 - BUSHWALK](../Software/Malware/S1118%20-%20BUSHWALK.md)
- [S0488 - CrackMapExec](../Software/Tools/S0488%20-%20CrackMapExec.md)
- [S1120 - FRAMESTING](../Software/Malware/S1120%20-%20FRAMESTING.md)
- [S1117 - GLASSTOKEN](../Software/Malware/S1117%20-%20GLASSTOKEN.md)
- [S0357 - Impacket](../Software/Tools/S0357%20-%20Impacket.md)
- [S1119 - LIGHTWIRE](../Software/Malware/S1119%20-%20LIGHTWIRE.md)
- [S1121 - LITTLELAMB.WOOLTEA](../Software/Malware/S1121%20-%20LITTLELAMB.WOOLTEA.md)
- [S1123 - PITSTOP](../Software/Malware/S1123%20-%20PITSTOP.md)
- [S1116 - WARPWIRE](../Software/Malware/S1116%20-%20WARPWIRE.md)
- [S1115 - WIREFIRE](../Software/Malware/S1115%20-%20WIREFIRE.md)
- [S1114 - ZIPLINE](../Software/Malware/S1114%20-%20ZIPLINE.md)

## Sources

- [Volexity Ivanti Global Exploitation January 2024](https://www.volexity.com/blog/2024/01/15/ivanti-connect-secure-vpn-exploitation-goes-global/)
- [Mandiant Cutting Edge Part 3 February 2024](https://www.mandiant.com/resources/blog/investigating-ivanti-exploitation-persistence)
- [Mandiant Cutting Edge Part 2 January 2024](https://www.mandiant.com/resources/blog/investigating-ivanti-zero-day-exploitation)
- [Mandiant Cutting Edge January 2024](https://www.mandiant.com/resources/blog/suspected-apt-targets-ivanti-zero-day)
- [Volexity Ivanti Zero-Day Exploitation January 2024](https://www.volexity.com/blog/2024/01/10/active-exploitation-of-two-zero-day-vulnerabilities-in-ivanti-connect-secure-vpn/)
