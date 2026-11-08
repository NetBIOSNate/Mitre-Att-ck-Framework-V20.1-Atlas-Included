# G0091 - Silence

[Enterprise](../../README.md) / [Groups](README.md)

[Silence](https://attack.mitre.org/groups/G0091) is a financially motivated threat actor targeting financial institutions in different countries. The group was first seen in June 2016. Their main targets reside in Russia, Ukraine, Belarus, Azerbaijan, Poland and Kazakhstan. They compromised various banking systems, including the Russian Central Bank's Automated Workstation Client, ATMs, and card processing.(Citation: Cyber Forensicator Silence Jan 2019)(Citation: SecureList Silence Nov 2017)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0091)

## Aliases

- Whisper Spider

## Techniques used

- [T1553.002 - Code Signing](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.002%20-%20Code%20Signing/README.md)
- [T1027.010 - Command Obfuscation](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.010%20-%20Command%20Obfuscation/README.md)
- [T1218.001 - Compiled HTML File](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.001%20-%20Compiled%20HTML%20File/README.md)
- [T1090.002 - External Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.002%20-%20External%20Proxy/README.md)
- [T1070.004 - File Deletion](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.004%20-%20File%20Deletion/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1112 - Modify Registry](../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1106 - Native API](../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1571 - Non-Standard Port](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1018 - Remote System Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1018%20-%20Remote%20System%20Discovery/README.md)
- [T1053.005 - Scheduled Task](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1113 - Screen Capture](../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1125 - Video Capture](../../Tactics/12%20TA0009%20-%20Collection/T1125%20-%20Video%20Capture/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)

## Software used

- [S0363 - Empire](../Software/Tools/S0363%20-%20Empire.md)
- [S0195 - SDelete](../Software/Tools/S0195%20-%20SDelete.md)
- [S0191 - Winexe](../Software/Tools/S0191%20-%20Winexe.md)

## Sources

- [Crowdstrike GTR2020 Mar 2020](https://go.crowdstrike.com/rs/281-OBQ-266/images/Report2020CrowdStrikeGlobalThreatReport.pdf)
- [SecureList Silence Nov 2017](https://securelist.com/the-silence/83009/)
- [Cyber Forensicator Silence Jan 2019](https://web.archive.org/web/20220119133748/https://cyberforensicator.com/2019/01/20/silence-dissecting-malicious-chm-files-and-performing-forensic-analysis/)
