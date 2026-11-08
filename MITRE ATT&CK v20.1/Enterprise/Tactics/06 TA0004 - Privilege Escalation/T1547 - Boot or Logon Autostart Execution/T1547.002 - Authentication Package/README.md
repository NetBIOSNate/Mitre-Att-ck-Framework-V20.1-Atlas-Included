# T1547.002 - Authentication Package

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may abuse authentication packages to execute DLLs when the system boots. Windows authentication package DLLs are loaded by the Local Security Authority (LSA) process at system start. They provide support for multiple logon processes and multiple security protocols to the operating system.(Citation: MSDN Authentication Packages)

Adversaries can use the autostart mechanism provided by LSA authentication packages for persistence by placing a reference to a binary in the Windows Registry location <code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa\</code> with the key value of <code>"Authentication Packages"=&lt;target binary&gt;</code>. The binary will then be executed by the system when the authentication packages are loaded.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/002)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1025 - Privileged Process Integrity](../../../../Defenses/Mitigations/M1025%20-%20Privileged%20Process%20Integrity.md) — Windows 8.1, Windows Server 2012 R2, and later versions, may make LSA run as a Protected Process Light (PPL) by setting the Registry key <code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa\RunAsPPL</code>, which requires all DLLs loaded by LSA to be signed by Microsoft. (Citation: Graeber 2014) (Citation: Microsoft Configure LSA) [Graeber 2014](http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html) · [Microsoft Configure LSA](https://technet.microsoft.com/en-us/library/dn408187.aspx)

## Detection strategies

- [DET0207 - Detect LSA Authentication Package Persistence via Registry and LSASS DLL Load](../../../../Defenses/Detection%20Strategies/DET0207%20-%20Detect%20LSA%20Authentication%20Package%20Persistence%20via%20Registry%20and%20LSASS%20DLL%20Load.md)

## Procedure examples

- [S0143 - Flame](../../../../Threat%20Intelligence/Software/Malware/S0143%20-%20Flame.md) — [Flame](https://attack.mitre.org/software/S0143) can use Windows Authentication Packages for persistence.(Citation: Crysys Skywiper) [Crysys Skywiper](https://www.crysys.hu/publications/files/skywiper.pdf)

## Sources

- [Graeber 2014](http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html)
- [Microsoft Configure LSA](https://technet.microsoft.com/en-us/library/dn408187.aspx)
- [MSDN Authentication Packages](https://msdn.microsoft.com/library/windows/desktop/aa374733.aspx)
