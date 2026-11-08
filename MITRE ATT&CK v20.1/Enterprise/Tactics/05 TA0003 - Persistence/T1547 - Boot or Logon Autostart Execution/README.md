# T1547 - Boot or Logon Autostart Execution

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may configure system settings to automatically execute a program during system boot or logon to maintain persistence or gain higher-level privileges on compromised systems. Operating systems may have mechanisms for automatically running a program on system boot or account logon.(Citation: Microsoft Run Key)(Citation: MSDN Authentication Packages)(Citation: Microsoft TimeProvider)(Citation: Cylance Reg Persistence Sept 2013)(Citation: Linux Kernel Programming) These mechanisms may include automatically executing programs that are placed in specially designated directories or are referenced by repositories that store configuration information, such as the Windows Registry. An adversary may achieve the same goal by modifying or extending features of the kernel.

Since some boot or logon autostart programs run with higher privileges, an adversary may leverage these to elevate privileges.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547)

**Tactics**  [Persistence](../README.md), [Privilege Escalation](../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1547.014 - Active Setup](T1547.014%20-%20Active%20Setup/README.md)
- [T1547.002 - Authentication Package](T1547.002%20-%20Authentication%20Package/README.md)
- [T1547.006 - Kernel Modules and Extensions](T1547.006%20-%20Kernel%20Modules%20and%20Extensions/README.md)
- [T1547.015 - Login Items](T1547.015%20-%20Login%20Items/README.md)
- [T1547.008 - LSASS Driver](T1547.008%20-%20LSASS%20Driver/README.md)
- [T1547.010 - Port Monitors](T1547.010%20-%20Port%20Monitors/README.md)
- [T1547.012 - Print Processors](T1547.012%20-%20Print%20Processors/README.md)
- [T1547.007 - Re-opened Applications](T1547.007%20-%20Re-opened%20Applications/README.md)
- [T1547.001 - Registry Run Keys / Startup Folder](T1547.001%20-%20Registry%20Run%20Keys%20-%20Startup%20Folder/README.md)
- [T1547.005 - Security Support Provider](T1547.005%20-%20Security%20Support%20Provider/README.md)
- [T1547.009 - Shortcut Modification](T1547.009%20-%20Shortcut%20Modification/README.md)
- [T1547.003 - Time Providers](T1547.003%20-%20Time%20Providers/README.md)
- [T1547.004 - Winlogon Helper DLL](T1547.004%20-%20Winlogon%20Helper%20DLL/README.md)
- [T1547.013 - XDG Autostart Entries](T1547.013%20-%20XDG%20Autostart%20Entries/README.md)

## Procedure examples

- [G1044 - APT42](../../../Threat%20Intelligence/Groups/G1044%20-%20APT42.md) — [APT42](https://attack.mitre.org/groups/G1044) has modified the Registry to maintain persistence.(Citation: Mandiant APT42-charms) [Mandiant APT42-charms](https://services.google.com/fh/files/misc/apt42-crooked-charms-cons-and-compromises.pdf)
- [S0651 - BoxCaon](../../../Threat%20Intelligence/Software/Malware/S0651%20-%20BoxCaon.md) — [BoxCaon](https://attack.mitre.org/software/S0651) established persistence by setting the <code>HKEY_CURRENT_USER\Software\Microsoft\Windows NT\CurrentVersion\Windows\load</code> registry key to point to its executable.(Citation: Checkpoint IndigoZebra July 2021) [Checkpoint IndigoZebra July 2021](https://research.checkpoint.com/2021/indigozebra-apt-continues-to-attack-central-asia-with-evolving-tools/)
- [S0567 - Dtrack](../../../Threat%20Intelligence/Software/Malware/S0567%20-%20Dtrack.md) — [Dtrack](https://attack.mitre.org/software/S0567)’s RAT makes a persistent target file with auto execution on the host start.(Citation: Securelist Dtrack) [Securelist Dtrack](https://securelist.com/my-name-is-dtrack/93338/)
- [S0084 - Mis-Type](../../../Threat%20Intelligence/Software/Malware/S0084%20-%20Mis-Type.md) — [Mis-Type](https://attack.mitre.org/software/S0084) has created registry keys for persistence, including `HKCU\Software\bkfouerioyou`, `HKLM\SOFTWARE\Microsoft\Active Setup\Installed Components\{6afa8072-b2b1-31a8-b5c1-{Unique Identifier}`, and `HKLM\SOFTWARE\Microsoft\Active Setup\Installed Components\{3BF41072-B2B1-31A8-B5C1-{Unique Identifier}`.(Citation: Cylance Dust Storm) [Cylance Dust Storm](https://s7d2.scene7.com/is/content/cylance/prod/cylance-web/en-us/resources/knowledge-center/resource-library/reports/Op_Dust_Storm_Report.pdf)
- [S0083 - Misdat](../../../Threat%20Intelligence/Software/Malware/S0083%20-%20Misdat.md) — [Misdat](https://attack.mitre.org/software/S0083) has created registry keys for persistence, including `HKCU\Software\dnimtsoleht\StubPath`, `HKCU\Software\snimtsOleht\StubPath`, `HKCU\Software\Backtsaleht\StubPath`, `HKLM\SOFTWARE\Microsoft\Active Setup\Installed. Components\{3bf41072-b2b1-21c8-b5c1-bd56d32fbda7}`, and `HKLM\SOFTWARE\Microsoft\Active Setup\Installed Components\{3ef41072-a2f1-21c8-c5c1-70c2c3bc7905}`.(Citation: Cylance Dust Storm) [Cylance Dust Storm](https://s7d2.scene7.com/is/content/cylance/prod/cylance-web/en-us/resources/knowledge-center/resource-library/reports/Op_Dust_Storm_Report.pdf)
- [S0653 - xCaon](../../../Threat%20Intelligence/Software/Malware/S0653%20-%20xCaon.md) — [xCaon](https://attack.mitre.org/software/S0653) has added persistence via the Registry key <code>HKEY_CURRENT_USER\Software\Microsoft\Windows NT\CurrentVersion\Windows\load</code> which causes the malware to run each time any user logs in.(Citation: Checkpoint IndigoZebra July 2021) [Checkpoint IndigoZebra July 2021](https://research.checkpoint.com/2021/indigozebra-apt-continues-to-attack-central-asia-with-evolving-tools/)

## Detection strategies

- [DET0274 - Boot or Logon Autostart Execution Detection Strategy](../../../Defenses/Detection%20Strategies/DET0274%20-%20Boot%20or%20Logon%20Autostart%20Execution%20Detection%20Strategy.md)

## Sources

- [Cylance Reg Persistence Sept 2013](https://web.archive.org/web/20160214140250/http://blog.cylance.com/windows-registry-persistence-part-2-the-run-keys-and-search-order)
- [MSDN Authentication Packages](https://msdn.microsoft.com/library/windows/desktop/aa374733.aspx)
- [Microsoft Run Key](https://learn.microsoft.com/en-us/windows/win32/setupapi/run-and-runonce-registry-keys)
- [Microsoft TimeProvider](https://msdn.microsoft.com/library/windows/desktop/ms725475.aspx)
- [Linux Kernel Programming](https://www.tldp.org/LDP/lkmpg/2.4/lkmpg.pdf)
- [TechNet Autoruns](https://technet.microsoft.com/en-us/sysinternals/bb963902)
