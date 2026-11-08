# T1021.006 - Windows Remote Management

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1021 - Remote Services](../README.md)

Adversaries may use [Valid Accounts](https://attack.mitre.org/techniques/T1078) to interact with remote systems using Windows Remote Management (WinRM). The adversary may then perform actions as the logged-on user.

WinRM is the name of both a Windows service and a protocol that allows a user to interact with a remote system (e.g., run an executable, modify the Registry, modify services).(Citation: Microsoft WinRM) It may be called with the `winrm` command or by any number of programs such as PowerShell.(Citation: Jacobsen 2014) WinRM  can be used as a method of remotely interacting with [Windows Management Instrumentation](https://attack.mitre.org/techniques/T1047).(Citation: MSDN WMI)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1021/006)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1063 - Brute Ratel C4](../../../../Threat%20Intelligence/Software/Tools/S1063%20-%20Brute%20Ratel%20C4.md) — [Brute Ratel C4](https://attack.mitre.org/software/S1063) can use WinRM for pivoting.(Citation: Palo Alto Brute Ratel July 2022) [Palo Alto Brute Ratel July 2022](https://unit42.paloaltonetworks.com/brute-ratel-c4-tool/)
- [G0114 - Chimera](../../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has used WinRM for lateral movement.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can use <code>WinRM</code> to execute a payload on a remote host.(Citation: cobaltstrike manual)(Citation: Cobalt Strike Manual 4.3 November 2020) [cobaltstrike manual](https://web.archive.org/web/20210825130434/https://cobaltstrike.com/downloads/csmanual38.pdf) · [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf)
- [G1016 - FIN13](../../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has leveraged `WMI` to move laterally within a compromised network via application servers and SQL servers.(Citation: Sygnia Elephant Beetle Jan 2022) [Sygnia Elephant Beetle Jan 2022](https://web.archive.org/web/20220105132433/https://f.hubspotusercontent30.net/hubfs/8776530/Sygnia-%20Elephant%20Beetle_Jan2022.pdf)
- [C0048 - Operation MidnightEclipse](../../../../Threat%20Intelligence/Campaigns/C0048%20-%20Operation%20MidnightEclipse.md) — During [Operation MidnightEclipse](https://attack.mitre.org/campaigns/C0048), threat actors used WinRM to move laterally in targeted networks.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
- [S0692 - SILENTTRINITY](../../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) tracks `TrustedHosts` and can move laterally to these targets via WinRM.(Citation: GitHub SILENTTRINITY Modules July 2019) [GitHub SILENTTRINITY Modules July 2019](https://github.com/byt3bl33d3r/SILENTTRINITY/tree/master/silenttrinity/core/teamserver/modules/boo)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) used WinRM via PowerShell to execute commands and payloads on remote hosts.(Citation: Symantec RAINDROP January 2021) [Symantec RAINDROP January 2021](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/solarwinds-raindrop-malware)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has utilized the post-exploitation tool known as Evil-WinRM that uses PowerShell over Windows Remote Management (WinRM) for remote code execution.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has used WinRM to enable remote execution.(Citation: SecureWorks BRONZE UNION June 2017) [SecureWorks BRONZE UNION June 2017](https://www.secureworks.com/research/bronze-union)
- [G0102 - Wizard Spider](../../../../Threat%20Intelligence/Groups/G0102%20-%20Wizard%20Spider.md) — [Wizard Spider](https://attack.mitre.org/groups/G0102) has used Window Remote Management to move laterally through a victim network.(Citation: DHS/CISA Ransomware Targeting Healthcare October 2020) [DHS/CISA Ransomware Targeting Healthcare October 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-302a)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable the WinRM service.
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — If the service is necessary, lock down critical enclaves with separate WinRM infrastructure and follow WinRM best practices on use of host firewalls to restrict WinRM access to allow communication only to/from specific devices.(Citation: NSA Spotting) [NSA Spotting](https://massarobi.wordpress.com/wp-content/uploads/2017/03/spotting-the-adversary-with-windows-event-log-monitoring.pdf)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — If the service is necessary, lock down critical enclaves with separate WinRM accounts and permissions.

## Detection strategies

- [DET0477 - Behavioral Detection of WinRM-Based Remote Access](../../../../Defenses/Detection%20Strategies/DET0477%20-%20Behavioral%20Detection%20of%20WinRM-Based%20Remote%20Access.md)

## Sources

- [Medium Detecting Lateral Movement](https://medium.com/threatpunter/detecting-lateral-movement-using-sysmon-and-splunk-318d3be141bc)
- [Jacobsen 2014](https://www.slideshare.net/kieranjacobsen/lateral-movement-with-power-shell-2)
- [MSDN WMI](https://msdn.microsoft.com/en-us/library/aa394582.aspx)
- [Microsoft WinRM](https://learn.microsoft.com/en-us/windows/win32/winrm/portal)
