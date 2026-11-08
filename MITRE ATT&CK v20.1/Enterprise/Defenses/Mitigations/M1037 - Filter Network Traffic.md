# M1037 - Filter Network Traffic

[Enterprise](../../README.md) / [Mitigations](README.md)

Employ network appliances and endpoint software to filter ingress, egress, and lateral network traffic. This includes protocol-based filtering, enforcing firewall rules, and blocking or restricting traffic based on predefined conditions to limit adversary movement and data exfiltration. This mitigation can be implemented through the following measures:

Ingress Traffic Filtering:

- Use Case: Configure network firewalls to allow traffic only from authorized IP addresses to public-facing servers.
- Implementation: Limit SSH (port 22) and RDP (port 3389) traffic to specific IP ranges.

Egress Traffic Filtering:

- Use Case: Use firewalls or endpoint security software to block unauthorized outbound traffic to prevent data exfiltration and command-and-control (C2) communications.
- Implementation: Block outbound traffic to known malicious IPs or regions where communication is unexpected.

Protocol-Based Filtering:

- Use Case: Restrict the use of specific protocols that are commonly abused by adversaries, such as SMB, RPC, or Telnet, based on business needs.
- Implementation: Disable SMBv1 on endpoints to prevent exploits like EternalBlue.

Network Segmentation:

- Use Case: Create network segments for critical systems and restrict communication between segments unless explicitly authorized.
- Implementation: Implement VLANs to isolate IoT devices or guest networks from core business systems.

Application Layer Filtering:

- Use Case: Use proxy servers or Web Application Firewalls (WAFs) to inspect and block malicious HTTP/S traffic.
- Implementation: Configure a WAF to block SQL injection attempts or other web application exploitation techniques.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1037)

## Mitigated techniques

- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1696 - Anti-Automation Evasion](../../Tactics/07%20TA0005%20-%20Stealth/T1696%20-%20Anti-Automation%20Evasion/README.md)
- [T1499.003 - Application Exhaustion Flood](../../Tactics/15%20TA0040%20-%20Impact/T1499%20-%20Endpoint%20Denial%20of%20Service/T1499.003%20-%20Application%20Exhaustion%20Flood/README.md)
- [T1071 - Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/README.md)
- [T1499.004 - Application or System Exploitation](../../Tactics/15%20TA0040%20-%20Impact/T1499%20-%20Endpoint%20Denial%20of%20Service/T1499.004%20-%20Application%20or%20System%20Exploitation/README.md)
- [T1557.002 - ARP Cache Poisoning](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.002%20-%20ARP%20Cache%20Poisoning/README.md)
- [T1696.001 - Automate CAPTCHA Completion](../../Tactics/07%20TA0005%20-%20Stealth/T1696%20-%20Anti-Automation%20Evasion/T1696.001%20-%20Automate%20CAPTCHA%20Completion/README.md)
- [T1696.002 - Avoid CAPTCHA](../../Tactics/07%20TA0005%20-%20Stealth/T1696%20-%20Anti-Automation%20Evasion/T1696.002%20-%20Avoid%20CAPTCHA/README.md)
- [T1197 - BITS Jobs](../../Tactics/04%20TA0002%20-%20Execution/T1197%20-%20BITS%20Jobs/README.md)
- [T1552.005 - Cloud Instance Metadata API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.005%20-%20Cloud%20Instance%20Metadata%20API/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1602 - Data from Configuration Repository](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/README.md)
- [T1557.003 - DHCP Spoofing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.003%20-%20DHCP%20Spoofing/README.md)
- [T1498.001 - Direct Network Flood](../../Tactics/15%20TA0040%20-%20Impact/T1498%20-%20Network%20Denial%20of%20Service/T1498.001%20-%20Direct%20Network%20Flood/README.md)
- [T1071.004 - DNS](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.004%20-%20DNS/README.md)
- [T1499 - Endpoint Denial of Service](../../Tactics/15%20TA0040%20-%20Impact/T1499%20-%20Endpoint%20Denial%20of%20Service/README.md)
- [T1048 - Exfiltration Over Alternative Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/README.md)
- [T1048.002 - Exfiltration Over Asymmetric Encrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.002%20-%20Exfiltration%20Over%20Asymmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.001 - Exfiltration Over Symmetric Encrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.001%20-%20Exfiltration%20Over%20Symmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.003 - Exfiltration Over Unencrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.003%20-%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1071.002 - File Transfer Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.002%20-%20File%20Transfer%20Protocols/README.md)
- [T1187 - Forced Authentication](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1187%20-%20Forced%20Authentication/README.md)
- [T1105 - Ingress Tool Transfer](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1105%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1570 - Lateral Tool Transfer](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1570%20-%20Lateral%20Tool%20Transfer/README.md)
- [T1071.003 - Mail Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.003%20-%20Mail%20Protocols/README.md)
- [T1090.003 - Multi-hop Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/T1090.003%20-%20Multi-hop%20Proxy/README.md)
- [T1557.001 - Name Resolution Poisoning and SMB Relay](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.001%20-%20Name%20Resolution%20Poisoning%20and%20SMB%20Relay/README.md)
- [T1599.001 - Network Address Translation Traversal](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/T1599.001%20-%20Network%20Address%20Translation%20Traversal/README.md)
- [T1599 - Network Boundary Bridging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/README.md)
- [T1498 - Network Denial of Service](../../Tactics/15%20TA0040%20-%20Impact/T1498%20-%20Network%20Denial%20of%20Service/README.md)
- [T1602.002 - Network Device Configuration Dump](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.002%20-%20Network%20Device%20Configuration%20Dump/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1499.001 - OS Exhaustion Flood](../../Tactics/15%20TA0040%20-%20Impact/T1499%20-%20Endpoint%20Denial%20of%20Service/T1499.001%20-%20OS%20Exhaustion%20Flood/README.md)
- [T1205.001 - Port Knocking](../../Tactics/05%20TA0003%20-%20Persistence/T1205%20-%20Traffic%20Signaling/T1205.001%20-%20Port%20Knocking/README.md)
- [T1572 - Protocol Tunneling](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1572%20-%20Protocol%20Tunneling/README.md)
- [T1090 - Proxy](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1090%20-%20Proxy/README.md)
- [T1071.005 - Publish/Subscribe Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.005%20-%20Publish%20-%20Subscribe%20Protocols/README.md)
- [T1498.002 - Reflection Amplification](../../Tactics/15%20TA0040%20-%20Impact/T1498%20-%20Network%20Denial%20of%20Service/T1498.002%20-%20Reflection%20Amplification/README.md)
- [T1219 - Remote Access Tools](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/README.md)
- [T1219.002 - Remote Desktop Software](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1219%20-%20Remote%20Access%20Tools/T1219.002%20-%20Remote%20Desktop%20Software/README.md)
- [T1499.002 - Service Exhaustion Flood](../../Tactics/15%20TA0040%20-%20Impact/T1499%20-%20Endpoint%20Denial%20of%20Service/T1499.002%20-%20Service%20Exhaustion%20Flood/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1602.001 - SNMP (MIB Dump)](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.001%20-%20SNMP%20%28MIB%20Dump%29/README.md)
- [T1205.002 - Socket Filters](../../Tactics/05%20TA0003%20-%20Persistence/T1205%20-%20Traffic%20Signaling/T1205.002%20-%20Socket%20Filters/README.md)
- [T1218 - System Binary Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1205 - Traffic Signaling](../../Tactics/05%20TA0003%20-%20Persistence/T1205%20-%20Traffic%20Signaling/README.md)
- [T1537 - Transfer Data to Cloud Account](../../Tactics/14%20TA0010%20-%20Exfiltration/T1537%20-%20Transfer%20Data%20to%20Cloud%20Account/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1218.012 - Verclsid](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.012%20-%20Verclsid/README.md)
- [T1021.005 - VNC](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.005%20-%20VNC/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)
