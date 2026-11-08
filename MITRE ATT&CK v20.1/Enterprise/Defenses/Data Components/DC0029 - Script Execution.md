# DC0029 - Script Execution

[Enterprise](../../README.md) / [Data Components](README.md)

The execution of a text file that contains code via the interpreter.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0029)

## Log sources and channels

- **Script** — None
- **m365:office** — VBA auto_open, auto_close, or document_open events
- **macos:unifiedlog** — log stream --predicate 'eventMessage contains "python"'
- **linux:syslog** — /var/log/syslog
- **WinEventLog:System** — EventCode=1502, 1503
- **macos:unifiedlog** — log stream --predicate 'eventMessage contains "wscript" OR "vbs"'
- **macos:unifiedlog** — osascript or AppleScript invocation modifying UI
- **networkdevice:runtime** — runtime
- **macos:unifiedlog** — log
- **esxi:vmkernel** — boot
- **macos:unifiedlog** — AppleScript creating login item via 'System Events' dictionary
- **WinEventLog:PowerShell** — EventCode=4103, 4104, 4105, 4106
- **WinEventLog:Application** — Stored procedure creation, modification, or xp_cmdshell invocation via SQL logs or SQL Server auditing
- **ApplicationLogs:SQL** — Stored procedure creation or modification with shell invocation (e.g., system(), exec())
- **macos:unifiedlog** — subsystem=launchservices
- **WinEventLog:PowerShell** — Set-ADUser or Set-ADAuthenticationPolicy with MFA attributes disabled
- **EDR:scriptblock** — Process Tree + Script Block Logging
- **linux:syslog** — boot logs
- **m365:defender** — ScriptBlockLogging + AMSI
- **macos:unifiedlog** — log stream with predicate 'eventMessage CONTAINS "osascript"'
- **etw:Microsoft-Antimalware-Scan-Interface** — Amsi/Script content + API verdicts during in-memory staging
- **esxi:shell** — None
- **WinEventLog:System** — EventCode=4016, 5312
- **auditd:PROCTITLE** — scripting loop invoking sleep/ping
- **WinEventLog:PowerShell** — Scripts with references to XML parsing, AES decryption, or gpprefdecrypt logic
- **macos:syslog** — system.log, asl.log
- **macos:osquery** — exec: Unexpected execution of osascript or AppleScript targeting sensitive apps
- **macos:unifiedlog** — subsystem=com.apple.Security or com.apple.applescript
- **azure:activity** — Microsoft.Compute/virtualMachines/runCommand/action: Abnormal initiation of Azure RunCommand jobs or PowerShell/Bash payloads
- **EDR:AMSI** — Malicious inline C#/script blobs embedded in MSBuild projects if intercepted by AMSI-aware loaders (rare but possible via chained LOLBins)
- **macos:unifiedlog** — osascript, AppleScript, or Python execution triggered immediately after HID connection
- **m365:unified** — Scripted Activity
- **auditd:SYSCALL** — Linux Audit SYSCALL/EXECVE/SOCKADDR records (configured audit rule): execve of scripting interpreter making sequential Industrial Control Systems (ICS) protocol reads with output to file, by User Identifier (UID) not in authorized scripting UIDs

## Analytics using this component

- [AN0029 - Analytic 0029](../Analytics/AN0029.md)
- [AN0173 - Analytic 0173](../Analytics/AN0173.md)
- [AN0174 - Analytic 0174](../Analytics/AN0174.md)
- [AN0199 - Analytic 0199](../Analytics/AN0199.md)
- [AN0210 - Analytic 0210](../Analytics/AN0210.md)
- [AN0211 - Analytic 0211](../Analytics/AN0211.md)
- [AN0231 - Analytic 0231](../Analytics/AN0231.md)
- [AN0281 - Analytic 0281](../Analytics/AN0281.md)
- [AN0313 - Analytic 0313](../Analytics/AN0313.md)
- [AN0314 - Analytic 0314](../Analytics/AN0314.md)
- [AN0340 - Analytic 0340](../Analytics/AN0340.md)
- [AN0345 - Analytic 0345](../Analytics/AN0345.md)
- [AN0511 - Analytic 0511](../Analytics/AN0511.md)
- [AN0512 - Analytic 0512](../Analytics/AN0512.md)
- [AN0533 - Analytic 0533](../Analytics/AN0533.md)
- [AN0543 - Analytic 0543](../Analytics/AN0543.md)
- [AN0578 - Analytic 0578](../Analytics/AN0578.md)
- [AN0658 - Analytic 0658](../Analytics/AN0658.md)
- [AN0733 - Analytic 0733](../Analytics/AN0733.md)
- [AN0734 - Analytic 0734](../Analytics/AN0734.md)
- [AN0735 - Analytic 0735](../Analytics/AN0735.md)
- [AN0838 - Analytic 0838](../Analytics/AN0838.md)
- [AN0927 - Analytic 0927](../Analytics/AN0927.md)
- [AN1018 - Analytic 1018](../Analytics/AN1018.md)
- [AN1034 - Analytic 1034](../Analytics/AN1034.md)
- [AN1049 - Analytic 1049](../Analytics/AN1049.md)
- [AN1075 - Analytic 1075](../Analytics/AN1075.md)
- [AN1082 - Analytic 1082](../Analytics/AN1082.md)
- [AN1359 - Analytic 1359](../Analytics/AN1359.md)
- [AN1442 - Analytic 1442](../Analytics/AN1442.md)
- [AN1502 - Analytic 1502](../Analytics/AN1502.md)
- [AN1535 - Analytic 1535](../Analytics/AN1535.md)
- [AN1569 - Analytic 1569](../Analytics/AN1569.md)
- [AN1619 - Analytic 1619](../Analytics/AN1619.md)
- [AN2063 - Analytic 2063](../Analytics/AN2063.md)
- [AN2079 - Analytic 2079](../Analytics/AN2079.md)
