# C0053 - FLORAHOX Activity

[Enterprise](../../README.md) / [Campaigns](README.md)

[FLORAHOX Activity](https://attack.mitre.org/campaigns/C0053) is conducted using a hybrid operational relay box (ORB) network, which combines two types of infrastructure: compromised devices and leased Virtual Private Servers (VPS). The compromised devices include end-of-life routers and IoT devices, while VPS space is commercially leased and managed by ORB network administrators. This hybrid ORB network allows adversaries to proxy and obscure malicious traffic, making the source of the traffic more difficult to trace.

The FLORAHOX ORB network has been leveraged by multiple cyber threat actors, including China-nexus actors like [ZIRCONIUM](https://attack.mitre.org/groups/G0128). These adversaries conduct espionage campaigns through [FLORAHOX Activity](https://attack.mitre.org/campaigns/C0053), relying on the ORB network's ability to funnel traffic through [Tor](https://attack.mitre.org/software/S0183) nodes, provisioned VPS servers, and compromised routers to obfuscate malicious traffic.(Citation: ORB Mandiant)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0053)

## Techniques used

- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1584.008 - Network Devices](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/T1584.008%20-%20Network%20Devices/README.md)
- [T1059.004 - Unix Shell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.004%20-%20Unix%20Shell/README.md)
- [T1583.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.003%20-%20Virtual%20Private%20Server/README.md)

## Software used

- [S0183 - Tor](../Software/Tools/S0183%20-%20Tor.md)

## Sources

- [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)
