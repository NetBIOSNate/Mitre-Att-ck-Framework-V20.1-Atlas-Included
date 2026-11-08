# C0040 - APT41 DUST

[Enterprise](../../README.md) / [Campaigns](README.md)

[APT41 DUST](https://attack.mitre.org/campaigns/C0040) was conducted by [APT41](https://attack.mitre.org/groups/G0096) from 2023 to July 2024 against entities in Europe, Asia, and the Middle East. [APT41 DUST](https://attack.mitre.org/campaigns/C0040) targeted sectors such as shipping, logistics, and media for information gathering purposes. [APT41](https://attack.mitre.org/groups/G0096) used previously-observed malware such as [DUSTPAN](https://attack.mitre.org/software/S1158) as well as newly observed tools such as [DUSTTRAP](https://attack.mitre.org/software/S1159) in [APT41 DUST](https://attack.mitre.org/campaigns/C0040).(Citation: Google Cloud APT41 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0040)

## Techniques used

- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1573.002 - Asymmetric Cryptography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1586.003 - Cloud Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1586%20-%20Compromise%20Accounts/T1586.003%20-%20Cloud%20Accounts/README.md)
- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1588.003 - Code Signing Certificates](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.003%20-%20Code%20Signing%20Certificates/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1036.004 - Masquerade Task or Service](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.004%20-%20Masquerade%20Task%20or%20Service/README.md)
- [T1596.005 - Scan Databases](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1596%20-%20Search%20Open%20Technical%20Databases/T1596.005%20-%20Scan%20Databases/README.md)
- [T1593.002 - Search Engines](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/T1593.002%20-%20Search%20Engines/README.md)
- [T1594 - Search Victim-Owned Websites](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1594%20-%20Search%20Victim-Owned%20Websites/README.md)
- [T1583.007 - Serverless](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.007%20-%20Serverless/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1102 - Web Service](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)

## Attributed groups

- [G0096 - APT41](../Groups/G0096%20-%20APT41.md)

## Software used

- [S0160 - certutil](../Software/Tools/S0160%20-%20certutil.md)
- [S0154 - Cobalt Strike](../Software/Malware/S0154%20-%20Cobalt%20Strike.md)
- [S1158 - DUSTPAN](../Software/Malware/S1158%20-%20DUSTPAN.md)
- [S1159 - DUSTTRAP](../Software/Malware/S1159%20-%20DUSTTRAP.md)

## Sources

- [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
