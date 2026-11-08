# M0814 - Static Network Configuration

[ICS](../../README.md) / [Mitigations](README.md)

Configure hosts and devices to use static network configurations when possible, protocols that require dynamic discovery/addressing (e.g., ARP, DHCP, DNS) can be used to manipulate network message forwarding and enable various AiTM attacks. This mitigation may not always be usable due to limited device features or challenges introduced with different network configurations.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M0814)

## Mitigated techniques

- [T0830 - Adversary-in-the-Middle](../../Tactics/08%20TA0100%20-%20Collection/T0830%20-%20Adversary-in-the-Middle/README.md)
- [T0878 - Alarm Suppression](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T0878%20-%20Alarm%20Suppression/README.md)
- [T1691 - Block Operational Technology Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/README.md)
- [T0846.002 - Broadcast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.002%20-%20Broadcast%20Discovery/README.md)
- [T1691.001 - Command Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/T1691.001%20-%20Command%20Message/README.md)
- [T0846.003 - Multicast Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.003%20-%20Multicast%20Discovery/README.md)
- [T0842 - Network Sniffing](../../Tactics/06%20TA0102%20-%20Discovery/T0842%20-%20Network%20Sniffing/README.md)
- [T0846.001 - Port Scan](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/T0846.001%20-%20Port%20Scan/README.md)
- [T0846 - Remote System Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0846%20-%20Remote%20System%20Discovery/README.md)
- [T0888 - Remote System Information Discovery](../../Tactics/06%20TA0102%20-%20Discovery/T0888%20-%20Remote%20System%20Information%20Discovery/README.md)
- [T1691.002 - Reporting Message](../../Tactics/10%20TA0107%20-%20Inhibit%20Response%20Function/T1691%20-%20Block%20Operational%20Technology%20Message/T1691.002%20-%20Reporting%20Message/README.md)
