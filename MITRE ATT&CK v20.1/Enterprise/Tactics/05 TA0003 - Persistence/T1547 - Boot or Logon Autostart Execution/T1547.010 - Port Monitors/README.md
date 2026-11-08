# T1547.010 - Port Monitors

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may use port monitors to run an adversary supplied DLL during system boot for persistence or privilege escalation. A port monitor can be set through the <code>AddMonitor</code> API call to set a DLL to be loaded at startup.(Citation: AddMonitor) This DLL can be located in <code>C:\Windows\System32</code> and will be loaded and run by the print spooler service, `spoolsv.exe`, under SYSTEM level permissions on boot.(Citation: Bloxham) 

Alternatively, an arbitrary DLL can be loaded if permissions allow writing a fully-qualified pathname for that DLL to the `Driver` value of an existing or new arbitrarily named subkey of <code>HKLM\SYSTEM\CurrentControlSet\Control\Print\Monitors</code>. The Registry key contains entries for the following:

* Local Port
* Standard TCP/IP Port
* USB Monitor
* WSD Port

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/010)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0204 - Detection Strategy for T1547.010 – Port Monitor DLL Persistence via spoolsv.exe (Windows)](../../../../Defenses/Detection%20Strategies/DET0204%20-%20Detection%20Strategy%20for%20T1547.010%20%E2%80%93%20Port%20Monitor%20DLL%20Persistence%20via%20spoolsv.exe%20%28Wind.md)

## Sources

- [Bloxham](https://www.defcon.org/images/defcon-22/dc-22-presentations/Bloxham/DEFCON-22-Brady-Bloxham-Windows-API-Abuse-UPDATED.pdf)
- [AddMonitor](https://learn.microsoft.com/en-us/windows/win32/printdocs/addmonitor)
- [TechNet Autoruns](https://technet.microsoft.com/en-us/sysinternals/bb963902)
