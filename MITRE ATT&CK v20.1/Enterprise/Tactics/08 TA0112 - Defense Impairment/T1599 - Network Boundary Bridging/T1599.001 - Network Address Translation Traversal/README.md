# T1599.001 - Network Address Translation Traversal

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1599 - Network Boundary Bridging](../README.md)

Adversaries may bridge network boundaries by modifying a network device’s Network Address Translation (NAT) configuration. Malicious modifications to NAT may enable an adversary to bypass restrictions on traffic routing that otherwise separate trusted and untrusted networks.

Network devices such as routers and firewalls that connect multiple networks together may implement NAT during the process of passing packets between networks. When performing NAT, the network device will rewrite the source and/or destination addresses of the IP address header. Some network designs require NAT for the packets to cross the border device.  A typical example of this is environments where internal networks make use of non-Internet routable addresses.(Citation: RFC1918)

When an adversary gains control of a network boundary device, they may modify NAT configurations to send traffic between two separated networks, or to obscure their activities.  In network designs that require NAT to function, such modifications enable the adversary to overcome inherent routing limitations that would normally prevent them from accessing protected systems behind the border device.  In network designs that do not require NAT, adversaries may use address translation to further obscure their activities, as changing the addresses of packets that traverse a network boundary device can make monitoring data transmissions more challenging for defenders.  

Adversaries may use [Patch System Image](https://attack.mitre.org/techniques/T1601/001) to change the operating system of a network device, implementing their own custom NAT mechanisms to further obscure their activities.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1599/001)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Mitigations

- [M1043 - Credential Access Protection](../../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — Some embedded network devices are capable of storing passwords for local accounts in either plain-text or encrypted formats. Ensure that, where available, local passwords are always encrypted, per vendor recommendations. (Citation: Cisco IOS Software Integrity Assurance - AAA) [Cisco IOS Software Integrity Assurance - AAA](https://tools.cisco.com/security/center/resources/integrity_assurance.html#38)
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Block Traffic Upon identifying a compromised network device being used to bridge a network boundary, block the malicious packets using an unaffected network device in path, such as a firewall or a router that has not been compromised. Continue to monitor for additional activity and to ensure that the blocks are indeed effective.
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts. Most embedded network devices support TACACS+ and/or RADIUS. Follow vendor prescribed best practices for hardening access control. (Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict administrator accounts to as few individuals as possible, following least privilege principles. Prevent credential overlap across systems of administrator and privileged accounts, particularly between network and non-network platforms, such as servers or endpoints.

## Detection strategies

- [DET0163 - Detection Strategy for Network Address Translation Traversal](../../../../Defenses/Detection%20Strategies/DET0163%20-%20Detection%20Strategy%20for%20Network%20Address%20Translation%20Traversal.md)

## Sources

- [RFC1918](https://tools.ietf.org/html/rfc1918)
