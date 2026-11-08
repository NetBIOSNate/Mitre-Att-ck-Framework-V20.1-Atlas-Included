# C0054 - Operation Triangulation

[Mobile](../../README.md) / [Campaigns](README.md)

[Operation Triangulation](https://attack.mitre.org/campaigns/C0054) is a mobile campaign targeting iOS devices.(Citation: SecureList OpTriangulation 01Jun2023) The unidentified actors used zero-click exploits in iMessage attachments to gain [Initial Access](https://attack.mitre.org/tactics/TA0027), then executed exploits and validators, such as [Binary Validator](https://attack.mitre.org/software/S1215) before finally executing the [TriangleDB](https://attack.mitre.org/software/S1216) implant.

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0054)

## Techniques used

- [T1437 - Application Layer Protocol](../../Tactics/10%20TA0037%20-%20Command%20and%20Control/T1437%20-%20Application%20Layer%20Protocol/README.md)
- [T1521.002 - Asymmetric Cryptography](../../Tactics/10%20TA0037%20-%20Command%20and%20Control/T1521%20-%20Encrypted%20Channel/T1521.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1429 - Audio Capture](../../Tactics/09%20TA0035%20-%20Collection/T1429%20-%20Audio%20Capture/README.md)
- [T1533 - Data from Local System](../../Tactics/09%20TA0035%20-%20Collection/T1533%20-%20Data%20from%20Local%20System/README.md)
- [T1658 - Exploitation for Client Execution](../../Tactics/02%20TA0041%20-%20Execution/T1658%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1404 - Exploitation for Privilege Escalation](../../Tactics/04%20TA0029%20-%20Privilege%20Escalation/T1404%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1420 - File and Directory Discovery](../../Tactics/07%20TA0032%20-%20Discovery/T1420%20-%20File%20and%20Directory%20Discovery/README.md)
- [T1630.002 - File Deletion](../../Tactics/05%20TA0030%20-%20Defense%20Evasion/T1630%20-%20Indicator%20Removal%20on%20Host/T1630.002%20-%20File%20Deletion/README.md)
- [T1630 - Indicator Removal on Host](../../Tactics/05%20TA0030%20-%20Defense%20Evasion/T1630%20-%20Indicator%20Removal%20on%20Host/README.md)
- [T1544 - Ingress Tool Transfer](../../Tactics/10%20TA0037%20-%20Command%20and%20Control/T1544%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1634.001 - Keychain](../../Tactics/06%20TA0031%20-%20Credential%20Access/T1634%20-%20Credentials%20from%20Password%20Store/T1634.001%20-%20Keychain/README.md)
- [T1430 - Location Tracking](../../Tactics/07%20TA0032%20-%20Discovery/T1430%20-%20Location%20Tracking/README.md)
- [T1575 - Native API](../../Tactics/02%20TA0041%20-%20Execution/T1575%20-%20Native%20API/README.md)
- [T1424 - Process Discovery](../../Tactics/07%20TA0032%20-%20Discovery/T1424%20-%20Process%20Discovery/README.md)
- [T1636.004 - SMS Messages](../../Tactics/09%20TA0035%20-%20Collection/T1636%20-%20Protected%20User%20Data/T1636.004%20-%20SMS%20Messages/README.md)
- [T1418 - Software Discovery](../../Tactics/07%20TA0032%20-%20Discovery/T1418%20-%20Software%20Discovery/README.md)
- [T1409 - Stored Application Data](../../Tactics/09%20TA0035%20-%20Collection/T1409%20-%20Stored%20Application%20Data/README.md)
- [T1521.001 - Symmetric Cryptography](../../Tactics/10%20TA0037%20-%20Command%20and%20Control/T1521%20-%20Encrypted%20Channel/T1521.001%20-%20Symmetric%20Cryptography/README.md)
- [T1426 - System Information Discovery](../../Tactics/07%20TA0032%20-%20Discovery/T1426%20-%20System%20Information%20Discovery/README.md)
- [T1422 - System Network Configuration Discovery](../../Tactics/07%20TA0032%20-%20Discovery/T1422%20-%20System%20Network%20Configuration%20Discovery/README.md)

## Software used

- [S1215 - Binary Validator](../Software/Malware/S1215%20-%20Binary%20Validator.md)
- [S1216 - TriangleDB](../Software/Malware/S1216%20-%20TriangleDB.md)

## Sources

- [SecureList OpTriangulation 01Jun2023](https://securelist.com/operation-triangulation/109842/)
