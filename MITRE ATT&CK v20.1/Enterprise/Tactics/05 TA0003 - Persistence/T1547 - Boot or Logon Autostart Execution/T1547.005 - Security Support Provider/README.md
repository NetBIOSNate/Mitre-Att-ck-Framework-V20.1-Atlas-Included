# T1547.005 - Security Support Provider

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may abuse security support providers (SSPs) to execute DLLs when the system boots. Windows SSP DLLs are loaded into the Local Security Authority (LSA) process at system start. Once loaded into the LSA, SSP DLLs have access to encrypted and plaintext passwords that are stored in Windows, such as any logged-on user's Domain password or smart card PINs.

The SSP configuration is stored in two Registry keys: <code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa\Security Packages</code> and <code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa\OSConfig\Security Packages</code>. An adversary may modify these Registry keys to add new SSPs, which will be loaded the next time the system boots, or when the AddSecurityPackage Windows API function is called.(Citation: Graeber 2014)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/005)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0542 - Registry and LSASS Monitoring for Security Support Provider Abuse](../../../../Defenses/Detection%20Strategies/DET0542%20-%20Registry%20and%20LSASS%20Monitoring%20for%20Security%20Support%20Provider%20Abuse.md)

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can enumerate Security Support Providers (SSPs) as well as utilize [PowerSploit](https://attack.mitre.org/software/S0194)'s <code>Install-SSP</code> and <code>Invoke-Mimikatz</code> to install malicious SSPs and log authentication events.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0002 - Mimikatz](../../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — The [Mimikatz](https://attack.mitre.org/software/S0002) credential dumper contains an implementation of an SSP.(Citation: Deply Mimikatz) [Deply Mimikatz](https://github.com/gentilkiwi/mimikatz)
- [S0194 - PowerSploit](../../../../Threat%20Intelligence/Software/Tools/S0194%20-%20PowerSploit.md) — [PowerSploit](https://attack.mitre.org/software/S0194)'s <code>Install-SSP</code> Persistence module can be used to establish by installing a SSP DLL.(Citation: GitHub PowerSploit May 2012)(Citation: PowerSploit Documentation) [GitHub PowerSploit May 2012](https://github.com/PowerShellMafia/PowerSploit) · [PowerSploit Documentation](http://powersploit.readthedocs.io)

## Mitigations

- [M1025 - Privileged Process Integrity](../../../../Defenses/Mitigations/M1025%20-%20Privileged%20Process%20Integrity.md) — Windows 8.1, Windows Server 2012 R2, and later versions may make LSA run as a Protected Process Light (PPL) by setting the Registry key <code>HKLM\\SYSTEM\\CurrentControlSet\\Control\\Lsa\\RunAsPPL</code>, which requires all SSP DLLs to be signed by Microsoft. (Citation: Graeber 2014) (Citation: Microsoft Configure LSA) [Graeber 2014](http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html) · [Microsoft Configure LSA](https://technet.microsoft.com/en-us/library/dn408187.aspx)

## Sources

- [Graeber 2014](http://docplayer.net/20839173-Analysis-of-malicious-security-support-provider-dlls.html)
- [Microsoft Configure LSA](https://technet.microsoft.com/en-us/library/dn408187.aspx)
