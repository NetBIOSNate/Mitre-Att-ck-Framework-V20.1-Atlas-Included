# T1556.004 - Network Device Authentication

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may use [Patch System Image](https://attack.mitre.org/techniques/T1601/001) to hard code a password in the operating system, thus bypassing of native authentication mechanisms for local accounts on network devices.

[Modify System Image](https://attack.mitre.org/techniques/T1601) may include implanted code to the operating system for network devices to provide access for adversaries using a specific password.  The modification includes a specific password which is implanted in the operating system image via the patch.  Upon authentication attempts, the inserted code will first check to see if the user input is the password. If so, access is granted. Otherwise, the implanted code will pass the credentials on for verification of potentially valid credentials.(Citation: Mandiant - Synful Knock)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/004)

**Tactics**  [Persistence](../../README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md), [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [S9013 - DRYHOOK](../../../../Threat%20Intelligence/Software/Malware/S9013%20-%20DRYHOOK.md) — [DRYHOOK](https://attack.mitre.org/software/S9013) has patched victim appliances authentication routines to capture credentials in plaintext as users log in.(Citation: Google UNC5221 Ivanti January 2025) [Google UNC5221 Ivanti January 2025](https://cloud.google.com/blog/topics/threat-intelligence/ivanti-connect-secure-vpn-zero-day)
- [S1104 - SLOWPULSE](../../../../Threat%20Intelligence/Software/Malware/S1104%20-%20SLOWPULSE.md) — [SLOWPULSE](https://attack.mitre.org/software/S1104) can modify LDAP and two factor authentication flows by inspecting login credentials and forcing successful authentication if the provided password matches a chosen backdoor password.(Citation: Mandiant Pulse Secure Zero-Day April 2021) [Mandiant Pulse Secure Zero-Day April 2021](https://www.mandiant.com/resources/blog/suspected-apt-actors-leverage-bypass-techniques-pulse-secure-zero-day)
- [S0519 - SYNful Knock](../../../../Threat%20Intelligence/Software/Malware/S0519%20-%20SYNful%20Knock.md) — [SYNful Knock](https://attack.mitre.org/software/S0519) has the capability to add its own custom backdoor password when it modifies the operating system of the affected network device.(Citation: Mandiant - Synful Knock) [Mandiant - Synful Knock](https://cloud.google.com/blog/topics/threat-intelligence/synful-knock-acis/)

## Detection strategies

- [DET0272 - Detect Modification of Network Device Authentication via Patched System Images](../../../../Defenses/Detection%20Strategies/DET0272%20-%20Detect%20Modification%20of%20Network%20Device%20Authentication%20via%20Patched%20System%20Images.md)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts. Most embedded network devices support TACACS+ and/or RADIUS. Follow vendor prescribed best practices for hardening access control. (Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict administrator accounts to as few individuals as possible, following least privilege principles. Prevent credential overlap across systems of administrator and privileged accounts, particularly between network and non-network platforms, such as servers or endpoints.

## Sources

- [Mandiant - Synful Knock](https://cloud.google.com/blog/topics/threat-intelligence/synful-knock-acis/)
