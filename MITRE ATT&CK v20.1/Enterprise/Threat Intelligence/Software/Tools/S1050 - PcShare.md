# S1050 - PcShare

[Enterprise](../../../README.md) / [Tools](README.md)

[PcShare](https://attack.mitre.org/software/S1050) is an open source remote access tool that has been modified and used by Chinese threat actors, most notably during the FunnyDream campaign since late 2018.(Citation: Bitdefender FunnyDream Campaign November 2020)(Citation: GitHub PcShare 2014)

[MITRE ATT&CK record](https://attack.mitre.org/software/S1050)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Techniques used

- [T1546.015 - Component Object Model Hijacking](../../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.015%20-%20Component%20Object%20Model%20Hijacking/README.md)
- [T1027.015 - Compression](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.015%20-%20Compression/README.md)
- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1140 - Deobfuscate/Decode Files or Information](../../../Tactics/07%20TA0005%20-%20Stealth/T1140%20-%20Deobfuscate%20-%20Decode%20Files%20or%20Information/README.md)
- [T1027.013 - Encrypted/Encoded File](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1070.004 - File Deletion](../../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1036.001 - Invalid Code Signature](../../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.001%20-%20Invalid%20Code%20Signature/README.md)
- [T1056.001 - Keylogging](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1112 - Modify Registry](../../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1106 - Native API](../../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1055 - Process Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1012 - Query Registry](../../../Tactics/10%20TA0007%20-%20Discovery/T1012%20-%20Query%20Registry/README.md)
- [T1218.011 - Rundll32](../../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.011%20-%20Rundll32/README.md)
- [T1113 - Screen Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1125 - Video Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1125%20-%20Video%20Capture/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1059.003 - Windows Command Shell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Used by

- [G1023 - APT5](../../Groups/G1023%20-%20APT5.md)
- [C0007 - FunnyDream](../../Campaigns/C0007%20-%20FunnyDream.md)

## Sources

- [GitHub PcShare 2014](https://github.com/LiveMirror/pcshare)
- [Bitdefender FunnyDream Campaign November 2020](https://www.bitdefender.com/files/News/CaseStudies/study/379/Bitdefender-Whitepaper-Chinese-APT.pdf)
