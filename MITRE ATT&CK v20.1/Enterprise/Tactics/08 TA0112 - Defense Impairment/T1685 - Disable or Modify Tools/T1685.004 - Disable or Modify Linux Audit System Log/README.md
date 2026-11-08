# T1685.004 - Disable or Modify Linux Audit System Log

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1685 - Disable or Modify Tools](../README.md)

Adversaries may disable or modify the Linux Audit system to hide malicious activity and avoid detection. Linux admins use the Linux Audit system to track security-relevant information on a system. The Linux Audit system operates at the kernel-level and maintains event logs on application and system activity such as process, network, file, and login events based on pre-configured rules. 

Often referred to as `auditd`, this is the name of the daemon used to write events to disk and is governed by the parameters set in the `audit.conf` configuration file. Two primary ways to configure the log generation rules are through the command line `auditctl` utility and the file `/etc/audit/audit.rules`, containing a sequence of `auditctl` commands loaded at boot time.(Citation: IzyKnows auditd threat detection 2022)(Citation: Red Hat Linux Disable or Mod)

With root privileges, adversaries may be able to ensure their activity is not logged through disabling the Audit system service, editing the configuration/rule files, or by hooking the Audit system library functions. Using the command line, adversaries can disable the Audit system service through killing processes associated with `auditd` daemon or use `systemctl` to stop the Audit service. Adversaries can also hook Audit system functions to disable logging or modify the rules contained in the `/etc/audit/audit.rules` or `audit.conf` files to ignore malicious activity.(Citation: ESET Ebury Feb 2014)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1685/004)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0062 - Detection Strategy for Disable or Modify Linux Audit System Log](../../../../Defenses/Detection%20Strategies/DET0062%20-%20Detection%20Strategy%20for%20Disable%20or%20Modify%20Linux%20Audit%20System%20Log.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Routinely check account role permissions to ensure only expected users and roles have permission to modify logging settings. To ensure Audit rules can not be modified at runtime, add the `auditctl -e 2` as the last command in the audit.rules files. Once started, any attempt to change the configuration in this mode will be audited and denied. The configuration can only be changed by rebooting the machine.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — An adversary must already have root level access on the local system to make full use of this technique; be sure to restrict users and accounts to the least privileges they require.

## Procedure examples

- [S0377 - Ebury](../../../../Threat%20Intelligence/Software/Malware/S0377%20-%20Ebury.md) — [Ebury](https://attack.mitre.org/software/S0377) disables OpenSSH, system (`systemd`), and audit logs (`/sbin/auditd`) when the backdoor is active.(Citation: ESET Ebury May 2024) [ESET Ebury May 2024](https://web-assets.esetstatic.com/wls/en/papers/white-papers/ebury-is-alive-but-unseen.pdf)

## Sources

- [IzyKnows auditd threat detection 2022](https://izyknows.medium.com/linux-auditd-for-threat-detection-d06c8b941505)
- [ESET Ebury Feb 2014](https://www.welivesecurity.com/2014/02/21/an-in-depth-analysis-of-linuxebury/)
- [Red Hat Linux Disable or Mod](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/6/html/security_guide/chap-system_auditing)
