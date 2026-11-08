# T1557.003 - DHCP Spoofing

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1557 - Adversary-in-the-Middle](../README.md)

Adversaries may redirect network traffic to adversary-owned systems by spoofing Dynamic Host Configuration Protocol (DHCP) traffic and acting as a malicious DHCP server on the victim network. By achieving the adversary-in-the-middle (AiTM) position, adversaries may collect network communications, including passed credentials, especially those sent over insecure, unencrypted protocols. This may also enable follow-on behaviors such as [Network Sniffing](https://attack.mitre.org/techniques/T1040) or [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1565/002).

DHCP is based on a client-server model and has two functionalities: a protocol for providing network configuration settings from a DHCP server to a client and a mechanism for allocating network addresses to clients.(Citation: rfc2131) The typical server-client interaction is as follows: 

1. The client broadcasts a `DISCOVER` message.

2. The server responds with an `OFFER` message, which includes an available network address. 

3. The client broadcasts a `REQUEST` message, which includes the network address offered. 

4. The server acknowledges with an `ACK` message and the client receives the network configuration parameters.

Adversaries may spoof as a rogue DHCP server on the victim network, from which legitimate hosts may receive malicious network configurations. For example, malware can act as a DHCP server and provide adversary-owned DNS servers to the victimized computers.(Citation: new_rogue_DHCP_serv_malware)(Citation: w32.tidserv.g) Through the malicious network configurations, an adversary may achieve the AiTM position, route client traffic through adversary-controlled systems, and collect information from the client network.

DHCPv6 clients can receive network configuration information without being assigned an IP address by sending an <code>INFORMATION-REQUEST (code 11)</code> message to the <code>All_DHCP_Relay_Agents_and_Servers</code> multicast address.(Citation: rfc3315) Adversaries may use their rogue DHCP server to respond to this request message with malicious network configurations.

Rather than establishing an AiTM position, adversaries may also abuse DHCP spoofing to perform a DHCP exhaustion attack (i.e., [Service Exhaustion Flood](https://attack.mitre.org/techniques/T1499/002)) by generating many broadcast DISCOVER messages to exhaust a network’s DHCP allocation pool.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1557/003)

**Tactics**  [Credential Access](../../README.md), [Collection](../../../12%20TA0009%20-%20Collection/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Consider filtering DHCP traffic on ports 67 and 68 to/from unknown or untrusted DHCP servers. Additionally, port security may also be enabled on layer switches. Furthermore, consider enabling DHCP snooping on layer 2 switches as it will prevent DHCP spoofing attacks and starvation attacks. Consider tracking available IP addresses through a script or a tool. Additionally, block DHCPv6 traffic and incoming router advertisements, especially if IPv6 is not commonly used in the network.(Citation: ntlm_relaying_kerberos_del) [ntlm_relaying_kerberos_del](https://dirkjanm.io/worst-of-both-worlds-ntlm-relaying-and-kerberos-delegation/)
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Network intrusion detection and prevention systems that can identify traffic patterns indicative of AiTM activity can be used to mitigate activity at the network level.(Citation: dhcp_serv_op_events) [dhcp_serv_op_events](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn800668%28v=ws.11%29)

## Detection strategies

- [DET0468 - Detect DHCP Spoofing Across Linux, Windows, and macOS](../../../../Defenses/Detection%20Strategies/DET0468%20-%20Detect%20DHCP%20Spoofing%20Across%20Linux%2C%20Windows%2C%20and%20macOS.md)

## Sources

- [rfc2131](https://datatracker.ietf.org/doc/html/rfc2131)
- [new_rogue_DHCP_serv_malware](https://isc.sans.edu/forums/diary/new+rogueDHCP+server+malware/6025/)
- [rfc3315](https://datatracker.ietf.org/doc/html/rfc3315)
- [w32.tidserv.g](https://web.archive.org/web/20150923175837/http://www.symantec.com/security_response/writeup.jsp?docid=2009-032211-2952-99&tabid=2)
