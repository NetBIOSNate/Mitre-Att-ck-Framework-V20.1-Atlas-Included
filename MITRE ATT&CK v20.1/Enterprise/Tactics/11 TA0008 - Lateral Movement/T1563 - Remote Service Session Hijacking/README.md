# T1563 - Remote Service Session Hijacking

[Enterprise](../../../README.md) / [Lateral Movement](../README.md)

Adversaries may take control of preexisting sessions with remote services to move laterally in an environment. Users may use valid credentials to log into a service specifically designed to accept remote connections, such as telnet, SSH, and RDP. When a user logs into a service, a session will be established that will allow them to maintain a continuous interaction with that service.

Adversaries may commandeer these sessions to carry out actions on remote systems. [Remote Service Session Hijacking](https://attack.mitre.org/techniques/T1563) differs from use of [Remote Services](https://attack.mitre.org/techniques/T1021) because it hijacks an existing session rather than creating a new session using [Valid Accounts](https://attack.mitre.org/techniques/T1078).(Citation: RDP Hijacking Medium)(Citation: Breach Post-mortem SSH Hijack)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1563)

**Tactics**  [Lateral Movement](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1563.002 - RDP Hijacking](T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1563.001 - SSH Hijacking](T1563.001%20-%20SSH%20Hijacking/README.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable the remote service (ex: SSH, RDP, etc.) if it is unnecessary.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Enable firewall rules to block unnecessary traffic between network security zones within a network.
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Set and enforce secure password policies for accounts.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow remote access to services as a privileged account unless necessary.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit remote user permissions if remote access is necessary.

## Detection strategies

- [DET0079 - Detection of Remote Service Session Hijacking](../../../Defenses/Detection%20Strategies/DET0079%20-%20Detection%20of%20Remote%20Service%20Session%20Hijacking.md)

## Sources

- [RDP Hijacking Medium](https://medium.com/@networksecurity/rdp-hijacking-how-to-hijack-rds-and-remoteapp-sessions-transparently-to-move-through-an-da2a1e73a5f6)
- [Breach Post-mortem SSH Hijack](https://matrix.org/blog/2019/05/08/post-mortem-and-remediations-for-apr-11-security-incident/)
