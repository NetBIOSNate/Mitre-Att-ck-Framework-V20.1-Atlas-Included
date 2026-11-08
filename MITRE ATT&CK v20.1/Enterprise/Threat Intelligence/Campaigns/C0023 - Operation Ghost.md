# C0023 - Operation Ghost

[Enterprise](../../README.md) / [Campaigns](README.md)

[Operation Ghost](https://attack.mitre.org/campaigns/C0023) was an [APT29](https://attack.mitre.org/groups/G0016) campaign starting in 2013 that included operations against ministries of foreign affairs in Europe and the Washington, D.C. embassy of a European Union country. During [Operation Ghost](https://attack.mitre.org/campaigns/C0023), [APT29](https://attack.mitre.org/groups/G0016) used new families of malware and leveraged web services, steganography, and unique C2 infrastructure for each victim.(Citation: ESET Dukes October 2019)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0023)

## Techniques used

- [T1102.002 - Bidirectional Communication](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/T1102.002%20-%20Bidirectional%20Communication/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1587.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1587%20-%20Develop%20Capabilities/T1587.001%20-%20Malware/README.md)
- [T1585.001 - Social Media Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.001%20-%20Social%20Media%20Accounts/README.md)
- [T1001.002 - Steganography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1001%20-%20Data%20Obfuscation/T1001.002%20-%20Steganography/README.md)
- [T1027.003 - Steganography](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.003%20-%20Steganography/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)

## Software used

- [S0512 - FatDuke](../Software/Malware/S0512%20-%20FatDuke.md)
- [S0051 - MiniDuke](../Software/Malware/S0051%20-%20MiniDuke.md)
- [S0518 - PolyglotDuke](../Software/Malware/S0518%20-%20PolyglotDuke.md)
- [S0029 - PsExec](../Software/Tools/S0029%20-%20PsExec.md)
- [S0511 - RegDuke](../Software/Malware/S0511%20-%20RegDuke.md)

## Attributed groups

- [G0016 - APT29](../Groups/G0016%20-%20APT29.md)

## Sources

- [ESET Dukes October 2019](https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Operation_Ghost_Dukes.pdf)
