# C0007 - FunnyDream

[Enterprise](../../README.md) / [Campaigns](README.md)

[FunnyDream](https://attack.mitre.org/campaigns/C0007) was a suspected Chinese cyber espionage campaign that targeted government and foreign organizations in Malaysia, the Philippines, Taiwan, Vietnam, and other parts of Southeast Asia. Security researchers linked the [FunnyDream](https://attack.mitre.org/campaigns/C0007) campaign to possible Chinese-speaking threat actors through the use of the [Chinoxy](https://attack.mitre.org/software/S1041) backdoor and noted infrastructure overlap with the TAG-16 threat group.(Citation: Bitdefender FunnyDream Campaign November 2020)(Citation: Kaspersky APT Trends Q1 2020)(Citation: Recorded Future Chinese Activity in Southeast Asia December 2021)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0007)

## Software used

- [S1043 - ccf32](../Software/Malware/S1043%20-%20ccf32.md)
- [S1041 - Chinoxy](../Software/Malware/S1041%20-%20Chinoxy.md)
- [S1044 - FunnyDream](../Software/Malware/S1044%20-%20FunnyDream.md)
- [S0100 - ipconfig](../Software/Tools/S0100%20-%20ipconfig.md)
- [S0104 - netstat](../Software/Tools/S0104%20-%20netstat.md)
- [S1050 - PcShare](../Software/Tools/S1050%20-%20PcShare.md)
- [S0096 - Systeminfo](../Software/Tools/S0096%20-%20Systeminfo.md)
- [S0057 - Tasklist](../Software/Tools/S0057%20-%20Tasklist.md)

## Techniques used

- [T1560.001 - Archive via Utility](../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1585.002 - Email Accounts](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/T1585.002%20-%20Email%20Accounts/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1588.001 - Malware](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.001%20-%20Malware/README.md)
- [T1057 - Process Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1082 - System Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)

## Sources

- [Kaspersky APT Trends Q1 2020](https://securelist.com/apt-trends-report-q1-2020/96826/)
- [Recorded Future Chinese Activity in Southeast Asia December 2021](https://go.recordedfuture.com/hubfs/reports/cta-2021-1208.pdf)
- [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
