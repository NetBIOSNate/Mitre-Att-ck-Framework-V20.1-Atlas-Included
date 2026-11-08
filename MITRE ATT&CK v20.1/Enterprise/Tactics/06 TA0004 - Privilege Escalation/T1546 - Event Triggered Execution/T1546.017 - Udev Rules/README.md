# T1546.017 - Udev Rules

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may maintain persistence through executing malicious content triggered using udev rules. Udev is the Linux kernel device manager that dynamically manages device nodes, handles access to pseudo-device files in the `/dev` directory, and responds to hardware events, such as when external devices like hard drives or keyboards are plugged in or removed. Udev uses rule files with `match keys` to specify the conditions a hardware event must meet and `action keys` to define the actions that should follow. Root permissions are required to create, modify, or delete rule files located in `/etc/udev/rules.d/`, `/run/udev/rules.d/`, `/usr/lib/udev/rules.d/`, `/usr/local/lib/udev/rules.d/`, and `/lib/udev/rules.d/`. Rule priority is determined by both directory and by the digit prefix in the rule filename.(Citation: Ignacio Udev research 2024)(Citation: Elastic Linux Persistence 2024)

Adversaries may abuse the udev subsystem by adding or modifying rules in udev rule files to execute malicious content. For example, an adversary may configure a rule to execute their binary each time the pseudo-device file, such as `/dev/random`, is accessed by an application. Although udev is limited to running short tasks and is restricted by systemd-udevd's sandbox (blocking network and filesystem access), attackers may use scripting commands under the action key `RUN+=` to detach and run the malicious content’s process in the background to bypass these controls.(Citation: Reichert aon sedexp 2024)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/017)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [S1219 - REPTILE](../../../../Threat%20Intelligence/Software/Malware/S1219%20-%20REPTILE.md) — [REPTILE](https://attack.mitre.org/software/S1219) has used udev for persistence.(Citation: Google Cloud Mandiant UNC3886 2024) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations)

## Detection strategies

- [DET0375 - Detection Strategy for T1546.017 - Udev Rules (Linux)](../../../../Defenses/Detection%20Strategies/DET0375%20-%20Detection%20Strategy%20for%20T1546.017%20-%20Udev%20Rules%20%28Linux%29.md)

## Sources

- [Ignacio Udev research 2024](https://ch4ik0.github.io/en/posts/leveraging-Linux-udev-for-persistence/)
- [Elastic Linux Persistence 2024](https://www.elastic.co/security-labs/sequel-on-persistence-mechanisms)
- [Reichert aon sedexp 2024](https://www.aon.com/en/insights/cyber-labs/unveiling-sedexp)
