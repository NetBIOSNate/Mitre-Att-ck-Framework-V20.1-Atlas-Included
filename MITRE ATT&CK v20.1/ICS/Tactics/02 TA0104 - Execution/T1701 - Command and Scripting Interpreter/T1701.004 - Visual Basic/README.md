# T1701.004 - Visual Basic

[ICS](../../../../README.md) / [Execution](../../README.md) / [T1701 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse Visual Basic (VB) for execution. VB is a programming language created by Microsoft with interoperability with many Windows technologies such as [Component Object Model](https://attack.mitre.org/techniques/T1559/001) and the [Native API](https://attack.mitre.org/techniques/T1106) through the Windows API. Although tagged as legacy with no planned future evolutions, VB is integrated and supported in the .NET Framework and cross-platform .NET Core.(Citation: VB .NET Mar 2020)(Citation: VB Microsoft)

Derivative languages based on VB have also been created, such as Visual Basic for Applications (VBA) and VBScript. VBA is an event-driven programming language built into Microsoft Office, as well as several third-party applications.(Citation: Microsoft VBA)(Citation: Wikipedia VBA) VBA enables documents to contain macros used to automate the execution of tasks and other functionality on the host. VBScript is a default scripting language on Windows hosts and can also be used in place of [JavaScript](https://attack.mitre.org/techniques/T1701/006) on HTML Application (HTA) webpages served to Internet Explorer (though most modern browsers do not come with VBScript support).(Citation: Microsoft VBScript)

Adversaries may use VB payloads to execute malicious commands. Common malicious usage includes automating execution of behaviors with VBScript or embedding VBA content into [Spearphishing Attachment](https://attack.mitre.org/techniques/T1566/001) payloads (which may also involve [Mark-of-the-Web Bypass](https://attack.mitre.org/techniques/T1553/005) to enable execution).

Within industrial control system networks, adversaries may abuse the use of VB and VBScript on overlap assets that run on Microsoft Windows operating systems, especially in cases where legacy versions are still used in operations (Workstations, Data Historians, Human Machine Interfaces, Application Servers, Jump Hosts, etc.).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701/004)

**Tactics**  [Execution](../../README.md)

## Mitigations

- [M0949 - Antivirus/Antimalware](../../../../Defenses/Mitigations/M0949%20-%20Antivirus%20-%20Antimalware.md) — Apply exploit-protection controls to Windows applications capable of invoking VBA/VBScript, particularly Office and legacy applications present on ICS overlap assets, after compatibility testing.
- [M0942 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable Windows Script Host, Office macro capability, or other VB execution surfaces only on ICS assets where they are not required by validated vendor or engineering workflows.
- [M0938 - Execution Prevention](../../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Use application control and macro/script restrictions to prevent unapproved VBS/VBA/VBScript execution, while explicitly allowlisting required vendor macros and engineering automation.
- [M0950 - Exploit Protection](../../../../Defenses/Mitigations/M0950%20-%20Exploit%20Protection.md) — Harden applications that can host or launch VB/VBA/VBScript content and reduce exposed script-host execution paths where operationally feasible.
- [M0921 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M0921%20-%20Restrict%20Web-Based%20Content.md) — Limit retrieval and execution of untrusted web or document-based active content on ICS workstations and jump hosts, especially where those systems can reach control assets.

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) utilized VBS and batch scripts for file movement and as wrappers for PowerShell execution.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0034 - 2022 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0034%20-%202022%20Ukraine%20Electric%20Power%20Attack.md) — During the [2022 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0034), [Sandworm Team](https://attack.mitre.org/groups/G0034) utilizes a Visual Basic script `lun.vbs` to execute `n.bat` which then executed the MicroSCADA `scilc.exe` command.(Citation: Mandiant-Sandworm-Ukraine-2022) [Mandiant-Sandworm-Ukraine-2022](https://www.mandiant.com/resources/blog/sandworm-disrupts-power-ukraine-operational-technology)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has embedded a macro within spearphishing attachments that has been made up of both a VBScript and a PowerShell script.(Citation: Robert Falcone, Bryan Lee May 2016) [Robert Falcone, Bryan Lee May 2016](https://unit42.paloaltonetworks.com/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)

## Detection strategies

- [DET0932 - Behavioral Detection of Visual Basic Execution in ICS](../../../../Defenses/Detection%20Strategies/DET0932%20-%20Behavioral%20Detection%20of%20Visual%20Basic%20Execution%20in%20ICS.md)

## Sources

- [VB .NET Mar 2020](https://devblogs.microsoft.com/vbteam/visual-basic-support-planned-for-net-5-0/)
- [Microsoft VBScript](https://docs.microsoft.com/previous-versions//1kw29xwf%28v=vs.85%29)
- [Microsoft VBA](https://docs.microsoft.com/office/vba/api/overview/)
- [VB Microsoft](https://docs.microsoft.com/dotnet/visual-basic/)
- [Wikipedia VBA](https://en.wikipedia.org/wiki/Visual_Basic_for_Applications)
