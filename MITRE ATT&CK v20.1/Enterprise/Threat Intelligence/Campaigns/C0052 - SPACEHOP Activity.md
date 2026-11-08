# C0052 - SPACEHOP Activity

[Enterprise](../../README.md) / [Campaigns](README.md)

[SPACEHOP Activity](https://attack.mitre.org/campaigns/C0052) is conducted through commercially leased Virtual Private Servers (VPS), otherwise known as provisioned Operational Relay Box (ORB) networks. The network leveraged for SPACEHOP Activity enabled China-nexus cyber threat actors – such as [APT5](https://attack.mitre.org/groups/G1023) and [Ke3chang](https://attack.mitre.org/groups/G0004) – to perform network reconnaissance scanning and vulnerability exploitation. SPACEHOP Activity has historically targeted entities in North America, Europe, and the Middle East.(Citation: ORB Mandiant)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0052)

## Techniques used

- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1588.002 - Tool](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.002%20-%20Tool/README.md)
- [T1583.003 - Virtual Private Server](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.003%20-%20Virtual%20Private%20Server/README.md)

## Attributed groups

- [G1023 - APT5](../Groups/G1023%20-%20APT5.md)
- [G0004 - Ke3chang](../Groups/G0004%20-%20Ke3chang.md)

## Sources

- [ORB Mandiant](https://cloud.google.com/blog/topics/threat-intelligence/china-nexus-espionage-orb-networks)
