# T1546.004 - Unix Shell Configuration Modification

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence through executing malicious commands triggered by a user’s shell. User [Unix Shell](https://attack.mitre.org/techniques/T1059/004)s execute several configuration scripts at different points throughout the session based on events. For example, when a user opens a command-line interface or remotely logs in (such as via SSH) a login shell is initiated. The login shell executes scripts from the system (<code>/etc</code>) and the user’s home directory (<code>~/</code>) to configure the environment. All login shells on a system use /etc/profile when initiated. These configuration scripts run at the permission level of their directory and are often used to set environment variables, create aliases, and customize the user’s environment. When the shell exits or terminates, additional shell scripts are executed to ensure the shell exits appropriately. 

Adversaries may attempt to establish persistence by inserting commands into scripts automatically executed by shells. Using bash as an example, the default shell for most GNU/Linux systems, adversaries may add commands that launch malicious binaries into the <code>/etc/profile</code> and <code>/etc/profile.d</code> files.(Citation: intezer-kaiji-malware)(Citation: bencane blog bashrc) These files typically require root permissions to modify and are executed each time any shell on a system launches. For user level permissions, adversaries can insert malicious commands into <code>~/.bash_profile</code>, <code>~/.bash_login</code>, or <code>~/.profile</code> which are sourced when a user opens a command-line interface or connects remotely.(Citation: anomali-rocke-tactics)(Citation: Linux manual bash invocation) Since the system only executes the first existing file in the listed order, adversaries have used <code>~/.bash_profile</code> to ensure execution. Adversaries have also leveraged the <code>~/.bashrc</code> file which is additionally executed if the connection is established remotely or an additional interactive shell is opened, such as a new tab in the command-line interface.(Citation: Tsunami)(Citation: anomali-rocke-tactics)(Citation: anomali-linux-rabbit)(Citation: Magento) Some malware targets the termination of a program to trigger execution, adversaries can use the <code>~/.bash_logout</code> file to execute malicious commands at the end of a session. 

For macOS, the functionality of this technique is similar but may leverage zsh, the default shell for macOS 10.15+. When the Terminal.app is opened, the application launches a zsh login shell and a zsh interactive shell. The login shell configures the system environment using <code>/etc/profile</code>, <code>/etc/zshenv</code>, <code>/etc/zprofile</code>, and <code>/etc/zlogin</code>.(Citation: ScriptingOSX zsh)(Citation: PersistentJXA_leopitt)(Citation: code_persistence_zsh)(Citation: macOS MS office sandbox escape) The login shell then configures the user environment with <code>~/.zprofile</code> and <code>~/.zlogin</code>. The interactive shell uses the <code>~/.zshrc</code> to configure the user environment. Upon exiting, <code>/etc/zlogout</code> and <code>~/.zlogout</code> are executed. For legacy programs, macOS executes <code>/etc/bashrc</code> on startup.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/004)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has targeted macOS victim hosts using a bash downloader `coremedia.sh` and a bash script `cloud.sh`.(Citation: Sekoia ClickFake 2025) [Sekoia ClickFake 2025](https://blog.sekoia.io/clickfake-interview-campaign-by-lazarus/)
- [S0690 - Green Lambert](../../../../Threat%20Intelligence/Software/Malware/S0690%20-%20Green%20Lambert.md) — [Green Lambert](https://attack.mitre.org/software/S0690) can establish persistence on a compromised host through modifying the `profile`, `login`, and run command (rc) files associated with the `bash`, `csh`, and `tcsh` shells. (Citation: Objective See Green Lambert for OSX Oct 2021)(Citation: Glitch-Cat Green Lambert ATTCK Oct 2021) [Objective See Green Lambert for OSX Oct 2021](https://objective-see.com/blog/blog_0x68.html) · [Glitch-Cat Green Lambert ATTCK Oct 2021](https://web.archive.org/web/20211018145402/https://www.glitch-cat.com/blog/green-lambert-and-attack)
- [S0362 - Linux Rabbit](../../../../Threat%20Intelligence/Software/Malware/S0362%20-%20Linux%20Rabbit.md) — [Linux Rabbit](https://attack.mitre.org/software/S0362) maintains persistence on an infected machine through rc.local and .bashrc files. (Citation: Anomali Linux Rabbit 2018) [Anomali Linux Rabbit 2018](https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat)
- [S9014 - PHASEJAM](../../../../Threat%20Intelligence/Software/Malware/S9014%20-%20PHASEJAM.md) — [PHASEJAM](https://attack.mitre.org/software/S9014) has used a bash script to modify components on Ivanti Connect Secure appliances and execute files via `/bin/bash`.[1] It has also used the Linux stream editor (`sed`) to execute commands.(Citation: Google UNC5221 Ivanti January 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)
- [S1078 - RotaJakiro](../../../../Threat%20Intelligence/Software/Malware/S1078%20-%20RotaJakiro.md) — When executing with non-root level permissions, [RotaJakiro](https://attack.mitre.org/software/S1078) can install persistence by adding a command to the .bashrc file that executes a binary in the `${HOME}/.gvfsd/.profile/` folder.(Citation: RotaJakiro 2021 netlab360 analysis) [RotaJakiro 2021 netlab360 analysis](https://blog.netlab.360.com/stealth_rotajakiro_backdoor_en/)
- [C0045 - ShadowRay](../../../../Threat%20Intelligence/Campaigns/C0045%20-%20ShadowRay.md) — During [ShadowRay](https://attack.mitre.org/campaigns/C0045), threat actors executed commands on interactive and reverse shells.(Citation: Oligo ShadowRay Campaign MAR 2024) [Oligo ShadowRay Campaign MAR 2024](https://www.oligo.security/blog/shadowray-attack-ai-workloads-actively-exploited-in-the-wild)
- [S0658 - XCSSET](../../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — Using [AppleScript](https://attack.mitre.org/techniques/T1059/002), [XCSSET](https://attack.mitre.org/software/S0658) adds it's executable to the user's `~/.zshrc_aliases` file (`"echo " & payload & " > ~/zshrc_aliases"`), it then adds a line to the .zshrc file to source the `.zshrc_aliases` file (`[ -f $HOME/.zshrc_aliases ] && . $HOME/.zshrc_aliases`). Each time the user starts a new `zsh` terminal session, the `.zshrc` file executes the `.zshrc_aliases` file.(Citation: Microsoft March 2025 XCSSET) [Microsoft March 2025 XCSSET](https://www.microsoft.com/en-us/security/blog/2025/03/11/new-xcsset-malware-adds-new-obfuscation-persistence-techniques-to-infect-xcode-projects/)

## Detection strategies

- [DET0020 - Detect Shell Configuration Modification for Persistence via Event-Triggered Execution](../../../../Defenses/Detection%20Strategies/DET0020%20-%20Detect%20Shell%20Configuration%20Modification%20for%20Persistence%20via%20Event-Triggered%20Execution.md)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Making these files immutable and only changeable by certain administrators will limit the ability for adversaries to easily create user level persistence.

## Sources

- [anomali-linux-rabbit](https://www.anomali.com/blog/pulling-linux-rabbit-rabbot-malware-out-of-a-hat)
- [anomali-rocke-tactics](https://www.anomali.com/blog/illicit-cryptomining-threat-actor-rocke-changes-tactics-now-more-difficult-to-detect)
- [Linux manual bash invocation](https://wiki.archlinux.org/index.php/Bash#Invocation)
- [ScriptingOSX zsh](https://scriptingosx.com/2019/06/moving-to-zsh-part-2-configuration-files/)
- [bencane blog bashrc](https://web.archive.org/web/20220316014323/http://bencane.com/2013/09/16/understanding-a-little-more-about-etcprofile-and-etcbashrc/)
- [macOS MS office sandbox escape](https://cedowens.medium.com/macos-ms-office-sandbox-brain-dump-4509b5fed49a)
- [Magento](https://blog.sucuri.net/2018/05/shell-logins-as-a-magento-reinfection-vector.html)
- [Tsunami](https://unit42.paloaltonetworks.com/unit42-new-iotlinux-malware-targets-dvrs-forms-botnet/)
- [PersistentJXA_leopitt](https://posts.specterops.io/persistent-jxa-66e1c3cd1cf5)
- [code_persistence_zsh](https://github.com/D00MFist/PersistentJXA/blob/master/BashProfilePersist.js)
- [ESF_filemonitor](https://objective-see.com/blog/blog_0x48.html)
- [intezer-kaiji-malware](https://www.intezer.com/blog/research/kaiji-new-chinese-linux-malware-turning-to-golang/)
