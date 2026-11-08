# T1563.001 - SSH Hijacking

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1563 - Remote Service Session Hijacking](../README.md)

Adversaries may hijack a legitimate user's SSH session to move laterally within an environment. Secure Shell (SSH) is a standard means of remote access on Linux and macOS systems. It allows a user to connect to another system via an encrypted tunnel, commonly authenticating through a password, certificate or the use of an asymmetric encryption key pair.

In order to move laterally from a compromised host, adversaries may take advantage of trust relationships established with other systems via public key authentication in active SSH sessions by hijacking an existing connection to another system. This may occur through compromising the SSH agent itself or by having access to the agent's socket. If an adversary is able to obtain root access, then hijacking SSH sessions is likely trivial.(Citation: Slideshare Abusing SSH)(Citation: SSHjack Blackhat)(Citation: Clockwork SSH Agent Hijacking)(Citation: Breach Post-mortem SSH Hijack)

[SSH Hijacking](https://attack.mitre.org/techniques/T1563/001) differs from use of [SSH](https://attack.mitre.org/techniques/T1021/004) because it hijacks an existing SSH session rather than creating a new session using [Valid Accounts](https://attack.mitre.org/techniques/T1078).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1563/001)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S1220 - MEDUSA](../../../../Threat%20Intelligence/Software/Malware/S1220%20-%20MEDUSA.md) — [MEDUSA](https://attack.mitre.org/software/S1220) can be configured to capture SSH credentials via SSH hijacking.(Citation: Google Cloud Mandiant UNC3886 2024) [Google Cloud Mandiant UNC3886 2024](https://cloud.google.com/blog/topics/threat-intelligence/uncovering-unc3886-espionage-operations)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Ensure that agent forwarding is disabled on systems that do not explicitly require this feature to prevent misuse. (Citation: Symantec SSH and ssh-agent) [Symantec SSH and ssh-agent](https://www.symantec.com/connect/articles/ssh-and-ssh-agent)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure SSH key pairs have strong passwords and refrain from using key-store technologies such as ssh-agent unless they are properly protected.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow remote access via SSH as root or other privileged accounts.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure proper file permissions are set and harden system to prevent root privilege escalation opportunities.

## Detection strategies

- [DET0256 - Detection Strategy for SSH Session Hijacking](../../../../Defenses/Detection%20Strategies/DET0256%20-%20Detection%20Strategy%20for%20SSH%20Session%20Hijacking.md)

## Sources

- [SSHjack Blackhat](https://www.blackhat.com/presentations/bh-usa-05/bh-us-05-boileau.pdf)
- [Clockwork SSH Agent Hijacking](https://web.archive.org/web/20210311184303/https://www.clockwork.com/news/2012/09/28/602/ssh_agent_hijacking/)
- [Slideshare Abusing SSH](https://www.slideshare.net/morisson/mistrusting-and-abusing-ssh-13526219)
- [Breach Post-mortem SSH Hijack](https://matrix.org/blog/2019/05/08/post-mortem-and-remediations-for-apr-11-security-incident/)
