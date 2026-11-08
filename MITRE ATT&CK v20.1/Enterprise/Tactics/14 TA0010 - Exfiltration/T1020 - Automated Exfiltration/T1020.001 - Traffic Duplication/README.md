# T1020.001 - Traffic Duplication

[Enterprise](../../../../README.md) / [Exfiltration](../../README.md) / [T1020 - Automated Exfiltration](../README.md)

Adversaries may leverage traffic mirroring in order to automate data exfiltration over compromised infrastructure. Traffic mirroring is a native feature for some devices, often used for network analysis. For example, devices may be configured to forward network traffic to one or more destinations for analysis by a network analyzer or other monitoring device.(Citation: Cisco Traffic Mirroring)(Citation: Juniper Traffic Mirroring)

Adversaries may abuse traffic mirroring to mirror or redirect network traffic through other infrastructure they control. Malicious modifications to network devices to enable traffic redirection may be possible through [ROMMONkit](https://attack.mitre.org/techniques/T1542/004) or [Patch System Image](https://attack.mitre.org/techniques/T1601/001).(Citation: US-CERT-TA18-106A)(Citation: Cisco Blog Legacy Device Attacks)

Many cloud-based environments also support traffic mirroring. For example, AWS Traffic Mirroring, GCP Packet Mirroring, and Azure vTap allow users to define specified instances to collect traffic from and specified targets to send collected traffic to.(Citation: AWS Traffic Mirroring)(Citation: GCP Packet Mirroring)(Citation: Azure Virtual Network TAP)

Adversaries may use traffic duplication in conjunction with [Network Sniffing](https://attack.mitre.org/techniques/T1040), [Input Capture](https://attack.mitre.org/techniques/T1056), or [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) depending on the goals and objectives of the adversary.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1020/001)

**Tactics**  [Exfiltration](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md), [IaaS](../../../../Platforms/IaaS.md)

## Procedure examples

- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has enabled traffic mirroring to exfiltrate data.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)

## Detection strategies

- [DET0403 - Detection Strategy for Traffic Duplication via Mirroring in IaaS and Network Devices](../../../../Defenses/Detection%20Strategies/DET0403%20-%20Detection%20Strategy%20for%20Traffic%20Duplication%20via%20Mirroring%20in%20IaaS%20and%20Network%20Devices.md)

## Mitigations

- [M1057 - Data Loss Prevention](../../../../Defenses/Mitigations/M1057%20-%20Data%20Loss%20Prevention.md) — Implement Data Loss Prevention (DLP) solutions to monitor, detect, and control the flow of sensitive information. DLP tools can be configured to block unauthorized attempts to exfiltrate data, such as preventing emails from being forwarded to external recipients or monitoring for suspicious data transfers. By creating email flow rules and applying policies to detect anomalies, DLP solutions help mitigate the risk of data exfiltration over alternative protocols.
- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Ensure that all wired and/or wireless traffic is encrypted appropriately. Use best practices for authentication protocols, such as Kerberos, and ensure web traffic that may contain credentials is protected by SSL/TLS.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — In cloud environments, ensure that users are not granted permissions to create or modify traffic mirrors unless this is explicitly required.

## Sources

- [AWS Traffic Mirroring](https://docs.aws.amazon.com/vpc/latest/mirroring/traffic-mirroring-how-it-works.html)
- [Cisco Traffic Mirroring](https://www.cisco.com/c/en/us/td/docs/routers/crs/software/crs_r5-1/interfaces/configuration/guide/hc51xcrsbook/hc51span.html)
- [GCP Packet Mirroring](https://cloud.google.com/vpc/docs/packet-mirroring)
- [Juniper Traffic Mirroring](https://www.juniper.net/documentation/en_US/junos/topics/concept/port-mirroring-ex-series.html)
- [Azure Virtual Network TAP](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-tap-overview)
- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
- [US-CERT-TA18-106A](https://www.us-cert.gov/ncas/alerts/TA18-106A)
