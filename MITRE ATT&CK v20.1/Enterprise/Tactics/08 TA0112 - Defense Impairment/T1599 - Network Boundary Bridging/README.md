# T1599 - Network Boundary Bridging

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may bridge network boundaries by compromising perimeter network devices or internal devices responsible for network segmentation. Breaching these devices may enable an adversary to bypass restrictions on traffic routing that otherwise separate trusted and untrusted networks.

Devices such as routers and firewalls can be used to create boundaries between trusted and untrusted networks.  They achieve this by restricting traffic types to enforce organizational policy in an attempt to reduce the risk inherent in such connections.  Restriction of traffic can be achieved by prohibiting IP addresses, layer 4 protocol ports, or through deep packet inspection to identify applications.  To participate with the rest of the network, these devices can be directly addressable or transparent, but their mode of operation has no bearing on how the adversary can bypass them when compromised.

When an adversary takes control of such a boundary device, they can bypass its policy enforcement to pass normally prohibited traffic across the trust boundary between the two separated networks without hinderance.  By achieving sufficient rights on the device, an adversary can reconfigure the device to allow the traffic they want, allowing them to then further achieve goals such as command and control via [Multi-hop Proxy](https://attack.mitre.org/techniques/T1090/003) or exfiltration of data via [Traffic Duplication](https://attack.mitre.org/techniques/T1020/001). Adversaries may also target internal devices responsible for network segmentation and abuse these in conjunction with [Internal Proxy](https://attack.mitre.org/techniques/T1090/001) to achieve the same goals.(Citation: Kaspersky ThreatNeedle Feb 2021)  In the cases where a border device separates two separate organizations, the adversary can also facilitate lateral movement into new victim environments.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1599)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1599.001 - Network Address Translation Traversal](T1599.001%20-%20Network%20Address%20Translation%20Traversal/README.md)

## Mitigations

- [M1043 - Credential Access Protection](../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — Some embedded network devices are capable of storing passwords for local accounts in either plain-text or encrypted formats. Ensure that, where available, local passwords are always encrypted, per vendor recommendations.(Citation: Cisco IOS Software Integrity Assurance - AAA) [Cisco IOS Software Integrity Assurance - AAA](https://tools.cisco.com/security/center/resources/integrity_assurance.html#38)
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Upon identifying a compromised network device being used to bridge a network boundary, block the malicious packets using an unaffected network device in path, such as a firewall or a router that has not been compromised. Continue to monitor for additional activity and to ensure that the blocks are indeed effective.
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts. Most embedded network devices support TACACS+ and/or RADIUS. Follow vendor prescribed best practices for hardening access control.(Citation: Cisco IOS Software Integrity Assurance - TACACS) [Cisco IOS Software Integrity Assurance - TACACS](https://tools.cisco.com/security/center/resources/integrity_assurance.html#39)
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict administrator accounts to as few individuals as possible, following least privilege principles. Prevent credential overlap across systems of administrator and privileged accounts, particularly between network and non-network platforms, such as servers or endpoints.

## Procedure examples

- [G0096 - APT41](../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) used `NATBypass` to bypass firewall restrictions and to access compromised systems via RDP.(Citation: apt41_dcsocytec_dec2022) [apt41_dcsocytec_dec2022](https://medium.com/@DCSO_CyTec/apt41-the-spy-who-failed-to-encrypt-me-24fc0f49cad1)
- [C0043 - Indian Critical Infrastructure Intrusions](../../../Threat%20Intelligence/Campaigns/C0043%20-%20Indian%20Critical%20Infrastructure%20Intrusions.md) — [Indian Critical Infrastructure Intrusions](https://attack.mitre.org/campaigns/C0043) involved the use of [FRP](https://attack.mitre.org/software/S1144) to bridge network boundaries and overcome NAT.(Citation: RecordedFuture RedEcho 2022) [Indian Critical Infrastructure Intrusions](https://attack.mitre.org/campaigns/C0043) also involved the use of VPN tunnels with a potentially compromised MSP entity allowing for direct access to critical infrastructure entity networks.(Citation: Dragos YIR 2021) [Dragos YIR 2021](https://hub.dragos.com/hubfs/333%20Year%20in%20Review/2021/2021%20ICS%20OT%20Cybersecurity%20Year%20In%20Review%20-%20Dragos%202021.pdf?hsLang=en) · [RecordedFuture RedEcho 2022](https://go.recordedfuture.com/hubfs/reports/ta-2022-0406.pdf)
- [G1045 - Salt Typhoon](../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has abused peer connections to exfiltrate data.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)

## Detection strategies

- [DET0006 - Detection Strategy for Network Boundary Bridging](../../../Defenses/Detection%20Strategies/DET0006%20-%20Detection%20Strategy%20for%20Network%20Boundary%20Bridging.md)

## Sources

- [Kaspersky ThreatNeedle Feb 2021](https://securelist.com/lazarus-threatneedle/100803/)
