# G1041 - Sea Turtle

[Enterprise](../../README.md) / [Groups](README.md)

[Sea Turtle](https://attack.mitre.org/groups/G1041) is a Türkiye-linked threat actor active since at least 2017 performing espionage and service provider compromise operations against victims in Asia, Europe, and North America. [Sea Turtle](https://attack.mitre.org/groups/G1041) is notable for targeting registrars managing ccTLDs and complex DNS-based intrusions where the threat actor compromised DNS providers to hijack DNS resolution for ultimate victims, enabling [Sea Turtle](https://attack.mitre.org/groups/G1041) to spoof log in portals and other applications for credential collection.(Citation: Talos Sea Turtle 2019)(Citation: Talos Sea Turtle 2019_2)(Citation: PWC Sea Turtle 2023)(Citation: Hunt Sea Turtle 2024)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G1041)

## Aliases

- Teal Kurma
- Marbled Dust
- Cosmic Wolf
- SILICON

## Techniques used

- [T1583 - Acquire Infrastructure](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/README.md)
- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1685.006 - Clear Linux or Mac System Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.006%20-%20Clear%20Linux%20or%20Mac%20System%20Logs/README.md)
- [T1027.004 - Compile After Delivery](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.004%20-%20Compile%20After%20Delivery/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1588.004 - Digital Certificates](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.004%20-%20Digital%20Certificates/README.md)
- [T1583.002 - DNS Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.002%20-%20DNS%20Server/README.md)
- [T1584.002 - DNS Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.002%20-%20DNS%20Server/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1564.011 - Ignore Process Interrupts](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.011%20-%20Ignore%20Process%20Interrupts/README.md)
- [T1608.003 - Install Digital Certificate](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1608%20-%20Stage%20Capabilities/T1608.003%20-%20Install%20Digital%20Certificate/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1114.001 - Local Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1566 - Phishing](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/README.md)
- [T1690 - Prevent Command History Logging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1690%20-%20Prevent%20Command%20History%20Logging/README.md)
- [T1074.002 - Remote Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.002%20-%20Remote%20Data%20Staging/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1199 - Trusted Relationship](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1199%20-%20Trusted%20Relationship/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1583.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.003%20-%20Virtual%20Private%20Server/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1505.003 - Web Shell](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.003%20-%20Web%20Shell/README.md)

## Software used

- [S1163 - SnappyTCP](../Software/Malware/S1163%20-%20SnappyTCP.md)

## Sources

- [Talos Sea Turtle 2019](https://blog.talosintelligence.com/seaturtle/)
- [Hunt Sea Turtle 2024](https://www.huntandhackett.com/blog/turkish-espionage-campaigns)
- [Microsoft Digital Defense 2021](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWMFIi?id=101738)
- [Talos Sea Turtle 2019_2](https://blog.talosintelligence.com/sea-turtle-keeps-on-swimming/)
- [PWC Sea Turtle 2023](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/tortoise-and-malwahare.html)
