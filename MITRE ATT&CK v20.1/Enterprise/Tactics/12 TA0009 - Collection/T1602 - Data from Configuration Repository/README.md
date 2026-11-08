# T1602 - Data from Configuration Repository

[Enterprise](../../../README.md) / [Collection](../README.md)

Adversaries may collect data related to managed devices from configuration repositories. Configuration repositories are used by management systems in order to configure, manage, and control data on remote systems. Configuration repositories may also facilitate remote access and administration of devices.

Adversaries may target these repositories in order to collect large quantities of sensitive system administration data. Data from configuration repositories may be exposed by various protocols and software and can store a wide variety of data, much of which may align with adversary Discovery objectives.(Citation: US-CERT-TA18-106A)(Citation: US-CERT TA17-156A SNMP Abuse 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1602)

**Tactics**  [Collection](../README.md)

**Platforms**  [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1602.002 - Network Device Configuration Dump](T1602.002%20-%20Network%20Device%20Configuration%20Dump/README.md)
- [T1602.001 - SNMP (MIB Dump)](T1602.001%20-%20SNMP%20%28MIB%20Dump%29/README.md)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Configure SNMPv3 to use the highest level of security (authPriv) available.(Citation: US-CERT TA17-156A SNMP Abuse 2017) [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Apply extended ACLs to block unauthorized protocols outside the trusted network.(Citation: US-CERT TA17-156A SNMP Abuse 2017) [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Configure intrusion prevention devices to detect SNMP queries and commands from unauthorized sources.(Citation: US-CERT-TA18-106A) [US-CERT-TA18-106A](https://www.us-cert.gov/ncas/alerts/TA18-106A)
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Segregate SNMP traffic on a separate management network.(Citation: US-CERT TA17-156A SNMP Abuse 2017) [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Allowlist MIB objects and implement SNMP views.(Citation: Cisco Securing SNMP) [Cisco Securing SNMP](https://www.cisco.com/c/en/us/support/docs/ip/simple-network-management-protocol-snmp/20370-snmpsecurity-20370.html)
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Keep system images and software updated and migrate to SNMPv3.(Citation: Cisco Blog Legacy Device Attacks) [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)

## Detection strategies

- [DET0592 - Detection Strategy for Data from Configuration Repository on Network Devices](../../../Defenses/Detection%20Strategies/DET0592%20-%20Detection%20Strategy%20for%20Data%20from%20Configuration%20Repository%20on%20Network%20Devices.md)

## Sources

- [Cisco Advisory SNMP v3 Authentication Vulnerabilities](https://tools.cisco.com/security/center/content/CiscoAppliedMitigationBulletin/cisco-amb-20080610-SNMPv3)
- [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [US-CERT-TA18-106A](https://www.us-cert.gov/ncas/alerts/TA18-106A)
