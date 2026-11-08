# C0057 - 3CX Supply Chain Attack

[Enterprise](../../README.md) / [Campaigns](README.md)

The [3CX Supply Chain Attack](https://attack.mitre.org/campaigns/C0057) was the first publicly reported case of one supply chain compromise triggering another, leading to a cascading, two-stage intrusion. The initial supply chain attack began when a 3CX employee downloaded and executed a trojanized, end-of-life version of the X_Trader trading software from Trading Technologies. This provided UNC4736, a threat cluster associated with [AppleJeus](https://attack.mitre.org/groups/G1049), access to the 3CX environment. From there UNC4736 compromised the Windows and macOS build environments used to distribute the 3CX desktop application to their customers.(Citation: Mandiant 3cx UNC4736 2023) While 3CX serves more than 600,000 customers and 12 million users, only a subset of systems were affected. Subsequent targeting focused on victims in the defense and cryptocurrency sectors, where attackers deployed secondary payloads such as Gopuram for credential theft and persistence.(Citation: Kaspersky 3CX Gopuram 2023) The campaign began in late 2022 and was disrupted after security vendors publicly reported the compromise in March 2023.(Citation: 3cx official statement 2023)(Citation: Krebs 3cx overview 2023)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0057)

## Techniques used

- [T1217 - Browser Information Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1217%20-%20Browser%20Information%20Discovery/README.md)
- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1195.002 - Compromise Software Supply Chain](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.002%20-%20Compromise%20Software%20Supply%20Chain/README.md)
- [T1102.001 - Dead Drop Resolver](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/T1102.001%20-%20Dead%20Drop%20Resolver/README.md)
- [T1678 - Delay Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1678%20-%20Delay%20Execution/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1189 - Drive-by Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md)
- [T1218.015 - Electron Applications](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.015%20-%20Electron%20Applications/README.md)
- [T1027.009 - Embedded Payloads](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.009%20-%20Embedded%20Payloads/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1546.016 - Installer Packages](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.016%20-%20Installer%20Packages/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1543.004 - Launch Daemon](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.004%20-%20Launch%20Daemon/README.md)
- [T1218.007 - Msiexec](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.007%20-%20Msiexec/README.md)
- [T1027 - Obfuscated Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1055.002 - Portable Executable Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.002%20-%20Portable%20Executable%20Injection/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1620 - Reflective Code Loading](../../Tactics/07%20TA0005%20-%20Stealth/T1620%20-%20Reflective%20Code%20Loading/README.md)
- [T1573.001 - Symmetric Cryptography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.001%20-%20Symmetric%20Cryptography/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Software used

- [S1144 - FRP](../Software/Tools/S1144%20-%20FRP.md)

## Attributed groups

- [G1049 - AppleJeus](../Groups/G1049%20-%20AppleJeus.md)

## Sources

- [3cx official statement 2023](https://www.3cx.com/blog/news/mandiant-security-update2/)
- [Krebs 3cx overview 2023](https://krebsonsecurity.com/2023/04/3cx-breach-was-a-double-supply-chain-compromise/)
- [Kaspersky 3CX Gopuram 2023](https://securelist.com/gopuram-backdoor-deployed-through-3cx-supply-chain-attack/109344/)
- [Mandiant 3cx UNC4736 2023](https://cloud.google.com/blog/topics/threat-intelligence/3cx-software-supply-chain-compromise/)
