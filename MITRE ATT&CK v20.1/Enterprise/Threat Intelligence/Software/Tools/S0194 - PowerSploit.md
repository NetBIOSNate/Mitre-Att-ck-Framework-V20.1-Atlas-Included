# S0194 - PowerSploit

[Enterprise](../../../README.md) / [Tools](README.md)

[PowerSploit](https://attack.mitre.org/software/S0194) is an open source, offensive security framework comprised of [PowerShell](https://attack.mitre.org/techniques/T1059/001) modules and scripts that perform a wide range of tasks related to penetration testing such as code execution, persistence, bypassing anti-virus, recon, and exfiltration. (Citation: GitHub PowerSploit May 2012) (Citation: PowerShellMagazine PowerSploit July 2014) (Citation: PowerSploit Documentation)

[MITRE ATT&CK record](https://attack.mitre.org/software/S0194)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Used by

- [G0064 - APT33](../../Groups/G0064%20-%20APT33.md)
- [G0096 - APT41](../../Groups/G0096%20-%20APT41.md)
- [C0004 - CostaRicto](../../Campaigns/C0004%20-%20CostaRicto.md)
- [G1006 - Earth Lusca](../../Groups/G1006%20-%20Earth%20Lusca.md)
- [G0046 - FIN7](../../Groups/G0046%20-%20FIN7.md)
- [G0065 - Leviathan](../../Groups/G0065%20-%20Leviathan.md)
- [G0045 - menuPass](../../Groups/G0045%20-%20menuPass.md)
- [G0069 - MuddyWater](../../Groups/G0069%20-%20MuddyWater.md)
- [C0014 - Operation Wocao](../../Campaigns/C0014%20-%20Operation%20Wocao.md)
- [G0040 - Patchwork](../../Groups/G0040%20-%20Patchwork.md)
- [G0092 - TA505](../../Groups/G0092%20-%20TA505.md)

## Techniques used

- [T1134 - Access Token Manipulation](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1134%20-%20Access%20Token%20Manipulation/README.md)
- [T1123 - Audio Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1123%20-%20Audio%20Capture/README.md)
- [T1027.010 - Command Obfuscation](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.010%20-%20Command%20Obfuscation/README.md)
- [T1552.002 - Credentials in Registry](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.002%20-%20Credentials%20in%20Registry/README.md)
- [T1005 - Data from Local System](../../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1574.001 - DLL](../../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1482 - Domain Trust Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1055.001 - Dynamic-link Library Injection](../../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1055%20-%20Process%20Injection/T1055.001%20-%20Dynamic-link%20Library%20Injection/README.md)
- [T1552.006 - Group Policy Preferences](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.006%20-%20Group%20Policy%20Preferences/README.md)
- [T1027.005 - Indicator Removal from Tools](../../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.005%20-%20Indicator%20Removal%20from%20Tools/README.md)
- [T1558.003 - Kerberoasting](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.003%20-%20Kerberoasting/README.md)
- [T1056.001 - Keylogging](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1056%20-%20Input%20Capture/T1056.001%20-%20Keylogging/README.md)
- [T1087.001 - Local Account](../../../Tactics/10%20TA0007%20-%20Discovery/T1087%20-%20Account%20Discovery/T1087.001%20-%20Local%20Account/README.md)
- [T1003.001 - LSASS Memory](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.001%20-%20LSASS%20Memory/README.md)
- [T1574.007 - Path Interception by PATH Environment Variable](../../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.007%20-%20Path%20Interception%20by%20PATH%20Environment%20Variable/README.md)
- [T1574.008 - Path Interception by Search Order Hijacking](../../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.008%20-%20Path%20Interception%20by%20Search%20Order%20Hijacking/README.md)
- [T1574.009 - Path Interception by Unquoted Path](../../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.009%20-%20Path%20Interception%20by%20Unquoted%20Path/README.md)
- [T1059.001 - PowerShell](../../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1057 - Process Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1057%20-%20Process%20Discovery/README.md)
- [T1012 - Query Registry](../../../Tactics/10%20TA0007%20-%20Discovery/T1012%20-%20Query%20Registry/README.md)
- [T1620 - Reflective Code Loading](../../../Tactics/07%20TA0005%20-%20Stealth/T1620%20-%20Reflective%20Code%20Loading/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](../../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1053.005 - Scheduled Task](../../../Tactics/04%20TA0002%20-%20Execution/T1053%20-%20Scheduled%20Task%20-%20Job/T1053.005%20-%20Scheduled%20Task/README.md)
- [T1113 - Screen Capture](../../../Tactics/12%20TA0009%20-%20Collection/T1113%20-%20Screen%20Capture/README.md)
- [T1547.005 - Security Support Provider](../../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.005%20-%20Security%20Support%20Provider/README.md)
- [T1555.004 - Windows Credential Manager](../../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.004%20-%20Windows%20Credential%20Manager/README.md)
- [T1047 - Windows Management Instrumentation](../../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1543.003 - Windows Service](../../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)

## Sources

- [PowerShellMagazine PowerSploit July 2014](http://www.powershellmagazine.com/2014/07/08/powersploit/)
- [GitHub PowerSploit May 2012](https://github.com/PowerShellMafia/PowerSploit)
- [PowerSploit Documentation](http://powersploit.readthedocs.io)
