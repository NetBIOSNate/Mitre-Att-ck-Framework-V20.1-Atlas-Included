# M1038 - Execution Prevention

[Enterprise](../../README.md) / [Mitigations](README.md)

Prevent the execution of unauthorized or malicious code on systems by implementing application control, script blocking, and other execution prevention mechanisms. This ensures that only trusted and authorized code is executed, reducing the risk of malware and unauthorized actions. This mitigation can be implemented through the following measures:

Application Control:

- Use Case: Use tools like AppLocker or Windows Defender Application Control (WDAC) to create whitelists of authorized applications and block unauthorized ones. On Linux, use tools like SELinux or AppArmor to define mandatory access control policies for application execution.
- Implementation: Allow only digitally signed or pre-approved applications to execute on servers and endpoints. (e.g., `New-AppLockerPolicy -PolicyType Enforced -FilePath "C:\Policies\AppLocker.xml"`) 


Script Blocking:

- Use Case: Use script control mechanisms to block unauthorized execution of scripts, such as PowerShell or JavaScript. Web Browsers: Use browser extensions or settings to block JavaScript execution from untrusted sources.
- Implementation: Configure PowerShell to enforce Constrained Language Mode for non-administrator users. (e.g., `Set-ExecutionPolicy AllSigned`) 

Executable Blocking:

- Use Case: Prevent execution of binaries from suspicious locations, such as `%TEMP%` or `%APPDATA%` directories.
- Implementation: Block execution of `.exe`, `.bat`, or `.ps1` files from user-writable directories.

Dynamic Analysis Prevention:
- Use Case: Use behavior-based execution prevention tools to identify and block malicious activity in real time.
- Implemenation: Employ EDR solutions that analyze runtime behavior and block suspicious code execution.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1038)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1546.008 - Accessibility Features](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.008%20-%20Accessibility%20Features/README.md)
- [T1546.009 - AppCert DLLs](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.009%20-%20AppCert%20DLLs/README.md)
- [T1546.010 - AppInit DLLs](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.010%20-%20AppInit%20DLLs/README.md)
- [T1059.002 - AppleScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.002%20-%20AppleScript/README.md)
- [T1059.010 - AutoHotKey & AutoIT](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.010%20-%20AutoHotKey%20%26%20AutoIT/README.md)
- [T1176.001 - Browser Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.001%20-%20Browser%20Extensions/README.md)
- [T1059.009 - Cloud API](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.009%20-%20Cloud%20API/README.md)
- [T1218.003 - CMSTP](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.003%20-%20CMSTP/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1218.001 - Compiled HTML File](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.001%20-%20Compiled%20HTML%20File/README.md)
- [T1609 - Container Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1609%20-%20Container%20Administration%20Command/README.md)
- [T1059.013 - Container CLI/API](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.013%20-%20Container%20CLI%20-%20API/README.md)
- [T1218.002 - Control Panel](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.002%20-%20Control%20Panel/README.md)
- [T1574.012 - COR_PROFILER](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.012%20-%20COR_PROFILER/README.md)
- [T1699 - Direct Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1699%20-%20Direct%20Prompt%20Injection/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1574.006 - Dynamic Linker Hijacking](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.006%20-%20Dynamic%20Linker%20Hijacking/README.md)
- [T1218.015 - Electron Applications](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.015%20-%20Electron%20Applications/README.md)
- [T1548.004 - Elevated Execution with Prompt](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.004%20-%20Elevated%20Execution%20with%20Prompt/README.md)
- [T1611 - Escape to Host](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1553.001 - Gatekeeper Bypass](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.001%20-%20Gatekeeper%20Bypass/README.md)
- [T1564.003 - Hidden Window](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.003%20-%20Hidden%20Window/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1176.002 - IDE Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/T1176.002%20-%20IDE%20Extensions/README.md)
- [T1219.001 - IDE Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.001%20-%20IDE%20Tunneling/README.md)
- [T1505.004 - IIS Components](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.004%20-%20IIS%20Components/README.md)
- [T1685.007 - Impair Autonomous Defenses](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.007%20-%20Impair%20Autonomous%20Defenses/README.md)
- [T1698 - Indirect Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1698%20-%20Indirect%20Prompt%20Injection/README.md)
- [T1490 - Inhibit System Recovery](../../Tactics/15%20TA0040%20-%20Impact/T1490%20-%20Inhibit%20System%20Recovery/README.md)
- [T1674 - Input Injection](../../Tactics/04%20TA0002%20-%20Execution/T1674%20-%20Input%20Injection/README.md)
- [T1218.004 - InstallUtil](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.004%20-%20InstallUtil/README.md)
- [T1127.003 - JamPlus](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.003%20-%20JamPlus/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1547.006 - Kernel Modules and Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.006%20-%20Kernel%20Modules%20and%20Extensions/README.md)
- [T1546.006 - LC_LOAD_DYLIB Addition](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.006%20-%20LC_LOAD_DYLIB%20Addition/README.md)
- [T1059.011 - Lua](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.011%20-%20Lua/README.md)
- [T1204.004 - Malicious Copy and Paste](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.004%20-%20Malicious%20Copy%20and%20Paste/README.md)
- [T1204.002 - Malicious File](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.002%20-%20Malicious%20File/README.md)
- [T1553.005 - Mark-of-the-Web Bypass](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.005%20-%20Mark-of-the-Web%20Bypass/README.md)
- [T1036.008 - Masquerade File Type](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.008%20-%20Masquerade%20File%20Type/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1218.013 - Mavinject](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.013%20-%20Mavinject/README.md)
- [T1218.014 - MMC](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.014%20-%20MMC/README.md)
- [T1685.003 - Modify or Spoof Tool UI](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.003%20-%20Modify%20or%20Spoof%20Tool%20UI/README.md)
- [T1127.001 - MSBuild](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.001%20-%20MSBuild/README.md)
- [T1218.005 - Mshta](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.005%20-%20Mshta/README.md)
- [T1106 - Native API](../../Tactics/04%20TA0002%20-%20Execution/T1106%20-%20Native%20API/README.md)
- [T1059.008 - Network Device CLI](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.008%20-%20Network%20Device%20CLI/README.md)
- [T1218.008 - Odbcconf](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.008%20-%20Odbcconf/README.md)
- [T1574.007 - Path Interception by PATH Environment Variable](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.007%20-%20Path%20Interception%20by%20PATH%20Environment%20Variable/README.md)
- [T1574.008 - Path Interception by Search Order Hijacking](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.008%20-%20Path%20Interception%20by%20Search%20Order%20Hijacking/README.md)
- [T1574.009 - Path Interception by Unquoted Path](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.009%20-%20Path%20Interception%20by%20Unquoted%20Path/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1216.001 - PubPrn](../../Tactics/07%20TA0005%20-%20Stealth/T1216%20-%20System%20Script%20Proxy%20Execution/T1216.001%20-%20PubPrn/README.md)
- [T1059.006 - Python](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.006%20-%20Python/README.md)
- [T1218.009 - Regsvcs/Regasm](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.009%20-%20Regsvcs%20-%20Regasm/README.md)
- [T1219 - Remote Access Tools](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/README.md)
- [T1219.002 - Remote Desktop Software](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.002%20-%20Remote%20Desktop%20Software/README.md)
- [T1564.006 - Run Virtual Instance](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.006%20-%20Run%20Virtual%20Instance/README.md)
- [T1546.002 - Screensaver](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.002%20-%20Screensaver/README.md)
- [T1129 - Shared Modules](../../Tactics/04%20TA0002%20-%20Execution/T1129%20-%20Shared%20Modules/README.md)
- [T1547.009 - Shortcut Modification](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.009%20-%20Shortcut%20Modification/README.md)
- [T1553.003 - SIP and Trust Provider Hijacking](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.003%20-%20SIP%20and%20Trust%20Provider%20Hijacking/README.md)
- [T1176 - Software Extensions](../../Tactics/05%20TA0003%20-%20Persistence/T1176%20-%20Software%20Extensions/README.md)
- [T1553 - Subvert Trust Controls](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/README.md)
- [T1216.002 - SyncAppvPublishingServer](../../Tactics/07%20TA0005%20-%20Stealth/T1216%20-%20System%20Script%20Proxy%20Execution/T1216.002%20-%20SyncAppvPublishingServer/README.md)
- [T1218 - System Binary Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1216 - System Script Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1216%20-%20System%20Script%20Proxy%20Execution/README.md)
- [T1080 - Taint Shared Content](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1080%20-%20Taint%20Shared%20Content/README.md)
- [T1127 - Trusted Developer Utilities Proxy Execution](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1204 - User Execution](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md)
- [T1218.012 - Verclsid](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.012%20-%20Verclsid/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1059.003 - Windows Command Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.003%20-%20Windows%20Command%20Shell/README.md)
- [T1047 - Windows Management Instrumentation](../../Tactics/04%20TA0002%20-%20Execution/T1047%20-%20Windows%20Management%20Instrumentation/README.md)
- [T1547.004 - Winlogon Helper DLL](../../Tactics/05%20TA0003%20-%20Persistence/T1547%20-%20Boot%20or%20Logon%20Autostart%20Execution/T1547.004%20-%20Winlogon%20Helper%20DLL/README.md)
- [T1220 - XSL Script Processing](../../Tactics/07%20TA0005%20-%20Stealth/T1220%20-%20XSL%20Script%20Processing/README.md)
