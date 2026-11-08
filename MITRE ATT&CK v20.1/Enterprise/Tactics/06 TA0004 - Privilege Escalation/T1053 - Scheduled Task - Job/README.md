# T1053 - Scheduled Task/Job

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may abuse task scheduling functionality to facilitate initial or recurring execution of malicious code. Utilities exist within all major operating systems to schedule programs or scripts to be executed at a specified date and time. A task can also be scheduled on a remote system, provided the proper authentication is met (ex: RPC and file and printer sharing in Windows environments). Scheduling a task on a remote system typically may require being a member of an admin or otherwise privileged group on the remote system.(Citation: TechNet Task Scheduler Security)

Adversaries may use task scheduling to execute programs at system startup or on a scheduled basis for persistence. These mechanisms can also be abused to run a process under the context of a specified account (such as one with elevated permissions/privileges). Similar to [System Binary Proxy Execution](https://attack.mitre.org/techniques/T1218), adversaries have also abused task scheduling to potentially mask one-time execution under a trusted system process.(Citation: ProofPoint Serpent)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1053)

**Tactics**  [Execution](../../04%20TA0002%20-%20Execution/README.md), [Persistence](../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../README.md)

**Platforms**  [Containers](../../../Platforms/Containers.md), [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1053.002 - At](T1053.002%20-%20At/README.md)
- [T1053.007 - Container Orchestration Job](T1053.007%20-%20Container%20Orchestration%20Job/README.md)
- [T1053.003 - Cron](T1053.003%20-%20Cron/README.md)
- [T1053.005 - Scheduled Task](T1053.005%20-%20Scheduled%20Task/README.md)
- [T1053.006 - Systemd Timers](T1053.006%20-%20Systemd%20Timers/README.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries set FortiGate scheduled tasks to run the adversary generated CLI scripts weekly.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S0447 - Lokibot](../../../Threat%20Intelligence/Software/Malware/S0447%20-%20Lokibot.md) — [Lokibot](https://attack.mitre.org/software/S0447)'s second stage DLL has set a timer using “timeSetEvent” to schedule its next execution.(Citation: Talos Lokibot Jan 2021) [Talos Lokibot Jan 2021](https://blog.talosintelligence.com/2021/01/a-deep-dive-into-lokibot-infection-chain.html)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Toolkits like the PowerSploit framework contain PowerUp modules that can be used to explore systems for permission weaknesses in scheduled tasks that could be used to escalate privileges. (Citation: Powersploit) [Powersploit](https://github.com/mattifestation/PowerSploit)
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Configure settings for scheduled tasks to force tasks to run under the context of the authenticated account instead of allowing them to run as SYSTEM. The associated Registry key is located at <code>HKLM\SYSTEM\CurrentControlSet\Control\Lsa\SubmitControl</code>. The setting can be configured through GPO: Computer Configuration > [Policies] > Windows Settings > Security Settings > Local Policies > Security Options: Domain Controller: Allow server operators to schedule tasks, set to disabled. (Citation: TechNet Server Operator Scheduled Task) [TechNet Server Operator Scheduled Task](https://technet.microsoft.com/library/jj852168.aspx)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Configure the Increase Scheduling Priority option to only allow the Administrators group the rights to schedule a priority process. This can be can be configured through GPO: Computer Configuration > [Policies] > Windows Settings > Security Settings > Local Policies > User Rights Assignment: Increase scheduling priority. (Citation: TechNet Scheduling Priority) [TechNet Scheduling Priority](https://technet.microsoft.com/library/dn221960.aspx)
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict access by setting directory and file permissions that are not specific to users or privileged accounts.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit privileges of user accounts and remediate Privilege Escalation vectors so only authorized administrators can create scheduled tasks on remote systems.

## Detection strategies

- [DET0094 - Cross-Platform Behavioral Detection of Scheduled Task/Job Abuse](../../../Defenses/Detection%20Strategies/DET0094%20-%20Cross-Platform%20Behavioral%20Detection%20of%20Scheduled%20Task%20-%20Job%20Abuse.md)

## Sources

- [ProofPoint Serpent](https://www.proofpoint.com/us/blog/threat-insight/serpent-no-swiping-new-backdoor-targets-french-entities-unique-attack-chain)
- [TechNet Task Scheduler Security](https://technet.microsoft.com/en-us/library/cc785125.aspx)
