# T1546.013 - PowerShell Profile

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may gain persistence and elevate privileges by executing malicious content triggered by PowerShell profiles. A PowerShell profile  (<code>profile.ps1</code>) is a script that runs when [PowerShell](https://attack.mitre.org/techniques/T1059/001) starts and can be used as a logon script to customize user environments.

[PowerShell](https://attack.mitre.org/techniques/T1059/001) supports several profiles depending on the user or host program. For example, there can be different profiles for [PowerShell](https://attack.mitre.org/techniques/T1059/001) host programs such as the PowerShell console, PowerShell ISE or Visual Studio Code. An administrator can also configure a profile that applies to all users and host programs on the local computer.(Citation: Microsoft About Profiles) 

Adversaries may modify these profiles to include arbitrary commands, functions, modules, and/or [PowerShell](https://attack.mitre.org/techniques/T1059/001) drives to gain persistence. Every time a user opens a [PowerShell](https://attack.mitre.org/techniques/T1059/001) session the modified script will be executed unless the <code>-NoProfile</code> flag is used when it is launched.(Citation: ESET Turla PowerShell May 2019) 

An adversary may also be able to escalate privileges if a script in a PowerShell profile is loaded and executed by an account with higher privileges, such as a domain administrator.(Citation: Wits End and Shady PowerShell Profiles)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/013)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has used PowerShell profiles to maintain persistence on an infected machine.(Citation: ESET Turla PowerShell May 2019) [ESET Turla PowerShell May 2019](https://www.welivesecurity.com/2019/05/29/turla-powershell-usage/)

## Mitigations

- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Enforce execution of only signed PowerShell scripts. Sign profiles to avoid them from being modified.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Making PowerShell profiles immutable and only changeable by certain administrators will limit the ability for adversaries to easily create user level persistence.
- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Avoid PowerShell profiles if not needed. Use the -No Profile flag with when executing PowerShell scripts remotely to prevent local profiles and scripts from being executed.

## Detection strategies

- [DET0451 - Detection Strategy for PowerShell Profile Persistence via profile.ps1 Modification](../../../../Defenses/Detection%20Strategies/DET0451%20-%20Detection%20Strategy%20for%20PowerShell%20Profile%20Persistence%20via%20profile.ps1%20Modification.md)

## Sources

- [Wits End and Shady PowerShell Profiles](https://witsendandshady.blogspot.com/2019/06/lab-notes-persistence-and-privilege.html)
- [ESET Turla PowerShell May 2019](https://www.welivesecurity.com/2019/05/29/turla-powershell-usage/)
- [Microsoft About Profiles](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6)
