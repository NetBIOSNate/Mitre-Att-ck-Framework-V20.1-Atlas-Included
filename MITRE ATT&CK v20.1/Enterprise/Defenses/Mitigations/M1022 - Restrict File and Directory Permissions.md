# M1022 - Restrict File and Directory Permissions

[Enterprise](../../README.md) / [Mitigations](README.md)

Restricting file and directory permissions involves setting access controls at the file system level to limit which users, groups, or processes can read, write, or execute files. By configuring permissions appropriately, organizations can reduce the attack surface for adversaries seeking to access sensitive data, plant malicious code, or tamper with system files.

Enforce Least Privilege Permissions:

- Remove unnecessary write permissions on sensitive files and directories.
- Use file ownership and groups to control access for specific roles.

Example (Windows): Right-click the shared folder → Properties → Security tab → Adjust permissions for NTFS ACLs.

Harden File Shares:

- Disable anonymous access to shared folders.
- Enforce NTFS permissions for shared folders on Windows.

Example: Set permissions to restrict write access to critical files, such as system executables (e.g., `/bin` or `/sbin` on Linux). Use tools like `chown` and `chmod` to assign file ownership and limit access.

On Linux, apply:
`chmod 750 /etc/sensitive.conf`
`chown root:admin /etc/sensitive.conf`

File Integrity Monitoring (FIM):

- Use tools like Tripwire, Wazuh, or OSSEC to monitor changes to critical file permissions.

Audit File System Access:

- Enable auditing to track permission changes or unauthorized access attempts.
- Use auditd (Linux) or Event Viewer (Windows) to log activities.

Restrict Startup Directories:

- Configure permissions to prevent unauthorized writes to directories like `C:\ProgramData\Microsoft\Windows\Start Menu`.

Example: Restrict write access to critical directories like `/etc/`, `/usr/local/`, and Windows directories such as `C:\Windows\System32`.

- On Windows, use icacls to modify permissions: `icacls "C:\Windows\System32" /inheritance:r /grant:r SYSTEM:(OI)(CI)F`
- On Linux, monitor permissions using tools like `lsattr` or `auditd`.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1022)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1700 - AI-Enabled Exfiltration](../../Tactics/14%20TA0010%20-%20Exfiltration/T1700%20-%20AI-Enabled%20Exfiltration/README.md)
- [T1574.014 - AppDomainManager](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.014%20-%20AppDomainManager/README.md)
- [T1037 - Boot or Logon Initialization Scripts](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/README.md)
- [T1070.003 - Clear Command History](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.003%20-%20Clear%20Command%20History/README.md)
- [T1685.006 - Clear Linux or Mac System Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.006%20-%20Clear%20Linux%20or%20Mac%20System%20Logs/README.md)
- [T1070.008 - Clear Mailbox Data](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.008%20-%20Clear%20Mailbox%20Data/README.md)
- [T1070.009 - Clear Persistence](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.009%20-%20Clear%20Persistence/README.md)
- [T1685.005 - Clear Windows Event Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1218.002 - Control Panel](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.002%20-%20Control%20Panel/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1552.001 - Credentials In Files](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1565 - Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/README.md)
- [T1686 - Disable or Modify System Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1685.001 - Disable or Modify Windows Event Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.001%20-%20Disable%20or%20Modify%20Windows%20Event%20Log/README.md)
- [T1574.004 - Dylib Hijacking](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.004%20-%20Dylib%20Hijacking/README.md)
- [T1048 - Exfiltration Over Alternative Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/README.md)
- [T1222 - File and Directory Permissions Modification](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1685.007 - Impair Autonomous Defenses](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.007%20-%20Impair%20Autonomous%20Defenses/README.md)
- [T1070 - Indicator Removal](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/README.md)
- [T1698 - Indirect Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1698%20-%20Indirect%20Prompt%20Injection/README.md)
- [T1543.001 - Launch Agent](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.001%20-%20Launch%20Agent/README.md)
- [T1222.002 - Linux and Mac Permissions](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/T1222.002%20-%20Linux%20and%20Mac%20Permissions/README.md)
- [T1037.002 - Login Hook](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/T1037.002%20-%20Login%20Hook/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1037.003 - Network Logon Script](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/T1037.003%20-%20Network%20Logon%20Script/README.md)
- [T1564.004 - NTFS File Attributes](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.004%20-%20NTFS%20File%20Attributes/README.md)
- [T1574.007 - Path Interception by PATH Environment Variable](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.007%20-%20Path%20Interception%20by%20PATH%20Environment%20Variable/README.md)
- [T1574.008 - Path Interception by Search Order Hijacking](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.008%20-%20Path%20Interception%20by%20Search%20Order%20Hijacking/README.md)
- [T1574.009 - Path Interception by Unquoted Path](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.009%20-%20Path%20Interception%20by%20Unquoted%20Path/README.md)
- [T1546.013 - PowerShell Profile](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.013%20-%20PowerShell%20Profile/README.md)
- [T1552.004 - Private Keys](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.004%20-%20Private%20Keys/README.md)
- [T1055.009 - Proc Memory](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.009%20-%20Proc%20Memory/README.md)
- [T1037.004 - RC Scripts](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/T1037.004%20-%20RC%20Scripts/README.md)
- [T1036.003 - Rename Legitimate Utilities](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.003%20-%20Rename%20Legitimate%20Utilities/README.md)
- [T1565.003 - Runtime Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/T1565.003%20-%20Runtime%20Data%20Manipulation/README.md)
- [T1053 - Scheduled Task/Job](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/README.md)
- [T1569.002 - Service Execution](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/T1569.002%20-%20Service%20Execution/README.md)
- [T1489 - Service Stop](../../Tactics/15%20TA0040%20-%20Impact/T1489%20-%20Service%20Stop/README.md)
- [T1547.009 - Shortcut Modification](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.009%20-%20Shortcut%20Modification/README.md)
- [T1553.003 - SIP and Trust Provider Hijacking](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.003%20-%20SIP%20and%20Trust%20Provider%20Hijacking/README.md)
- [T1098.004 - SSH Authorized Keys](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.004%20-%20SSH%20Authorized%20Keys/README.md)
- [T1563.001 - SSH Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.001%20-%20SSH%20Hijacking/README.md)
- [T1037.005 - Startup Items](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/T1037.005%20-%20Startup%20Items/README.md)
- [T1565.001 - Stored Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/T1565.001%20-%20Stored%20Data%20Manipulation/README.md)
- [T1548.003 - Sudo and Sudo Caching](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.003%20-%20Sudo%20and%20Sudo%20Caching/README.md)
- [T1569 - System Services](../../Tactics/04%20TA0002%20-%20Execution/T1569%20-%20System%20Services/README.md)
- [T1543.002 - Systemd Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.002%20-%20Systemd%20Service/README.md)
- [T1053.006 - Systemd Timers](../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.006%20-%20Systemd%20Timers/README.md)
- [T1080 - Taint Shared Content](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1080%20-%20Taint%20Shared%20Content/README.md)
- [T1548.006 - TCC Manipulation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.006%20-%20TCC%20Manipulation/README.md)
- [T1547.003 - Time Providers](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.003%20-%20Time%20Providers/README.md)
- [T1546.004 - Unix Shell Configuration Modification](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.004%20-%20Unix%20Shell%20Configuration%20Modification/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1686.003 - Windows Host Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.003%20-%20Windows%20Host%20Firewall/README.md)
- [T1222.001 - Windows Permissions](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1222%20-%20File%20and%20Directory%20Permissions%20Modification/T1222.001%20-%20Windows%20Permissions/README.md)
- [T1547.013 - XDG Autostart Entries](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.013%20-%20XDG%20Autostart%20Entries/README.md)
