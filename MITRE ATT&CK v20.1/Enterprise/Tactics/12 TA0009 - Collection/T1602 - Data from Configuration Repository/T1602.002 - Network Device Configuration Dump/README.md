# T1602.002 - Network Device Configuration Dump

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1602 - Data from Configuration Repository](../README.md)

Adversaries may access network configuration files to collect sensitive data about the device and the network. The network configuration is a file containing parameters that determine the operation of the device. The device typically stores an in-memory copy of the configuration while operating, and a separate configuration on non-volatile storage to load after device reset. Adversaries can inspect the configuration files to reveal information about the target network and its layout, the network device and its software, or identifying legitimate accounts and credentials for later use.

Adversaries can use common management tools and protocols, such as Simple Network Management Protocol (SNMP) and Smart Install (SMI), to access network configuration files.(Citation: US-CERT TA18-106A Network Infrastructure Devices 2018)(Citation: Cisco Blog Legacy Device Attacks) These tools may be used to query specific data from a configuration repository or configure the device to export the configuration for later analysis.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1602/002)

**Tactics**  [Collection](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries gathered and used the FortiGate bookmarks defined in the configuration file to include the statically defined credentials that facilitated RDP connections to jump hosts.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [S9010 - GlassWorm](../../../../Threat%20Intelligence/Software/Malware/S9010%20-%20GlassWorm.md) — [GlassWorm](https://attack.mitre.org/software/S9010) has gathered data pertaining to VPN configurations.(Citation: Koi Glassworm New Tricks December 2025)(Citation: Socket GlassWorm January 2026) [GlassWorm](https://attack.mitre.org/software/S9010) has also targeted locally stored data on macOS located in `/Library/Application Support/Fortinet/FortiClient/conf/vpn.plist`.(Citation: Socket GlassWorm January 2026) [Koi Glassworm New Tricks December 2025](https://www.koi.ai/blog/glassworm-goes-mac-fresh-infrastructure-new-tricks) · [Socket GlassWorm January 2026](https://socket.dev/blog/glassworm-loader-hits-open-vsx-via-suspected-developer-account-compromise)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has attempted to acquire credentials by dumping network device configurations.(Citation: Cisco Salt Typhoon FEB 2025)(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [Salt Typhoon](https://attack.mitre.org/groups/G1045) has also obtained data using RANCID.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a) · [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)

## Detection strategies

- [DET0233 - Detection Strategy for Network Device Configuration Dump via Config Repositories](../../../../Defenses/Detection%20Strategies/DET0233%20-%20Detection%20Strategy%20for%20Network%20Device%20Configuration%20Dump%20via%20Config%20Repositories.md)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Configure SNMPv3 to use the highest level of security (authPriv) available.(Citation: US-CERT TA17-156A SNMP Abuse 2017) [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Apply extended ACLs to block unauthorized protocols outside the trusted network.(Citation: US-CERT TA17-156A SNMP Abuse 2017) [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Configure intrusion prevention devices to detect SNMP queries and commands from unauthorized sources. Create signatures to detect Smart Install (SMI) usage from sources other than trusted director.(Citation: US-CERT TA18-106A Network Infrastructure Devices 2018) [US-CERT TA18-106A Network Infrastructure Devices 2018](https://us-cert.cisa.gov/ncas/alerts/TA18-106A)
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Segregate SNMP traffic on a separate management network.(Citation: US-CERT TA17-156A SNMP Abuse 2017) [US-CERT TA17-156A SNMP Abuse 2017](https://us-cert.cisa.gov/ncas/alerts/TA17-156A)
- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Allowlist MIB objects and implement SNMP views. Disable Smart Install (SMI) if not used.(Citation: Cisco Securing SNMP)(Citation: US-CERT TA18-106A Network Infrastructure Devices 2018) [Cisco Securing SNMP](https://www.cisco.com/c/en/us/support/docs/ip/simple-network-management-protocol-snmp/20370-snmpsecurity-20370.html) · [US-CERT TA18-106A Network Infrastructure Devices 2018](https://us-cert.cisa.gov/ncas/alerts/TA18-106A)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Keep system images and software updated and migrate to SNMPv3.(Citation: Cisco Blog Legacy Device Attacks) [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)

## Sources

- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
- [US-CERT TA18-106A Network Infrastructure Devices 2018](https://us-cert.cisa.gov/ncas/alerts/TA18-106A)
- [US-CERT TA18-068A 2018](https://www.us-cert.gov/ncas/alerts/TA18-086A)
