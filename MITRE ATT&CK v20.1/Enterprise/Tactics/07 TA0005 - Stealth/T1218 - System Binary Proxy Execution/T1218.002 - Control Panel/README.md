# T1218.002 - Control Panel

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse control.exe to proxy execution of malicious payloads. The Windows Control Panel process binary (control.exe) handles execution of Control Panel items, which are utilities that allow users to view and adjust computer settings.

Control Panel items are registered executable (.exe) or Control Panel (.cpl) files; the latter are actually renamed dynamic-link library (.dll) files that export a <code>CPlApplet</code> function.(Citation: Microsoft Implementing CPL)(Citation: TrendMicro CPL Malware Jan 2014) For ease of use, Control Panel items typically include graphical menus available to users after being registered and loaded into the Control Panel.(Citation: Microsoft Implementing CPL) Control Panel items can be executed directly from the command line, programmatically via an application programming interface (API) call, or by simply double-clicking the file.(Citation: Microsoft Implementing CPL)(Citation: TrendMicro CPL Malware Jan 2014)(Citation: TrendMicro CPL Malware Dec 2013)

Malicious Control Panel items can be delivered via [Phishing](https://attack.mitre.org/techniques/T1566) campaigns(Citation: TrendMicro CPL Malware Jan 2014)(Citation: TrendMicro CPL Malware Dec 2013) or executed as part of multi-stage malware.(Citation: Palo Alto Reaver Nov 2017) Control Panel items, specifically CPL files, may also bypass application and/or file extension allow lists.

Adversaries may also rename malicious DLL files (.dll) with Control Panel file extensions (.cpl) and register them to <code>HKCU\Software\Microsoft\Windows\CurrentVersion\Control Panel\Cpls</code>. Even when these registered DLLs do not comply with the CPL file specification and do not export <code>CPlApplet</code> functions, they are loaded and executed through its <code>DllEntryPoint</code> when Control Panel is executed. CPL files not exporting <code>CPlApplet</code> are not directly executable.(Citation: ESET InvisiMole June 2020)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/002)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Identify and block potentially malicious and unknown .cpl files by using application control (Citation: Beechey 2010) tools, like Windows Defender Application Control(Citation: Microsoft Windows Defender Application Control), AppLocker, (Citation: Windows Commands JPCERT) (Citation: NSA MS AppLocker) or Software Restriction Policies (Citation: Corio 2008) where appropriate. (Citation: TechNet Applocker vs SRP) [Beechey 2010](http://www.sans.org/reading-room/whitepapers/application/application-whitelisting-panacea-propaganda-33599) · [Corio 2008](https://learn.microsoft.com/en-us/previous-versions/technet-magazine/cc510322%28v=msdn.10%29) · [Microsoft Windows Defender Application Control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) · [TechNet Applocker vs SRP](https://technet.microsoft.com/en-us/library/ee791851.aspx) · [NSA MS AppLocker](https://apps.nsa.gov/iaarchive/library/ia-guidance/tech-briefs/application-whitelisting-using-microsoft-applocker.cfm) · [Windows Commands JPCERT](https://blogs.jpcert.or.jp/en/2016/01/windows-commands-abused-by-attackers.html)
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict storage and execution of Control Panel items to protected directories, such as <code>C:\Windows</code>, rather than user directories.

## Procedure examples

- [S0260 - InvisiMole](../../../../Threat%20Intelligence/Software/Malware/S0260%20-%20InvisiMole.md) — [InvisiMole](https://attack.mitre.org/software/S0260) can register itself for execution and persistence via the Control Panel.(Citation: ESET InvisiMole June 2020) [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)
- [S0172 - Reaver](../../../../Threat%20Intelligence/Software/Malware/S0172%20-%20Reaver.md) — [Reaver](https://attack.mitre.org/software/S0172) drops and executes a malicious CPL file as its payload.(Citation: Palo Alto Reaver Nov 2017) [Palo Alto Reaver Nov 2017](https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/)

## Detection strategies

- [DET0194 - Detection of Malicious Control Panel Item Execution via control.exe or Rundll32](../../../../Defenses/Detection%20Strategies/DET0194%20-%20Detection%20of%20Malicious%20Control%20Panel%20Item%20Execution%20via%20control.exe%20or%20Rundll32.md)

## Sources

- [TrendMicro CPL Malware Dec 2013](https://blog.trendmicro.com/trendlabs-security-intelligence/control-panel-files-used-as-malicious-attachments/)
- [Palo Alto Reaver Nov 2017](https://researchcenter.paloaltonetworks.com/2017/11/unit42-new-malware-with-ties-to-sunorcal-discovered/)
- [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)
- [Microsoft Implementing CPL](https://msdn.microsoft.com/library/windows/desktop/cc144185.aspx)
- [TrendMicro CPL Malware Jan 2014](https://www.trendmicro.de/cloud-content/us/pdfs/security-intelligence/white-papers/wp-cpl-malware.pdf)
