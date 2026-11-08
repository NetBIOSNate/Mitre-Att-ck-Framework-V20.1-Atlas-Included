# C0005 - Operation Spalax

[Enterprise](../../README.md) / [Campaigns](README.md)

[Operation Spalax](https://attack.mitre.org/campaigns/C0005) was a campaign that primarily targeted Colombian government organizations and private companies, particularly those associated with the energy and metallurgical industries. The [Operation Spalax](https://attack.mitre.org/campaigns/C0005) threat actors distributed commodity malware and tools using generic phishing topics related to COVID-19, banking, and law enforcement action. Security researchers noted indicators of compromise and some infrastructure overlaps with other campaigns dating back to April 2018, including at least one separately attributed to [APT-C-36](https://attack.mitre.org/groups/G0099), however identified enough differences to report this as separate, unattributed activity.(Citation: ESET Operation Spalax Jan 2021)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0005)

## Techniques used

- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1568 - Dynamic Resolution](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1568%20-%20Dynamic%20Resolution/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1204.001 - Malicious Link](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.001%20-%20Malicious%20Link/README.md)
- [T1588.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.001%20-%20Malware/README.md)
- [T1218.011 - Rundll32](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.011%20-%20Rundll32/README.md)
- [T1027.002 - Software Packing](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.002%20-%20Software%20Packing/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1027.003 - Steganography](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.003%20-%20Steganography/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1608.001 - Upload Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1608%20-%20Stage%20Capabilities/T1608.001%20-%20Upload%20Malware/README.md)
- [T1497 - Virtualization/Sandbox Evasion](../../Tactics/07%20TA0005%20-%20Stealth/T1497%20-%20Virtualization%20-%20Sandbox%20Evasion/README.md)
- [T1102 - Web Service](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/README.md)

## Software used

- [S0385 - njRAT](../Software/Malware/S0385%20-%20njRAT.md)
- [S0332 - Remcos](../Software/Tools/S0332%20-%20Remcos.md)

## Sources

- [ESET Operation Spalax Jan 2021](https://www.welivesecurity.com/2021/01/12/operation-spalax-targeted-malware-attacks-colombia/)
