# T1569.003 - Systemctl

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1569 - System Services](../README.md)

Adversaries may abuse systemctl to execute commands or programs. Systemctl is the primary interface for systemd, the Linux init system and service manager. Typically invoked from a shell, Systemctl can also be integrated into scripts or applications.   

Adversaries may use systemctl to execute commands or programs as [Systemd Service](https://attack.mitre.org/techniques/T1543/002)s. Common subcommands include: `systemctl start`, `systemctl stop`, `systemctl enable`, `systemctl disable`, and `systemctl status`.(Citation: Red Hat Systemctl 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1569/003)

**Tactics**  [Execution](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [S9042 - CanisterWorm](../../../../Threat%20Intelligence/Software/Malware/S9042%20-%20CanisterWorm.md) — [CanisterWorm](https://attack.mitre.org/software/S9042) has used executed `systemctl --user daemon-reload` to reload systemd, then enables and starts the malicious service.(Citation: Aikido TeamPCP Trivy MAR 2026) [Aikido TeamPCP Trivy MAR 2026](https://www.aikido.dev/blog/teampcp-deploys-worm-npm-trivy-compromise)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has created system services to execute cryptocurrency mining software.(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/)

## Detection strategies

- [DET0073 - Detection Strategy for System Services: Systemctl](../../../../Defenses/Detection%20Strategies/DET0073%20-%20Detection%20Strategy%20for%20System%20Services%20-%20Systemctl.md)

## Mitigations

- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit user access to `systemctl` to only users who have a legitimate need.

## Sources

- [Red Hat Systemctl 2022](https://www.redhat.com/en/blog/linux-systemctl-manage-services)
