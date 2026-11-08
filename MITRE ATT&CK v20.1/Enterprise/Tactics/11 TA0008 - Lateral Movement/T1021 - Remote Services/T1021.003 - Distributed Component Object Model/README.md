# T1021.003 - Distributed Component Object Model

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1021 - Remote Services](../README.md)

Adversaries may use [Valid Accounts](https://attack.mitre.org/techniques/T1078) to interact with remote machines by taking advantage of Distributed Component Object Model (DCOM). The adversary may then perform actions as the logged-on user.

The Windows Component Object Model (COM) is a component of the native Windows application programming interface (API) that enables interaction between software objects, or executable code that implements one or more interfaces. Through COM, a client object can call methods of server objects, which are typically Dynamic Link Libraries (DLL) or executables (EXE). Distributed COM (DCOM) is transparent middleware that extends the functionality of COM beyond a local computer using remote procedure call (RPC) technology.(Citation: Fireeye Hunting COM June 2019)(Citation: Microsoft COM)

Permissions to interact with local and remote server COM objects are specified by access control lists (ACL) in the Registry.(Citation: Microsoft Process Wide Com Keys) By default, only Administrators may remotely activate and launch COM objects through DCOM.(Citation: Microsoft COM ACL)

Through DCOM, adversaries operating in the context of an appropriately privileged user can remotely obtain arbitrary and even direct shellcode execution through Office applications(Citation: Enigma Outlook DCOM Lateral Movement Nov 2017) as well as other Windows objects that contain insecure methods.(Citation: Enigma MMC20 COM Jan 2017)(Citation: Enigma DCOM Lateral Movement Jan 2017) DCOM can also execute macros in existing documents(Citation: Enigma Excel DCOM Sept 2017) and may also invoke [Dynamic Data Exchange](https://attack.mitre.org/techniques/T1559/002) (DDE) execution directly through a COM created instance of a Microsoft Office application(Citation: Cyberreason DCOM DDE Lateral Movement Nov 2017), bypassing the need for a malicious document. DCOM can be used as a method of remotely interacting with [Windows Management Instrumentation](https://attack.mitre.org/techniques/T1047).(Citation: MSDN WMI)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1021/003)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can deliver Beacon payloads for lateral movement by leveraging remote COM execution.(Citation: Cobalt Strike DCOM Jan 2017) [Cobalt Strike DCOM Jan 2017](https://blog.cobaltstrike.com/2017/01/24/scripting-matt-nelsons-mmc20-application-lateral-movement-technique/)
- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can utilize <code>Invoke-DCOM</code> to leverage remote COM execution for lateral movement.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0692 - SILENTTRINITY](../../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) can use `System` namespace methods to execute lateral movement using DCOM.(Citation: GitHub SILENTTRINITY Modules July 2019) [GitHub SILENTTRINITY Modules July 2019](https://github.com/byt3bl33d3r/SILENTTRINITY/tree/master/silenttrinity/core/teamserver/modules/boo)

## Mitigations

- [M1048 - Application Isolation and Sandboxing](../../../../Defenses/Mitigations/M1048%20-%20Application%20Isolation%20and%20Sandboxing.md) — Ensure all COM alerts and Protected View are enabled.(Citation: Microsoft Protected View) [Microsoft Protected View](https://support.office.com/en-us/article/What-is-Protected-View-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)
- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider disabling DCOM through Dcomcnfg.exe.(Citation: Microsoft Disable DCOM) [Microsoft Disable DCOM](https://technet.microsoft.com/library/cc771387.aspx)
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Enable Windows firewall, which prevents DCOM instantiation by default.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Modify Registry settings (directly or using Dcomcnfg.exe) in `HKEY_LOCAL_MACHINE\SOFTWARE\Classes\AppID\{{AppID_GUID}}` associated with the process-wide security of individual COM applications.(Citation: Microsoft Process Wide Com Keys) Modify Registry settings (directly or using Dcomcnfg.exe) in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Ole` associated with system-wide security defaults for all COM applications that do not set their own process-wide security.(Citation: Microsoft System Wide Com Keys) (Citation: Microsoft COM ACL) [Microsoft Process Wide Com Keys](https://msdn.microsoft.com/en-us/library/windows/desktop/ms687317%28v=vs.85%29.aspx) · [Microsoft System Wide Com Keys](https://msdn.microsoft.com/en-us/library/windows/desktop/ms694331%28v=vs.85%29.aspx) · [Microsoft COM ACL](https://docs.microsoft.com/en-us/windows/desktop/com/dcom-security-enhancements-in-windows-xp-service-pack-2-and-windows-server-2003-service-pack-1)

## Detection strategies

- [DET0285 - Multi-Event Behavioral Detection for DCOM-Based Remote Code Execution](../../../../Defenses/Detection%20Strategies/DET0285%20-%20Multi-Event%20Behavioral%20Detection%20for%20DCOM-Based%20Remote%20Code%20Execution.md)

## Sources

- [Fireeye Hunting COM June 2019](https://www.fireeye.com/blog/threat-research/2019/06/hunting-com-objects.html)
- [Microsoft COM](https://msdn.microsoft.com/library/windows/desktop/ms680573.aspx)
- [Microsoft COM ACL](https://docs.microsoft.com/en-us/windows/desktop/com/dcom-security-enhancements-in-windows-xp-service-pack-2-and-windows-server-2003-service-pack-1)
- [Microsoft Process Wide Com Keys](https://msdn.microsoft.com/en-us/library/windows/desktop/ms687317%28v=vs.85%29.aspx)
- [MSDN WMI](https://msdn.microsoft.com/en-us/library/aa394582.aspx)
- [Enigma DCOM Lateral Movement Jan 2017](https://enigma0x3.net/2017/01/23/lateral-movement-via-dcom-round-2/)
- [Enigma MMC20 COM Jan 2017](https://enigma0x3.net/2017/01/05/lateral-movement-using-the-mmc20-application-com-object/)
- [Enigma Outlook DCOM Lateral Movement Nov 2017](https://enigma0x3.net/2017/11/16/lateral-movement-using-outlooks-createobject-method-and-dotnettojscript/)
- [Enigma Excel DCOM Sept 2017](https://enigma0x3.net/2017/09/11/lateral-movement-using-excel-application-and-dcom/)
- [Cyberreason DCOM DDE Lateral Movement Nov 2017](https://www.cybereason.com/blog/leveraging-excel-dde-for-lateral-movement-via-dcom)
