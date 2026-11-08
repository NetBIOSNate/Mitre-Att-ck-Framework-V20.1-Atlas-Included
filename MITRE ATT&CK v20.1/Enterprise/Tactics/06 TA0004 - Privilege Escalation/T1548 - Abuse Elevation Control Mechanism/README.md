# T1548 - Abuse Elevation Control Mechanism

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may circumvent mechanisms designed to control privilege elevation to gain higher-level permissions. Most modern systems contain native elevation control mechanisms that are intended to limit privileges that a user can perform on a machine. Authorization has to be granted to specific users in order to perform tasks that can be considered of higher risk.(Citation: TechNet How UAC Works)(Citation: sudo man page 2018) An adversary can perform several methods to take advantage of built-in control mechanisms in order to escalate privileges on a system.(Citation: OSX Keydnap malware)(Citation: Fortinet Fareit)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1548)

**Tactics**  [Privilege Escalation](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md), [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md)

## Sub-techniques

- [T1548.002 - Bypass User Account Control](T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1548.004 - Elevated Execution with Prompt](T1548.004%20-%20Elevated%20Execution%20with%20Prompt/README.md)
- [T1548.001 - Setuid and Setgid](T1548.001%20-%20Setuid%20and%20Setgid/README.md)
- [T1548.003 - Sudo and Sudo Caching](T1548.003%20-%20Sudo%20and%20Sudo%20Caching/README.md)
- [T1548.006 - TCC Manipulation](T1548.006%20-%20TCC%20Manipulation/README.md)
- [T1548.005 - Temporary Elevated Cloud Access](T1548.005%20-%20Temporary%20Elevated%20Cloud%20Access/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Check for common UAC bypass weaknesses on Windows systems to be aware of the risk posture and address issues where appropriate.(Citation: Github UACMe) [Github UACMe](https://github.com/hfiref0x/UACME)
- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — System settings can prevent applications from running that haven't been downloaded from legitimate repositories which may help mitigate some of these issues. Not allowing unsigned applications from being run may also mitigate some risk.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Applications with known vulnerabilities or known shell escapes should not have the setuid or setgid bits set to reduce potential damage if an application is compromised. Additionally, the number of programs with setuid or setgid bits set should be minimized across a system. Ensuring that the sudo tty_tickets setting is enabled will prevent this leakage across tty sessions.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Remove users from the local administrator group on systems. By requiring a password, even if an adversary can get terminal access, they must know the password to run anything in the sudoers file. Setting the timestamp_timeout to 0 will require the user to input their password every time sudo is executed.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — The sudoers file should be strictly edited such that passwords are always required and that users can't spawn risky processes as users with higher privilege.
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Perform regular software updates to mitigate exploitation risk.
- [M1052 - User Account Control](../../../Defenses/Mitigations/M1052%20-%20User%20Account%20Control.md) — Although UAC bypass techniques exist, it is still prudent to use the highest enforcement level for UAC when possible and mitigate bypass opportunities that exist with techniques such as [DLL](https://attack.mitre.org/techniques/T1574/001).
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit the privileges of cloud accounts to assume, create, or impersonate additional roles, policies, and permissions to only those required. Where just-in-time access is enabled, consider requiring manual approval for temporary elevation of privileges.

## Procedure examples

- [S1130 - Raspberry Robin](../../../Threat%20Intelligence/Software/Malware/S1130%20-%20Raspberry%20Robin.md) — [Raspberry Robin](https://attack.mitre.org/software/S1130) implements a variation of the <code>ucmDccwCOMMethod</code> technique abusing the Windows AutoElevate backdoor to bypass UAC while elevating privileges.(Citation: TrendMicro RaspberryRobin 2022) [TrendMicro RaspberryRobin 2022](https://www.trendmicro.com/en_us/research/22/l/raspberry-robin-malware-targets-telecom-governments.html)
- [G1048 - UNC3886](../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has used vSphere Installation Bundles (VIBs) that contained modified descriptor XML files with the `acceptance-level` set to `partner` which allowed for privilege escalation.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Detection strategies

- [DET0345 - Detection Strategy for Abuse Elevation Control Mechanism (T1548)](../../../Defenses/Detection%20Strategies/DET0345%20-%20Detection%20Strategy%20for%20Abuse%20Elevation%20Control%20Mechanism%20%28T1548%29.md)

## Sources

- [TechNet How UAC Works](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/how-user-account-control-works)
- [OSX Keydnap malware](https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/)
- [Fortinet Fareit](https://blog.fortinet.com/2016/12/16/malicious-macro-bypasses-uac-to-elevate-privilege-for-fareit-malware)
- [sudo man page 2018](https://www.sudo.ws/)
