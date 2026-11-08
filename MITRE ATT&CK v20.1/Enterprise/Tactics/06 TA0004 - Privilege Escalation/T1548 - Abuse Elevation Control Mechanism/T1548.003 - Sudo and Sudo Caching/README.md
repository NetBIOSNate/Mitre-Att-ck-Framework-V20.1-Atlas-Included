# T1548.003 - Sudo and Sudo Caching

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1548 - Abuse Elevation Control Mechanism](../README.md)

Adversaries may perform sudo caching and/or use the sudoers file to elevate privileges. Adversaries may do this to execute commands as other users or spawn processes with higher privileges.

Within Linux and MacOS systems, sudo (sometimes referred to as "superuser do") allows users to perform commands from terminals with elevated privileges and to control who can perform these commands on the system. The <code>sudo</code> command "allows a system administrator to delegate authority to give certain users (or groups of users) the ability to run some (or all) commands as root or another user while providing an audit trail of the commands and their arguments."(Citation: sudo man page 2018) Since sudo was made for the system administrator, it has some useful configuration features such as a <code>timestamp_timeout</code>, which is the amount of time in minutes between instances of <code>sudo</code> before it will re-prompt for a password. This is because <code>sudo</code> has the ability to cache credentials for a period of time. Sudo creates (or touches) a file at <code>/var/db/sudo</code> with a timestamp of when sudo was last run to determine this timeout. Additionally, there is a <code>tty_tickets</code> variable that treats each new tty (terminal session) in isolation. This means that, for example, the sudo timeout of one tty will not affect another tty (you will have to type the password again).

The sudoers file, <code>/etc/sudoers</code>, describes which users can run which commands and from which terminals. This also describes which commands users can run as other users or groups. This provides the principle of least privilege such that users are running in their lowest possible permissions for most of the time and only elevate to other users or permissions as needed, typically by prompting for a password. However, the sudoers file can also specify when to not prompt users for passwords with a line like <code>user1 ALL=(ALL) NOPASSWD: ALL</code>.(Citation: OSX.Dok Malware) Elevated privileges are required to edit this file though.

Adversaries can also abuse poor configurations of these mechanisms to escalate privileges without needing the user's password. For example, <code>/var/db/sudo</code>'s timestamp can be monitored to see if it falls within the <code>timestamp_timeout</code> range. If it does, then malware can execute sudo commands without needing to supply the user's password. Additionally, if <code>tty_tickets</code> is disabled, adversaries can do this from any tty for that user.

In the wild, malware has disabled <code>tty_tickets</code> to potentially make scripting easier by issuing <code>echo \'Defaults !tty_tickets\' >> /etc/sudoers</code>.(Citation: cybereason osx proton) In order for this change to be reflected, the malware also issued <code>killall Terminal</code>. As of macOS Sierra, the sudoers file has <code>tty_tickets</code> enabled by default.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1548/003)

**Tactics**  [Privilege Escalation](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has executed persistence actions using `sudo` commands within zsh shells.(Citation: Microsoft Sapphire Sleet APR 2026) [Microsoft Sapphire Sleet APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/16/dissecting-sapphire-sleets-macos-intrusion-from-lure-to-compromise/)
- [S9045 - BACKUPOSINT v9.0 APEX PREDATOR](../../../../Threat%20Intelligence/Software/Malware/S9045%20-%20BACKUPOSINT%20v9.0%20APEX%20PREDATOR.md) — [BACKUPOSINT v9.0 APEX PREDATOR](https://attack.mitre.org/software/S9045) has the ability to leverage `sudo` for executing commands.(Citation: AI-Mexico-Govt-Compromise) [AI-Mexico-Govt-Compromise](https://5943619.hs-sites.com/hubfs/116-Whitepapers/dragos-2026-ai-mexico-water-attack-intel-brief.pdf)
- [S9042 - CanisterWorm](../../../../Threat%20Intelligence/Software/Malware/S9042%20-%20CanisterWorm.md) — [CanisterWorm](https://attack.mitre.org/software/S9042) has checked if the current user is root. If it is, [CanisterWorm](https://attack.mitre.org/software/S9042) will wipe the system using `rm –rf / --no-preserve-root`. If it is not, [CanisterWorm](https://attack.mitre.org/software/S9042) will try passwordless sudo and will run the same command.(Citation: Aikido CanisterWorm MAR 2026) [Aikido CanisterWorm MAR 2026](https://www.aikido.dev/blog/teampcp-stage-payload-canisterworm-iran)
- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can use <code>sudo</code> to run a command.(Citation: Cobalt Strike Manual 4.3 November 2020) [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf)
- [S0281 - Dok](../../../../Threat%20Intelligence/Software/Malware/S0281%20-%20Dok.md) — [Dok](https://attack.mitre.org/software/S0281) adds <code>admin ALL=(ALL) NOPASSWD: ALL</code> to the <code>/etc/sudoers</code> file.(Citation: hexed osx.dok analysis 2019) [hexed osx.dok analysis 2019](https://web.archive.org/web/20221007144948/http://www.hexed.in/2019/07/osxdok-analysis.html)
- [S0279 - Proton](../../../../Threat%20Intelligence/Software/Malware/S0279%20-%20Proton.md) — [Proton](https://attack.mitre.org/software/S0279) modifies the tty_tickets line in the sudoers file.(Citation: objsee mac malware 2017) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has elevated privileges of local user accounts by editing `/etc/sudoers` or adding a file under `/etc/sudoers.d/`.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has attempted to gain root access by leveraging `sudo` and `/etc/sudoers.d`.(Citation: Socket Shai-Hulud November 2025) [Socket Shai-Hulud November 2025](https://socket.dev/blog/shai-hulud-strikes-again-v2)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can use `sudo` for code execution.(Citation: Aqua Security Blog Trivy Compromise APR 2026) [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know)

## Detection strategies

- [DET0052 - Behavioral Detection Strategy for Abuse of Sudo and Sudo Caching](../../../../Defenses/Detection%20Strategies/DET0052%20-%20Behavioral%20Detection%20Strategy%20for%20Abuse%20of%20Sudo%20and%20Sudo%20Caching.md)

## Mitigations

- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Ensuring that the <code>tty_tickets</code> setting is enabled will prevent this leakage across tty sessions.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — By requiring a password, even if an adversary can get terminal access, they must know the password to run anything in the sudoers file. Setting the <code>timestamp_timeout</code> to 0 will require the user to input their password every time <code>sudo</code> is executed.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — The sudoers file should be strictly edited such that passwords are always required and that users can't spawn risky processes as users with higher privilege.

## Sources

- [cybereason osx proton](https://www.cybereason.com/blog/labs-proton-b-what-this-mac-malware-actually-does)
- [OSX.Dok Malware](https://blog.malwarebytes.com/threat-analysis/2017/04/new-osx-dok-malware-intercepts-web-traffic/)
- [sudo man page 2018](https://www.sudo.ws/)
