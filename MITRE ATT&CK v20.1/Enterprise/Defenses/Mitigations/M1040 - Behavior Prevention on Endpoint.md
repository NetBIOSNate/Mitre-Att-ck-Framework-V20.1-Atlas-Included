# M1040 - Behavior Prevention on Endpoint

[Enterprise](../../README.md) / [Mitigations](README.md)

Behavior Prevention on Endpoint refers to the use of technologies and strategies to detect and block potentially malicious activities by analyzing the behavior of processes, files, API calls, and other endpoint events. Rather than relying solely on known signatures, this approach leverages heuristics, machine learning, and real-time monitoring to identify anomalous patterns indicative of an attack. This mitigation can be implemented through the following measures:

Suspicious Process Behavior:

- Implementation: Use Endpoint Detection and Response (EDR) tools to monitor and block processes exhibiting unusual behavior, such as privilege escalation attempts.
- Use Case: An attacker uses a known vulnerability to spawn a privileged process from a user-level application. The endpoint tool detects the abnormal parent-child process relationship and blocks the action.

Unauthorized File Access:

- Implementation: Leverage Data Loss Prevention (DLP) or endpoint tools to block processes attempting to access sensitive files without proper authorization.
- Use Case: A process tries to read or modify a sensitive file located in a restricted directory, such as /etc/shadow on Linux or the SAM registry hive on Windows. The endpoint tool identifies this anomalous behavior and prevents it.

Abnormal API Calls:

- Implementation: Implement runtime analysis tools to monitor API calls and block those associated with malicious activities.
- Use Case: A process dynamically injects itself into another process to hijack its execution. The endpoint detects the abnormal use of APIs like `OpenProcess` and `WriteProcessMemory` and terminates the offending process.

Exploit Prevention:

- Implementation: Use behavioral exploit prevention tools to detect and block exploits attempting to gain unauthorized access.
- Use Case: A buffer overflow exploit is launched against a vulnerable application. The endpoint detects the anomalous memory write operation and halts the process.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1040)

## Mitigated techniques

- [T1137.006 - Add-ins](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.006%20-%20Add-ins/README.md)
- [T1055.004 - Asynchronous Procedure Call](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.004%20-%20Asynchronous%20Procedure%20Call/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1027.010 - Command Obfuscation](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.010%20-%20Command%20Obfuscation/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1486 - Data Encrypted for Impact](../../Tactics/15%20TA0040%20-%20Impact/T1486%20-%20Data%20Encrypted%20for%20Impact/README.md)
- [T1006 - Direct Volume Access](../../Tactics/07%20TA0005%20-%20Stealth/T1006%20-%20Direct%20Volume%20Access/README.md)
- [T1559.002 - Dynamic Data Exchange](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.002%20-%20Dynamic%20Data%20Exchange/README.md)
- [T1055.001 - Dynamic-link Library Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.001%20-%20Dynamic-link%20Library%20Injection/README.md)
- [T1027.009 - Embedded Payloads](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.009%20-%20Embedded%20Payloads/README.md)
- [T1027.013 - Encrypted/Encoded File](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.013%20-%20Encrypted%20-%20Encoded%20File/README.md)
- [T1564.014 - Extended Attributes](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.014%20-%20Extended%20Attributes/README.md)
- [T1055.011 - Extra Window Memory Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.011%20-%20Extra%20Window%20Memory%20Injection/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1574.013 - KernelCallbackTable](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.013%20-%20KernelCallbackTable/README.md)
- [T1055.015 - ListPlanting](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.015%20-%20ListPlanting/README.md)
- [T1027.012 - LNK Icon Smuggling](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.012%20-%20LNK%20Icon%20Smuggling/README.md)
- [T1003.001 - LSASS Memory](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1036.008 - Masquerade File Type](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.008%20-%20Masquerade%20File%20Type/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1106 - Native API](../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1027 - Obfuscated Files or Information](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/README.md)
- [T1137 - Office Application Startup](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/README.md)
- [T1137.001 - Office Template Macros](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.001%20-%20Office%20Template%20Macros/README.md)
- [T1137.002 - Office Test](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.002%20-%20Office%20Test/README.md)
- [T1003 - OS Credential Dumping](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md)
- [T1137.003 - Outlook Forms](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.003%20-%20Outlook%20Forms/README.md)
- [T1137.004 - Outlook Home Page](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.004%20-%20Outlook%20Home%20Page/README.md)
- [T1137.005 - Outlook Rules](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.005%20-%20Outlook%20Rules/README.md)
- [T1027.014 - Polymorphic Code](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.014%20-%20Polymorphic%20Code/README.md)
- [T1055.002 - Portable Executable Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.002%20-%20Portable%20Executable%20Injection/README.md)
- [T1055.009 - Proc Memory](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.009%20-%20Proc%20Memory/README.md)
- [T1055.013 - Process Doppelgänging](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.013%20-%20Process%20Doppelg%C3%A4nging/README.md)
- [T1055.012 - Process Hollowing](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.012%20-%20Process%20Hollowing/README.md)
- [T1055 - Process Injection](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/README.md)
- [T1055.008 - Ptrace System Calls](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.008%20-%20Ptrace%20System%20Calls/README.md)
- [T1216.001 - PubPrn](../../Tactics/07%20TA0005%20-%20Stealth/T1216%20-%20System%20Script%20Proxy%20Execution/T1216.001%20-%20PubPrn/README.md)
- [T1091 - Replication Through Removable Media](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1091%20-%20Replication%20Through%20Removable%20Media/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1569 - System Services](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/README.md)
- [T1055.003 - Thread Execution Hijacking](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.003%20-%20Thread%20Execution%20Hijacking/README.md)
- [T1055.005 - Thread Local Storage](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.005%20-%20Thread%20Local%20Storage/README.md)
- [T1204 - User Execution](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md)
- [T1055.014 - VDSO Hijacking](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.014%20-%20VDSO%20Hijacking/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1546.003 - Windows Management Instrumentation Event Subscription](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.003%20-%20Windows%20Management%20Instrumentation%20Event%20Subscription/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)
