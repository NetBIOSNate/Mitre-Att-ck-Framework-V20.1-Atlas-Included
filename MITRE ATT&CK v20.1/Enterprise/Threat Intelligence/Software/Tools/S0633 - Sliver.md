# S0633 - Sliver

[Enterprise](../../../README.md) / [Tools](README.md)

[Sliver](https://attack.mitre.org/software/S0633) is an open source, cross-platform, red team command and control (C2) framework written in Golang. [Sliver](https://attack.mitre.org/software/S0633) includes its own package manager, "armory," for staging and downloading additional tools and payloads to the primary C2 framework.(Citation: Bishop Fox Sliver Framework August 2019)(Citation: Cybereason Sliver Undated)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0633)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md)

## Used by

- [G0016 - APT29](../../Groups/G0016%20-%20APT29.md)
- [C0018 - C0018](../../Campaigns/C0018%20-%20C0018.md)
- [G1021 - Cinnamon Tempest](../../Groups/G1021%20-%20Cinnamon%20Tempest.md)
- [G0127 - TA551](../../Groups/G0127%20-%20TA551.md)

## Techniques used

- [T1134 - Access Token Manipulation](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/README.md)
- [T1071 - Application Layer Protocol](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/README.md)
- [T1573.002 - Asymmetric Cryptography](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1548.002 - Bypass User Account Control](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1027.004 - Compile After Delivery](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.004%20-%20Compile%20After%20Delivery/README.md)
- [T1071.004 - DNS](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.004%20-%20DNS/README.md)
- [T1027.013 - Encrypted/Encoded File](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1558.001 - Golden Ticket](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.001%20-%20Golden%20Ticket/README.md)
- [T1105 - Ingress Tool Transfer](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1090.001 - Internal Proxy](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.001%20-%20Internal%20Proxy/README.md)
- [T1003.001 - LSASS Memory](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1027 - Obfuscated Files or Information](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1059.001 - PowerShell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1055 - Process Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1113 - Screen Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1132.001 - Standard Encoding](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1132%20-%20Data%20Encoding/T1132.001%20-%20Standard%20Encoding/README.md)
- [T1001.002 - Steganography](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1001%20-%20Data%20Obfuscation/T1001.002%20-%20Steganography/README.md)
- [T1573.001 - Symmetric Cryptography](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.001%20-%20Symmetric%20Cryptography/README.md)
- [T1016 - System Network Configuration Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1016%20-%20System%20Network%20Configuration%20Discovery/README.md)
- [T1049 - System Network Connections Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1049%20-%20System%20Network%20Connections%20Discovery/README.md)
- [T1071.001 - Web Protocols](../../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Sources

- [Cybereason Sliver Undated](https://www.cybereason.com/blog/sliver-c2-leveraged-by-many-threat-actors)
- [Bishop Fox Sliver Framework August 2019](https://labs.bishopfox.com/tech-blog/sliver)
