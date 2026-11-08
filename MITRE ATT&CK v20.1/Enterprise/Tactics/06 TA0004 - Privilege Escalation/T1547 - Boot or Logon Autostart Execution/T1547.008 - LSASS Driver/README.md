# T1547.008 - LSASS Driver

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may modify or add LSASS drivers to obtain persistence on compromised systems. The Windows security subsystem is a set of components that manage and enforce the security policy for a computer or domain. The Local Security Authority (LSA) is the main component responsible for local security policy and user authentication. The LSA includes multiple dynamic link libraries (DLLs) associated with various other security functions, all of which run in the context of the LSA Subsystem Service (LSASS) lsass.exe process.(Citation: Microsoft Security Subsystem)

Adversaries may target LSASS drivers to obtain persistence. By either replacing or adding illegitimate drivers (e.g., [Hijack Execution Flow](https://attack.mitre.org/techniques/T1574)), an adversary can use LSA operations to continuously execute malicious payloads.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/008)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0208 - Pasam](../../../../Threat%20Intelligence/Software/Malware/S0208%20-%20Pasam.md) — [Pasam](https://attack.mitre.org/software/S0208) establishes by infecting the Security Accounts Manager (SAM) DLL to load a malicious DLL dropped to disk.(Citation: Symantec Pasam May 2012) [Symantec Pasam May 2012](https://www.symantec.com/security_response/writeup.jsp?docid=2012-050412-4128-99)
- [S0176 - Wingbird](../../../../Threat%20Intelligence/Software/Malware/S0176%20-%20Wingbird.md) — [Wingbird](https://attack.mitre.org/software/S0176) drops a malicious file (sspisrv.dll) alongside a copy of lsass.exe, which is used to register a service that loads sspisrv.dll as a driver. The payload of the malicious driver (located in its entry-point function) is executed when loaded by lsass.exe before the spoofed service becomes unstable and crashes.(Citation: Microsoft SIR Vol 21)(Citation: Microsoft Wingbird Nov 2017) [Microsoft SIR Vol 21](http://download.microsoft.com/download/E/B/0/EB0F50CC-989C-4B66-B7F6-68CD3DC90DE3/Microsoft_Security_Intelligence_Report_Volume_21_English.pdf) · [Microsoft Wingbird Nov 2017](https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=Backdoor:Win32/Wingbird.A!dha)

## Mitigations

- [M1043 - Credential Access Protection](../../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — On Windows 10 and Server 2016, enable Windows Defender Credential Guard (Citation: Microsoft Enable Cred Guard April 2017) to run lsass.exe in an isolated virtualized environment without any device drivers. (Citation: Microsoft Credential Guard April 2017) [Microsoft Enable Cred Guard April 2017](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard-manage) · [Microsoft Credential Guard April 2017](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard-how-it-works)
- [M1025 - Privileged Process Integrity](../../../../Defenses/Mitigations/M1025%20-%20Privileged%20Process%20Integrity.md) — On Windows 8.1 and Server 2012 R2, enable LSA Protection by setting the Registry key <code>HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Lsa\\RunAsPPL</code> to <code>dword:00000001</code>. (Citation: Microsoft LSA Protection Mar 2014) LSA Protection ensures that LSA plug-ins and drivers are only loaded if they are digitally signed with a Microsoft signature and adhere to the Microsoft Security Development Lifecycle (SDL) process guidance. [Microsoft LSA Protection Mar 2014](https://technet.microsoft.com/library/dn408187.aspx)
- [M1044 - Restrict Library Loading](../../../../Defenses/Mitigations/M1044%20-%20Restrict%20Library%20Loading.md) — Ensure safe DLL search mode is enabled <code>HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Control\\Session Manager\\SafeDllSearchMode</code> to mitigate risk that lsass.exe loads a malicious code library. (Citation: Microsoft DLL Security) [Microsoft DLL Security](https://msdn.microsoft.com/library/windows/desktop/ff919712.aspx)

## Detection strategies

- [DET0225 - Detect unauthorized LSASS driver persistence via LSA plugin abuse (Windows)](../../../../Defenses/Detection%20Strategies/DET0225%20-%20Detect%20unauthorized%20LSASS%20driver%20persistence%20via%20LSA%20plugin%20abuse%20%28Windows%29.md)

## Sources

- [Microsoft LSA Protection Mar 2014](https://technet.microsoft.com/library/dn408187.aspx)
- [Microsoft DLL Security](https://msdn.microsoft.com/library/windows/desktop/ff919712.aspx)
- [Microsoft Security Subsystem](https://technet.microsoft.com/library/cc961760.aspx)
- [TechNet Autoruns](https://technet.microsoft.com/en-us/sysinternals/bb963902)
