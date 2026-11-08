# T1053.006 - Systemd Timers

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1053 - Scheduled Task/Job](../README.md)

Adversaries may abuse systemd timers to perform task scheduling for initial or recurring execution of malicious code. Systemd timers are unit files with file extension <code>.timer</code> that control services. Timers can be set to run on a calendar event or after a time span relative to a starting point. They can be used as an alternative to [Cron](https://attack.mitre.org/techniques/T1053/003) in Linux environments.(Citation: archlinux Systemd Timers Aug 2020) Systemd timers may be activated remotely via the <code>systemctl</code> command line utility, which operates over [SSH](https://attack.mitre.org/techniques/T1021/004).(Citation: Systemd Remote Control)

Each <code>.timer</code> file must have a corresponding <code>.service</code> file with the same name, e.g., <code>example.timer</code> and <code>example.service</code>. <code>.service</code> files are [Systemd Service](https://attack.mitre.org/techniques/T1543/002) unit files that are managed by the systemd system and service manager.(Citation: Linux man-pages: systemd January 2014) Privileged timers are written to <code>/etc/systemd/system/</code> and <code>/usr/lib/systemd/system</code> while user level are written to <code>~/.config/systemd/user/</code>.

An adversary may use systemd timers to execute malicious code at system startup or on a scheduled basis for persistence.(Citation: Arch Linux Package Systemd Compromise BleepingComputer 10JUL2018)(Citation: gist Arch package compromise 10JUL2018)(Citation: acroread package compromised Arch Linux Mail 8JUL2018) Timers installed using privileged paths may be used to maintain root level persistence. Adversaries may also install user level timers to achieve user level persistence.(Citation: Falcon Sandbox smp: 28553b3a9d)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1053/006)

**Tactics**  [Execution](../../README.md), [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Mitigations

- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit access to the root account and prevent users from creating and/or modifying systemd timer unit files.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict read/write access to systemd <code>.timer</code> unit files to only select privileged users who have a legitimate need to manage system services.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit user access to system utilities such as 'systemctl' or 'systemd-run' to users who have a legitimate need.

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used a multiplatform implant that can write to `~/.config/systemd/nvmconf/` to gain persistence on Linux hosts.(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [S9042 - CanisterWorm](../../../../Threat%20Intelligence/Software/Malware/S9042%20-%20CanisterWorm.md) — [CanisterWorm](https://attack.mitre.org/software/S9042) has registered itself as a systemd service for persistence on targeted Kubernetes nodes.(Citation: Aikido CanisterWorm MAR 2026)(Citation: Aikido TeamPCP Trivy MAR 2026) [Aikido TeamPCP Trivy MAR 2026](https://www.aikido.dev/blog/teampcp-deploys-worm-npm-trivy-compromise) · [Aikido CanisterWorm MAR 2026](https://www.aikido.dev/blog/teampcp-stage-payload-canisterworm-iran)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has obtained persistence on Linux devices by writing the `gh-token-monitor` daemon within `~/.config/systemd/user/gh-token-monitor.service` that polls GitHub every 60 seconds.(Citation: Wiz Mini Shai-Hulud MAY 2026) [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has also leveraged a daemon called “kitty-monitor.service” to maintain persistence within Linux hosts.(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/) · [Wiz Mini Shai-Hulud MAY 2026](https://www.wiz.io/blog/mini-shai-hulud-strikes-again-tanstack-more-npm-packages-compromised)

## Detection strategies

- [DET0231 - Behavioral Detection of Systemd Timer Abuse for Scheduled Execution](../../../../Defenses/Detection%20Strategies/DET0231%20-%20Behavioral%20Detection%20of%20Systemd%20Timer%20Abuse%20for%20Scheduled%20Execution.md)

## Sources

- [Systemd Remote Control](https://www.tecmint.com/control-systemd-services-on-remote-linux-server/)
- [archlinux Systemd Timers Aug 2020](https://wiki.archlinux.org/index.php/Systemd/Timers)
- [gist Arch package compromise 10JUL2018](https://gist.github.com/campuscodi/74d0d2e35d8fd9499c76333ce027345a)
- [Arch Linux Package Systemd Compromise BleepingComputer 10JUL2018](https://www.bleepingcomputer.com/news/security/malware-found-in-arch-linux-aur-package-repository/)
- [acroread package compromised Arch Linux Mail 8JUL2018](https://lists.archlinux.org/pipermail/aur-general/2018-July/034153.html)
- [Falcon Sandbox smp: 28553b3a9d](https://www.hybrid-analysis.com/sample/28553b3a9d2ad4361d33d29ac4bf771d008e0073cec01b5561c6348a608f8dd7?environmentId=300)
- [Linux man-pages: systemd January 2014](http://man7.org/linux/man-pages/man1/systemd.1.html)
