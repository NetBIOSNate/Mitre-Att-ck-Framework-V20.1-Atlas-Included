# C0048 - Operation MidnightEclipse

[Enterprise](../../README.md) / [Campaigns](README.md)

[Operation MidnightEclipse](https://attack.mitre.org/campaigns/C0048) was a campaign conducted in March and April 2024 that involved initial exploit of zero-day vulnerability CVE-2024-3400, a critical command injection vulnerability in the GlobalProtect feature of Palo Alto Networks PAN-OS.(Citation: Volexity UPSTYLE 2024)(Citation: Palo Alto MidnightEclipse APR 2024)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0048)

## Techniques used

- [T1053.003 - Cron](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.003%20-%20Cron/README.md)
- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1074.001 - Local Data Staging](../../Tactics/12%20TA0009%20-%20Collection/T1074%20-%20Data%20Staged/T1074.001%20-%20Local%20Data%20Staging/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1584.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.003%20-%20Virtual%20Private%20Server/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
- [T1584.006 - Web Services](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.006%20-%20Web%20Services/README.md)
- [T1021.006 - Windows Remote Management](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.006%20-%20Windows%20Remote%20Management/README.md)

## Software used

- [S1164 - UPSTYLE](../Software/Malware/S1164%20-%20UPSTYLE.md)

## Sources

- [Palo Alto MidnightEclipse APR 2024](https://unit42.paloaltonetworks.com/cve-2024-3400/)
- [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
