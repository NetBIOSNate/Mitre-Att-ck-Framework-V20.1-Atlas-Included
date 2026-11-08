# M1024 - Restrict Registry Permissions

[Enterprise](../../README.md) / [Mitigations](README.md)

Restricting registry permissions involves configuring access control settings for sensitive registry keys and hives to ensure that only authorized users or processes can make modifications. By limiting access, organizations can prevent unauthorized changes that adversaries might use for persistence, privilege escalation, or defense evasion. This mitigation can be implemented through the following measures:

Review and Adjust Permissions on Critical Keys

- Regularly review permissions on keys such as `Run`, `RunOnce`, and `Services` to ensure only authorized users have write access.
- Use tools like `icacls` or `PowerShell` to automate permission adjustments.

Enable Registry Auditing

- Enable auditing on sensitive keys to log access attempts.
- Use Event Viewer or SIEM solutions to analyze logs and detect suspicious activity.
- Example Audit Policy: `auditpol /set /subcategory:"Registry" /success:enable /failure:enable`

Protect Credential-Related Hives

- Limit access to hives like `SAM`,`SECURITY`, and `SYSTEM` to prevent credential dumping or other unauthorized access.
- Use LSA Protection to add an additional security layer for credential storage.

Restrict Registry Editor Usage

- Use Group Policy to restrict access to regedit.exe for non-administrative users.
- Block execution of registry editing tools on endpoints where they are unnecessary.

Deploy Baseline Configuration Tools

- Use tools like Microsoft Security Compliance Toolkit or CIS Benchmarks to apply and maintain secure registry configurations.

*Tools for Implementation* 

Registry Permission Tools:

- Registry Editor (regedit): Built-in tool to manage registry permissions.
- PowerShell: Automate permissions and manage keys. `Set-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Run" -Name "KeyName" -Value "Value"`
- icacls: Command-line tool to modify ACLs.

Monitoring Tools:

- Sysmon: Monitor and log registry events.
- Event Viewer: View registry access logs.

Policy Management Tools:

- Group Policy Management Console (GPMC): Enforce registry permissions via GPOs.
- Microsoft Endpoint Manager: Deploy configuration baselines for registry permissions.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1024)

## Mitigated techniques

- [T1037 - Boot or Logon Initialization Scripts](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/README.md)
- [T1070.007 - Clear Network Connection History and Configurations](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.007%20-%20Clear%20Network%20Connection%20History%20and%20Configurations/README.md)
- [T1553.006 - Code Signing Policy Modification](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.006%20-%20Code%20Signing%20Policy%20Modification/README.md)
- [T1574.012 - COR_PROFILER](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.012%20-%20COR_PROFILER/README.md)
- [T1686 - Disable or Modify System Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1685.001 - Disable or Modify Windows Event Log](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.001%20-%20Disable%20or%20Modify%20Windows%20Event%20Log/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1037.001 - Logon Script (Windows)](../../Tactics/05%20TA0003%20-%20Persistence/T1037%20-%20Boot%20or%20Logon%20Initialization%20Scripts/T1037.001%20-%20Logon%20Script%20%28Windows%29/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1112 - Modify Registry](../../Tactics/05%20TA0003%20-%20Persistence/T1112%20-%20Modify%20Registry/README.md)
- [T1556.008 - Network Provider DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.008%20-%20Network%20Provider%20DLL/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1489 - Service Stop](../../Tactics/15%20TA0040%20-%20Impact/T1489%20-%20Service%20Stop/README.md)
- [T1574.011 - Services Registry Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.011%20-%20Services%20Registry%20Permissions%20Weakness/README.md)
- [T1553.003 - SIP and Trust Provider Hijacking](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.003%20-%20SIP%20and%20Trust%20Provider%20Hijacking/README.md)
- [T1553 - Subvert Trust Controls](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/README.md)
- [T1505.005 - Terminal Services DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.005%20-%20Terminal%20Services%20DLL/README.md)
- [T1547.003 - Time Providers](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.003%20-%20Time%20Providers/README.md)
- [T1686.003 - Windows Host Firewall](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1686%20-%20Disable%20or%20Modify%20System%20Firewall/T1686.003%20-%20Windows%20Host%20Firewall/README.md)
