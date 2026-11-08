# T1546.007 - Netsh Helper DLL

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence by executing malicious content triggered by Netsh Helper DLLs. Netsh.exe (also referred to as Netshell) is a command-line scripting utility used to interact with the network configuration of a system. It contains functionality to add helper DLLs for extending functionality of the utility.(Citation: TechNet Netsh) The paths to registered netsh.exe helper DLLs are entered into the Windows Registry at <code>HKLM\SOFTWARE\Microsoft\Netsh</code>.

Adversaries can use netsh.exe helper DLLs to trigger execution of arbitrary code in a persistent manner. This execution would take place anytime netsh.exe is executed, which could happen automatically, with another persistence technique, or if other software (ex: VPN) is present on the system that executes netsh.exe as part of its normal functionality.(Citation: Github Netsh Helper CS Beacon)(Citation: Demaske Netsh Persistence)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/007)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0108 - netsh](../../../../Threat%20Intelligence/Software/Tools/S0108%20-%20netsh.md) — [netsh](https://attack.mitre.org/software/S0108) can be used as a persistence proxy technique to execute a helper DLL when netsh.exe is executed.(Citation: Demaske Netsh Persistence) [Demaske Netsh Persistence](https://htmlpreview.github.io/?https://github.com/MatthewDemaske/blogbackup/blob/master/netshell.html)

## Detection strategies

- [DET0575 - Detection Strategy for Netsh Helper DLL Persistence via Registry and Child Process Monitoring (Windows)](../../../../Defenses/Detection%20Strategies/DET0575%20-%20Detection%20Strategy%20for%20Netsh%20Helper%20DLL%20Persistence%20via%20Registry%20and%20Child%20Process%20Mo.md)

## Sources

- [Demaske Netsh Persistence](https://htmlpreview.github.io/?https://github.com/MatthewDemaske/blogbackup/blob/master/netshell.html)
- [TechNet Netsh](https://technet.microsoft.com/library/bb490939.aspx)
- [Github Netsh Helper CS Beacon](https://github.com/outflankbv/NetshHelperBeacon)
