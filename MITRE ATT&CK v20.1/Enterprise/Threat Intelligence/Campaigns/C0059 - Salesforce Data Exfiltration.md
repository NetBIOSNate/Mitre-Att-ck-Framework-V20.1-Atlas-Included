# C0059 - Salesforce Data Exfiltration

[Enterprise](../../README.md) / [Campaigns](README.md)

The [Salesforce Data Exfiltration](https://attack.mitre.org/campaigns/C0059) campaign began in October 2024 with financially-motivated threat actor UNC6040 using [Spearphishing Voice](https://attack.mitre.org/techniques/T1598/004) (vishing) to compromise corporate Salesforce instances for large-scale data theft and extortion. Following the initial data theft, victim organizations received extortion demands from a separate threat actor, UNC6240, who claimed to be the “ShinyHunters” group. The observed infrastructure and TTPs used during the [Salesforce Data Exfiltration](https://attack.mitre.org/campaigns/C0059) campaign overlap with those used by threat groups with suspected ties to the broader collective known as "The Com.” These overlaps could plausibly be the result of associated actors operating within the same communities and are not necessarily an indication of a direct operational relationship.(Citation: FBI Salesforce Data Theft SEP 2025)(Citation: Google Salesforce JUN 2025)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0059)

## Techniques used

- [T1020 - Automated Exfiltration](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/README.md)
- [T1671 - Cloud Application Integration](../../Tactics/05%20TA0003%20-%20Persistence/T1671%20-%20Cloud%20Application%20Integration/README.md)
- [T1213.004 - Customer Relationship Management Software](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.004%20-%20Customer%20Relationship%20Management%20Software/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1585.002 - Email Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.002%20-%20Email%20Accounts/README.md)
- [T1586.002 - Email Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1586%20-%20Compromise%20Accounts/T1586.002%20-%20Email%20Accounts/README.md)
- [T1585 - Establish Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/README.md)
- [T1567 - Exfiltration Over Web Service](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/README.md)
- [T1083 - File and Directory Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1684.001 - Impersonation](../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/T1684.001%20-%20Impersonation/README.md)
- [T1608.005 - Link Target](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1608%20-%20Stage%20Capabilities/T1608.005%20-%20Link%20Target/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1598.004 - Spearphishing Voice](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/T1598.004%20-%20Spearphishing%20Voice/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)

## Software used

- [S0183 - Tor](../Software/Tools/S0183%20-%20Tor.md)

## Sources

- [FBI Salesforce Data Theft SEP 2025](https://www.ic3.gov/CSA/2025/250912.pdf)
- [Google Salesforce JUN 2025](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion)
