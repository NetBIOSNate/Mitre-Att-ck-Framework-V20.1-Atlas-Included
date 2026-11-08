# S0445 - ShimRatReporter

[Enterprise](../../../README.md) / [Tools](README.md)

[ShimRatReporter](https://attack.mitre.org/software/S0445) is a tool used by suspected Chinese adversary [Mofang](https://attack.mitre.org/groups/G0103) to automatically conduct initial discovery. The details from this discovery are used to customize follow-on payloads (such as [ShimRat](https://attack.mitre.org/software/S0444)) as well as set up faux infrastructure which mimics the adversary's targets. [ShimRatReporter](https://attack.mitre.org/software/S0445) has been used in campaigns targeting multiple countries and sectors including government, military, critical infrastructure, automobile, and weapons development.(Citation: FOX-IT May 2016 Mofang)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0445)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1087 - Account Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/README.md)
- [T1560 - Archive Collected Data](../../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/README.md)
- [T1119 - Automated Collection](../../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1020 - Automated Exfiltration](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1106 - Native API](../../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1027 - Obfuscated Files or Information](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1069 - Permission Groups Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1069%20-%20Permission%20Groups%20Discovery/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1518 - Software Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1518%20-%20Software%20Discovery/README.md)
- [T1082 - System Information Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1082%20-%20System%20Information%20Discovery/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Used by

- [G0103 - Mofang](../../Groups/G0103%20-%20Mofang.md)

## Sources

- [FOX-IT May 2016 Mofang](https://foxitsecurity.files.wordpress.com/2016/06/fox-it_mofang_threatreport_tlp-white.pdf)
