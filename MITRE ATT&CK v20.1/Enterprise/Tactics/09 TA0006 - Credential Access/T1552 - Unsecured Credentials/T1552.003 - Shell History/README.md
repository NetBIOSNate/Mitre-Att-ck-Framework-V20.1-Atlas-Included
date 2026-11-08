# T1552.003 - Shell History

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1552 - Unsecured Credentials](../README.md)

Adversaries may search the command history on compromised systems for insecurely stored credentials.

On Linux and macOS systems, shells such as Bash and Zsh keep track of the commands users type on the command-line with the "history" utility. Once a user logs out, the history is flushed to the user's history file. For each user, this file resides at the same location: for example, `~/.bash_history` or `~/.zsh_history`. Typically, these files keep track of the user's last 1000 commands.

On Windows, PowerShell has both a command history that is wiped after the session ends, and one that contains commands used in all sessions and is persistent. The default location for persistent history can be found in `%userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt`, but command history can also be accessed with `Get-History`. Command Prompt (CMD) on Windows does not have persistent history.(Citation: Microsoft about_History)(Citation: Medium)

Users often type usernames and passwords on the command-line as parameters to programs, which then get saved to this file when they log out. Adversaries can abuse this by looking through the file for potential credentials.(Citation: External to DA, the OS X Way)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552/003)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary utilized Claude Code to gather data within bash histories.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has gathered data and credentials stored in Shell History.(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [S9045 - BACKUPOSINT v9.0 APEX PREDATOR](../../../../Threat%20Intelligence/Software/Malware/S9045%20-%20BACKUPOSINT%20v9.0%20APEX%20PREDATOR.md) — [BACKUPOSINT v9.0 APEX PREDATOR](https://attack.mitre.org/software/S9045) has extracted system data to include histories.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [S0599 - Kinsing](../../../../Threat%20Intelligence/Software/Malware/S0599%20-%20Kinsing.md) — [Kinsing](https://attack.mitre.org/software/S0599) has searched <code>bash_history</code> for credentials.(Citation: Aqua Kinsing April 2020) [Aqua Kinsing April 2020](https://blog.aquasec.com/threat-alert-kinsing-malware-container-vulnerability)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can target credentials in shell history on self-hosted runners.(Citation: Aqua Security Blog Trivy Compromise APR 2026) [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know)

## Mitigations

- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — There are multiple methods of preventing a user's command history from being flushed to their .bash_history file, including use of the following commands: <code>set +o history</code> and <code>set -o history</code> to start logging again; <code>unset HISTFILE</code> being added to a user's .bash_rc file; and <code>ln -s /dev/null ~/.bash_history</code> to write commands to <code>/dev/null</code> instead. In Zsh, `fc -p` can be used to create a private history session. However, previous history will be unavailable to the user until the session ends. Using `unset HISTFILE` and writing commands to `/dev/null` can also be used, similarly to Bash. In PowerShell, users can utilize `Set-PSReadLineOption` to modify how commands are saved into history. Setting `-HistorySaveStyle SaveNothing` prevents command history from being saved onto the file. Note that setting it from `SaveNothing` to `SaveIncrementally` in the same session will cause all commands from that session to be saved. Alternatively, `-AddToHistoryHandler` can be used to filter certain commands from being saved into the history file.

## Detection strategies

- [DET0385 - Detect Access and Parsing of .bash_history Files for Credential Harvesting](../../../../Defenses/Detection%20Strategies/DET0385%20-%20Detect%20Access%20and%20Parsing%20of%20.bash_history%20Files%20for%20Credential%20Harvesting.md)

## Sources

- [External to DA, the OS X Way](https://www.slideshare.net/slideshow/external-to-da-the-os-x-way/62021418)
- [Medium](https://michaelkoczwara.medium.com/windows-privilege-escalation-dbb908cce8d4)
- [Microsoft about_History](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-7.5)
