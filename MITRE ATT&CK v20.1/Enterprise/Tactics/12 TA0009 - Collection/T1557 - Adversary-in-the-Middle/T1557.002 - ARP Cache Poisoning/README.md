# T1557.002 - ARP Cache Poisoning

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1557 - Adversary-in-the-Middle](../README.md)

Adversaries may poison Address Resolution Protocol (ARP) caches to position themselves between the communication of two or more networked devices. This activity may be used to enable follow-on behaviors such as [Network Sniffing](https://attack.mitre.org/techniques/T1040) or [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1565/002).

The ARP protocol is used to resolve IPv4 addresses to link layer addresses, such as a media access control (MAC) address.(Citation: RFC826 ARP) Devices in a local network segment communicate with each other by using link layer addresses. If a networked device does not have the link layer address of a particular networked device, it may send out a broadcast ARP request to the local network to translate the IP address to a MAC address. The device with the associated IP address directly replies with its MAC address. The networked device that made the ARP request will then use as well as store that information in its ARP cache.

An adversary may passively wait for an ARP request to poison the ARP cache of the requesting device. The adversary may reply with their MAC address, thus deceiving the victim by making them believe that they are communicating with the intended networked device. For the adversary to poison the ARP cache, their reply must be faster than the one made by the legitimate IP address owner. Adversaries may also send a gratuitous ARP reply that maliciously announces the ownership of a particular IP address to all the devices in the local network segment.

The ARP protocol is stateless and does not require authentication. Therefore, devices may wrongly add or update the MAC address of the IP address in their ARP cache.(Citation: Sans ARP Spoofing Aug 2003)(Citation: Cylance Cleaver)

Adversaries may use ARP cache poisoning as a means to intercept network traffic. This activity may be used to collect and/or relay data such as credentials, especially those sent over an insecure, unencrypted protocol.(Citation: Sans ARP Spoofing Aug 2003)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1557/002)

**Tactics**  [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md), [Collection](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider disabling updating the ARP cache on gratuitous ARP replies.
- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Ensure that all wired and/or wireless traffic is encrypted appropriately. Use best practices for authentication protocols, such as Kerberos, and ensure web traffic that may contain credentials is protected by SSL/TLS.
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Consider enabling DHCP Snooping and Dynamic ARP Inspection on switches to create mappings between IP addresses requested via DHCP and ARP tables and tie the values to a port on the switch that may block bogus traffic.(Citation: Cisco ARP Poisoning Mitigation 2016)(Citation: Juniper DAI 2020) [Cisco ARP Poisoning Mitigation 2016](https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-6500-series-switches/white_paper_c11_603839.html) · [Juniper DAI 2020](https://www.juniper.net/documentation/en_US/junos/topics/task/configuration/understanding-and-using-dai.html)
- [M1035 - Limit Access to Resource Over Network](../../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Create static ARP entries for networked devices. Implementing static ARP entries may be infeasible for large networks.
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that can identify traffic patterns indicative of AiTM activity can be used to mitigate activity at the network level.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to be suspicious about certificate errors. Adversaries may use their own certificates in an attempt to intercept HTTPS traffic. Certificate errors may arise when the application’s certificate does not match the one expected by the host.

## Procedure examples

- [G0003 - Cleaver](../../../../Threat%20Intelligence/Groups/G0003%20-%20Cleaver.md) — [Cleaver](https://attack.mitre.org/groups/G0003) has used custom tools to facilitate ARP cache poisoning.(Citation: Cylance Cleaver) [Cylance Cleaver](https://web.archive.org/web/20200302085133/https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf)
- [G1014 - LuminousMoth](../../../../Threat%20Intelligence/Groups/G1014%20-%20LuminousMoth.md) — [LuminousMoth](https://attack.mitre.org/groups/G1014) has used ARP spoofing to redirect a compromised machine to an actor-controlled website.(Citation: Bitdefender LuminousMoth July 2021) [Bitdefender LuminousMoth July 2021](https://www.bitdefender.com/blog/labs/luminousmoth-plugx-file-exfiltration-and-persistence-revisited)

## Detection strategies

- [DET0387 - Detect ARP Cache Poisoning Across Linux, Windows, and macOS](../../../../Defenses/Detection%20Strategies/DET0387%20-%20Detect%20ARP%20Cache%20Poisoning%20Across%20Linux%2C%20Windows%2C%20and%20macOS.md)

## Sources

- [Cylance Cleaver](https://web.archive.org/web/20200302085133/https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf)
- [RFC826 ARP](https://tools.ietf.org/html/rfc826)
- [Sans ARP Spoofing Aug 2003](https://pen-testing.sans.org/resources/papers/gcih/real-world-arp-spoofing-105411)
