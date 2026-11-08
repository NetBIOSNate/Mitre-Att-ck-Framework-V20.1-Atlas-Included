# T1070.003 - Clear Command History

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1070 - Indicator Removal](../README.md)

In addition to clearing system logs, an adversary may clear the command history of a compromised account to conceal the actions undertaken during an intrusion. Various command interpreters keep track of the commands users type in their terminal so that users can retrace what they've done.

On Linux and macOS, these command histories can be accessed in a few different ways. While logged in, this command history is tracked in a file pointed to by the environment variable <code>HISTFILE</code>. When a user logs off a system, this information is flushed to a file in the user's home directory called <code>~/.bash_history</code>. The benefit of this is that it allows users to go back to commands they've used before in different sessions. Adversaries may delete their commands from these logs by manually clearing the history (<code>history -c</code>) or deleting the bash history file <code>rm ~/.bash_history</code>.  

Adversaries may also leverage a [Network Device CLI](https://attack.mitre.org/techniques/T1059/008) on network devices to clear command history data (<code>clear logging</code> and/or <code>clear history</code>).(Citation: US-CERT-TA18-106A) On ESXi servers, command history may be manually removed from the `/var/log/shell.log` file.(Citation: Broadcom ESXi Shell Audit)

On Windows hosts, PowerShell has two different command history providers: the built-in history and the command history managed by the <code>PSReadLine</code> module. The built-in history only tracks the commands used in the current session. This command history is not available to other sessions and is deleted when the session ends.

The <code>PSReadLine</code> command history tracks the commands used in all PowerShell sessions and writes them to a file (<code>$env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt</code> by default). This history file is available to all sessions and contains all past history since the file is not deleted when the session ends.(Citation: Microsoft PowerShell Command History)

Adversaries may run the PowerShell command <code>Clear-History</code> to flush the entire command history from a current PowerShell session. This, however, will not delete/flush the <code>ConsoleHost_history.txt</code> file. Adversaries may also delete the <code>ConsoleHost_history.txt</code> file or edit its contents to hide PowerShell commands they have run.(Citation: Sophos PowerShell command audit)(Citation: Sophos PowerShell Command History Forensics)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1070/003)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has executed scripts to delete the PowerShell command history file.(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) attempted to remove evidence of some of its activity by deleting Bash histories.(Citation: FireEye APT41 Aug 2019) [FireEye APT41 Aug 2019](https://www.mandiant.com/sites/default/files/2022-02/rt-apt41-dual-operation.pdf)
- [G1023 - APT5](../../../../Threat%20Intelligence/Groups/G1023%20-%20APT5.md) — [APT5](https://attack.mitre.org/groups/G1023) has cleared the command history on targeted ESXi servers.(Citation: Mandiant Pulse Secure Update May 2021) [Mandiant Pulse Secure Update May 2021](https://www.mandiant.com/resources/blog/updates-on-chinese-apt-compromising-pulse-secure-vpn-devices)
- [G0143 - Aquatic Panda](../../../../Threat%20Intelligence/Groups/G0143%20-%20Aquatic%20Panda.md) — [Aquatic Panda](https://attack.mitre.org/groups/G0143) cleared command history in Linux environments to remove traces of activity after operations.(Citation: Crowdstrike HuntReport 2022) [Crowdstrike HuntReport 2022](https://go.crowdstrike.com/rs/281-OBQ-266/images/2022OverWatchThreatHuntingReport.pdf)
- [S0601 - Hildegard](../../../../Threat%20Intelligence/Software/Malware/S0601%20-%20Hildegard.md) — [Hildegard](https://attack.mitre.org/software/S0601) has used history -c to clear script shell logs.(Citation: Unit 42 Hildegard Malware) [Unit 42 Hildegard Malware](https://unit42.paloaltonetworks.com/hildegard-malware-teamtnt/)
- [S1203 - J-magic](../../../../Threat%20Intelligence/Software/Malware/S1203%20-%20J-magic.md) — [J-magic](https://attack.mitre.org/software/S1203) can overwrite previously executed command line arguments.(Citation: Lumen J-Magic JAN 2025) [Lumen J-Magic JAN 2025](https://blog.lumen.com/the-j-magic-show-magic-packets-and-where-to-find-them/)
- [S0641 - Kobalos](../../../../Threat%20Intelligence/Software/Malware/S0641%20-%20Kobalos.md) — [Kobalos](https://attack.mitre.org/software/S0641) can remove all command history on compromised hosts.(Citation: ESET Kobalos Feb 2021) [ESET Kobalos Feb 2021](https://www.welivesecurity.com/2021/02/02/kobalos-complex-linux-threat-high-performance-computing-infrastructure/)
- [G0032 - Lazarus Group](../../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) has routinely deleted log files on a compromised router, including automatic log deletion through the use of the logrotate utility.(Citation: Kaspersky ThreatNeedle Feb 2021) [Kaspersky ThreatNeedle Feb 2021](https://securelist.com/lazarus-threatneedle/100803/)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has removed mailbox export requests from compromised Exchange servers.(Citation: DFIR Report APT35 ProxyShell March 2022) [DFIR Report APT35 ProxyShell March 2022](https://thedfirreport.com/2022/03/21/apt35-automates-initial-access-using-proxyshell)
- [G1051 - Medusa Group](../../../../Threat%20Intelligence/Groups/G1051%20-%20Medusa%20Group.md) — [Medusa Group](https://attack.mitre.org/groups/G1051) has cleared command history by running the PowerShell command `Remove-Item (Get-PSReadlineOption).HistorySavePath`.(Citation: CISA Medusa Group Medusa Ransomware March 2025) [CISA Medusa Group Medusa Ransomware March 2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a)
- [G0045 - menuPass](../../../../Threat%20Intelligence/Groups/G0045%20-%20menuPass.md) — [menuPass](https://attack.mitre.org/groups/G0045) has used [Wevtutil](https://attack.mitre.org/software/S0645) to remove PowerShell execution logs.(Citation: Securelist APT10 March 2021) [Securelist APT10 March 2021](https://securelist.com/apt10-sophisticated-multi-layered-loader-ecipekac-discovered-in-a41apt-campaign/101519/)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has deleted and cleared logs to avoid detection.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has cleared command history with <code>history -c</code>.(Citation: Trend Micro TeamTNT)(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Trend Micro TeamTNT](https://documents.trendmicro.com/assets/white_papers/wp-tracking-the-activities-of-teamTNT.pdf)
- [S9051 - The Gentlemen Ransomware](../../../../Threat%20Intelligence/Software/Malware/S9051%20-%20The%20Gentlemen%20Ransomware.md) — [The Gentlemen Ransomware](https://attack.mitre.org/software/S9051) has deleted PowerShell command history for all users by targeting the command history file located in `C:/Users/*/AppData/Roaming/Microsoft/Windows/PowerShell/PSReadline/ConsoleHost_History.txt`.(Citation: MSTI_GentelmenRansomware_May2026) [MSTI_GentelmenRansomware_May2026](https://www.microsoft.com/en-us/security/blog/2026/05/28/the-gentlemen-ransomware-dissecting-a-self-propagating-go-encryptor/)

## Mitigations

- [M1039 - Environment Variable Permissions](../../../../Defenses/Mitigations/M1039%20-%20Environment%20Variable%20Permissions.md) — Making the environment variables associated with command history read only may ensure that the history is preserved.(Citation: Securing bash history) [Securing bash history](http://www.akyl.net/securing-bashhistory-file-make-sure-your-linux-system-users-won%E2%80%99t-hide-or-delete-their-bashhistory)
- [M1029 - Remote Data Storage](../../../../Defenses/Mitigations/M1029%20-%20Remote%20Data%20Storage.md) — Forward logging of historical data to remote data store and centralized logging solution to preserve historical command line log data.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Preventing users from deleting or writing to certain files can stop adversaries from maliciously altering their <code>~/.bash_history</code> or <code>ConsoleHost_history.txt</code> files.

## Detection strategies

- [DET0165 - Behavioral Detection of Command History Clearing](../../../../Defenses/Detection%20Strategies/DET0165%20-%20Behavioral%20Detection%20of%20Command%20History%20Clearing.md)

## Sources

- [Broadcom ESXi Shell Audit](https://knowledge.broadcom.com/external/article/321910/auditing-esxi-shell-logins-and-commands.html)
- [Sophos PowerShell command audit](https://community.sophos.com/products/intercept/early-access-program/f/live-discover-response-queries/121529/live-discover---powershell-command-audit)
- [Microsoft PowerShell Command History](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_history?view=powershell-7)
- [US-CERT-TA18-106A](https://www.us-cert.gov/ncas/alerts/TA18-106A)
- [Sophos PowerShell Command History Forensics](https://community.sophos.com/sophos-labs/b/blog/posts/powershell-command-history-forensics)
