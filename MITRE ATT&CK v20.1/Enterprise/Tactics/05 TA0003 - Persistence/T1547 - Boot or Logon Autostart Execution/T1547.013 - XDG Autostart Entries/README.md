# T1547.013 - XDG Autostart Entries

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may add or modify XDG Autostart Entries to execute malicious programs or commands when a user’s desktop environment is loaded at login. XDG Autostart entries are available for any XDG-compliant Linux system. XDG Autostart entries use Desktop Entry files (`.desktop`) to configure the user’s desktop environment upon user login. These configuration files determine what applications launch upon user login, define associated applications to open specific file types, and define applications used to open removable media.(Citation: Free Desktop Application Autostart Feb 2006)(Citation: Free Desktop Entry Keys)

Adversaries may abuse this feature to establish persistence by adding a path to a malicious binary or command to the `Exec` directive in the `.desktop` configuration file. When the user’s desktop environment is loaded at user login, the `.desktop` files located in the XDG Autostart directories are automatically executed. System-wide Autostart entries are located in the `/etc/xdg/autostart` directory while the user entries are located in the `~/.config/autostart` directory.

Adversaries may combine this technique with [Masquerading](https://attack.mitre.org/techniques/T1036) to blend malicious Autostart entries with legitimate programs.(Citation: Red Canary Netwire Linux 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/013)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) has established persistence using [InvisibleFerret](https://attack.mitre.org/software/S1245) malware to create a .desktop entry to run on startup on GNOME-based Linux devices.(Citation: Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024) [Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.zscaler.com/blogs/security-research/pyongyang-your-payroll-rise-north-korean-remote-workers-west)
- [S0235 - CrossRAT](../../../../Threat%20Intelligence/Software/Malware/S0235%20-%20CrossRAT.md) — [CrossRAT](https://attack.mitre.org/software/S0235) can use an XDG Autostart to establish persistence.(Citation: Red Canary Netwire Linux 2022) [Red Canary Netwire Linux 2022](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)
- [S0410 - Fysbis](../../../../Threat%20Intelligence/Software/Malware/S0410%20-%20Fysbis.md) — If executing without root privileges, [Fysbis](https://attack.mitre.org/software/S0410) adds a `.desktop` configuration file to the user's `~/.config/autostart` directory.(Citation: Red Canary Netwire Linux 2022)(Citation: Fysbis Dr Web Analysis) [Fysbis Dr Web Analysis](https://vms.drweb.com/virus/?i=4276269) · [Red Canary Netwire Linux 2022](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)
- [S1245 - InvisibleFerret](../../../../Threat%20Intelligence/Software/Malware/S1245%20-%20InvisibleFerret.md) — [InvisibleFerret](https://attack.mitre.org/software/S1245) has established persistence within GNOME-based Linux environments by placing entries within `.desktop` that run on Startup.(Citation: Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024) [Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.zscaler.com/blogs/security-research/pyongyang-your-payroll-rise-north-korean-remote-workers-west)
- [S0198 - NETWIRE](../../../../Threat%20Intelligence/Software/Malware/S0198%20-%20NETWIRE.md) — [NETWIRE](https://attack.mitre.org/software/S0198) can use XDG Autostart Entries to establish persistence on Linux systems.(Citation: Red Canary NETWIRE January 2020) [Red Canary NETWIRE January 2020](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)
- [S0192 - Pupy](../../../../Threat%20Intelligence/Software/Tools/S0192%20-%20Pupy.md) — [Pupy](https://attack.mitre.org/software/S0192) can use an XDG Autostart to establish persistence.(Citation: Red Canary Netwire Linux 2022) [Red Canary Netwire Linux 2022](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)
- [S1078 - RotaJakiro](../../../../Threat%20Intelligence/Software/Malware/S1078%20-%20RotaJakiro.md) — When executing with user-level permissions, [RotaJakiro](https://attack.mitre.org/software/S1078) can install persistence using a .desktop file under the `$HOME/.config/autostart/` folder.(Citation: RotaJakiro 2021 netlab360 analysis) [RotaJakiro 2021 netlab360 analysis](https://blog.netlab.360.com/stealth_rotajakiro_backdoor_en/)

## Mitigations

- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Restrict software installation to trusted repositories only and be cautious of orphaned software packages.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict write access to XDG autostart entries to only select privileged users.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit privileges of user accounts so only authorized privileged users can create and modify XDG autostart entries.

## Detection strategies

- [DET0390 - Linux Detection Strategy for T1547.013 - XDG Autostart Entries](../../../../Defenses/Detection%20Strategies/DET0390%20-%20Linux%20Detection%20Strategy%20for%20T1547.013%20-%20XDG%20Autostart%20Entries.md)

## Sources

- [Free Desktop Application Autostart Feb 2006](https://specifications.freedesktop.org/autostart-spec/autostart-spec-latest.html)
- [Free Desktop Entry Keys](https://specifications.freedesktop.org/desktop-entry-spec/latest/recognized-keys.html)
- [Red Canary Netwire Linux 2022](https://redcanary.com/blog/netwire-remote-access-trojan-on-linux/)
