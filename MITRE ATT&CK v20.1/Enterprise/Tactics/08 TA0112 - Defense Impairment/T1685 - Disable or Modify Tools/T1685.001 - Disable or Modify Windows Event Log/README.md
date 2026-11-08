# T1685.001 - Disable or Modify Windows Event Log

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1685 - Disable or Modify Tools](../README.md)

Adversaries may disable or modify the Windows Event Log to limit data that can be leveraged for detections and audits. Windows Event Log records user and system activity such as login attempts and process creation.(Citation: EventLog_Core_Technologies) This data is used by security tools and analysts to generate detections. 

The EventLog service maintains event logs from various system components and applications. By default, the service automatically starts when a system powers on. An audit policy, maintained by the Local Security Policy (secpol.msc), defines which system events the EventLog service logs. Security audit policy settings can be changed by running secpol.msc, then navigating to `Security Settings\Local Policies\Audit Policy` for basic audit policy settings or `Security Settings\Advanced Audit Policy Configuration` for advanced audit policy settings.(Citation: Microsoft Audit Policy)(Citation: Microsoft Adv Security Settings) `auditpol.exe` may also be used to set audit policies.(Citation: Microsoft auditpol)

Adversaries may target system-wide logging or just that of a particular application. For example, the Windows EventLog service may be disabled using the `Set-Service -Name EventLog -Status Stopped` or `sc config eventlog start=disabled` commands (followed by manually stopping the service using `Stop-Service -Name EventLog`). Additionally, the service may be disabled by modifying the "Start" value in `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\EventLog` then restarting the system for the change to take effect.(Citation: Disable_Win_Event_Logging)(Citation: disable_win_evt_logging)

There are several ways to disable the EventLog service via registry key modification. Without Administrator privileges, adversaries may modify the "Start" value in the key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Autologger\EventLog-Security`, then reboot the system to disable the Security EventLog.(Citation: winser19_file_overwrite_bug_twitter) With Administrator privilege, adversaries may modify the same values in `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Autologger\EventLog-System` and `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\WMI\Autologger\EventLog-Application` to disable the entire EventLog.

Additionally, adversaries may use `auditpol` and its sub-commands in a command prompt to disable auditing or clear the audit policy. To enable or disable a specified setting or audit category, adversaries may use the `/success` or `/failure` parameters. For example, `auditpol /set /category:"Account Logon" /success:disable /failure:disable` turns off auditing for the Account Logon category.(Citation: auditpol.exe_STRONTIC) To clear the audit policy, adversaries may run the following lines: `auditpol /clear /y` or `auditpol /remove /allusers`.(Citation: T1562.002_redcanaryco)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1685/001)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Consider periodic review of <code>auditpol</code> settings for Administrator accounts and perform dynamic baselining on SIEM(s) to investigate potential malicious activity. Also ensure that the EventLog service and its threads are properly running.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure proper process and file permissions are in place to prevent adversaries from disabling or interfering with logging or deleting or modifying .evtx logging files. Ensure .evtx files, which are located at <code>C:\Windows\system32\Winevt\Logs</code>(Citation: win_xml_evt_log), have the proper file permissions for limited, legitimate access and audit policies for detection. [win_xml_evt_log](https://forensicswiki.xyz/wiki/index.php?title=Windows_XML_Event_Log_%28EVTX%29)
- [M1024 - Restrict Registry Permissions](../../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Ensure proper Registry permissions are in place to prevent adversaries from disabling or interfering logging. The addition of the MiniNT registry key disables Event Viewer.(Citation: def_ev_win_event_logging) [def_ev_win_event_logging](https://www.hackingarticles.in/defense-evasion-windows-event-logging-t1562-002/)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure proper user permissions are in place to prevent adversaries from disabling or interfering with logging.

## Detection strategies

- [DET0187 - Detect Disabled Windows Event Log](../../../../Defenses/Detection%20Strategies/DET0187%20-%20Detect%20Disabled%20Windows%20Event%20Log.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) disabled event logging on compromised systems.(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [C0038 - HomeLand Justice](../../../../Threat%20Intelligence/Campaigns/C0038%20-%20HomeLand%20Justice.md) — During [HomeLand Justice](https://attack.mitre.org/campaigns/C0038), threat actors deleted Windows events and application logs.(Citation: Microsoft Albanian Government Attacks September 2022) [Microsoft Albanian Government Attacks September 2022](https://www.microsoft.com/en-us/security/blog/2022/09/08/microsoft-investigates-iranian-attacks-against-the-albanian-government/)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has executed scripts to disable the event log service.(Citation: DFIR Phosphorus November 2021) [DFIR Phosphorus November 2021](https://thedfirreport.com/2021/11/15/exchange-exploit-leads-to-domain-wide-ransomware/)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016), used `AUDITPOL` to prevent the collection of audit logs.(Citation: Microsoft Deep Dive Solorigate January 2021) [Microsoft Deep Dive Solorigate January 2021](https://www.microsoft.com/security/blog/2021/01/20/deep-dive-into-the-solorigate-second-stage-activation-from-sunburst-to-teardrop-and-raindrop/)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) has used appcmd.exe to disable logging on a victim server.(Citation: SecureWorks BRONZE UNION June 2017) [SecureWorks BRONZE UNION June 2017](https://www.secureworks.com/research/bronze-union)
- [S0645 - Wevtutil](../../../../Threat%20Intelligence/Software/Tools/S0645%20-%20Wevtutil.md) — [Wevtutil](https://attack.mitre.org/software/S0645) can be used to disable specific event logs on the system.(Citation: Wevtutil Microsoft Documentation) [Wevtutil Microsoft Documentation](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/wevtutil)

## Sources

- [Disable_Win_Event_Logging](https://dmcxblue.gitbook.io/red-team-notes-2-0/red-team-techniques/defense-evasion/t1562-impair-defenses/disable-windows-event-logging)
- [EventLog_Core_Technologies](https://www.coretechnologies.com/blog/windows-services/eventlog/)
- [disable_win_evt_logging](https://ptylu.github.io/content/report/report.html?report=25)
- [Microsoft Audit Policy](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/security-policy-settings/audit-policy)
- [Microsoft Adv Security Settings](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/auditing/advanced-security-audit-policy-settings)
- [Microsoft auditpol](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/auditpol)
- [winser19_file_overwrite_bug_twitter](https://web.archive.org/web/20211107115646/https://twitter.com/klinix5/status/1457316029114327040)
- [T1562.002_redcanaryco](https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1562.002/T1562.002.md)
- [auditpol.exe_STRONTIC](https://strontic.github.io/xcyclopedia/library/auditpol.exe-214E0EA1F7F7C27C82D23F183F9D23F1.html)
