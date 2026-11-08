# C0056 - RedPenguin

[Enterprise](../../README.md) / [Campaigns](README.md)

The [RedPenguin](https://attack.mitre.org/campaigns/C0056) project was launched by Juniper in July 2024 to investigate reported malware infections of Juniper MX Series routers. [RedPenguin](https://attack.mitre.org/campaigns/C0056) activity was separately attributed to [UNC3886](https://attack.mitre.org/groups/G1048) and included the deployment of multiple custom versions of the publicly-available TINYSHELL backdoor on Juniper routers.(Citation: Juniper RedPenguin MAR 2025)(Citation: Mandiant UNC3886 Juniper Routers MAR 2025)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0056)

## Techniques used

- [T1070.007 - Clear Network Connection History and Configurations](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.007%20-%20Clear%20Network%20Connection%20History%20and%20Configurations/README.md)
- [T1554 - Compromise Host Software Binary](../../Tactics/05%20TA0003%20-%20Persistence/T1554%20-%20Compromise%20Host%20Software%20Binary/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1104 - Multi-Stage Channels](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1104%20-%20Multi-Stage%20Channels/README.md)
- [T1059.008 - Network Device CLI](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.008%20-%20Network%20Device%20CLI/README.md)
- [T1040 - Network Sniffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1571 - Non-Standard Port](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1690 - Prevent Command History Logging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1690%20-%20Prevent%20Command%20History%20Logging/README.md)
- [T1057 - Process Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1014 - Rootkit](../../Tactics/07%20TA0005%20-%20Stealth/T1014%20-%20Rootkit/README.md)
- [T1573.001 - Symmetric Cryptography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.001%20-%20Symmetric%20Cryptography/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1205 - Traffic Signaling](../../Tactics/05%20TA0003%20-%20Persistence/T1205%20-%20Traffic%20Signaling/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)

## Software used

- [S1220 - MEDUSA](../Software/Malware/S1220%20-%20MEDUSA.md)
- [S1219 - REPTILE](../Software/Malware/S1219%20-%20REPTILE.md)

## Attributed groups

- [G1048 - UNC3886](../Groups/G1048%20-%20UNC3886.md)

## Sources

- [Juniper RedPenguin MAR 2025](https://supportportal.juniper.net/sfc/servlet.shepherd/document/download/069Dp00000FzdmIIAR?operationContext=S1)
- [Mandiant UNC3886 Juniper Routers MAR 2025](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-targets-juniper-routers)
