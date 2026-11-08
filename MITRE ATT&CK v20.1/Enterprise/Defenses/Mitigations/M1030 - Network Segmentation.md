# M1030 - Network Segmentation

[Enterprise](../../README.md) / [Mitigations](README.md)

Network segmentation involves dividing a network into smaller, isolated segments to control and limit the flow of traffic between devices, systems, and applications. By segmenting networks, organizations can reduce the attack surface, restrict lateral movement by adversaries, and protect critical assets from compromise.

Effective network segmentation leverages a combination of physical boundaries, logical separation through VLANs, and access control policies enforced by network appliances like firewalls, routers, and cloud-based configurations. This mitigation can be implemented through the following measures:

Segment Critical Systems:

- Identify and group systems based on their function, sensitivity, and risk. Examples include payment systems, HR databases, production systems, and internet-facing servers.
- Use VLANs, firewalls, or routers to enforce logical separation.

Implement DMZ for Public-Facing Services:

- Host web servers, DNS servers, and email servers in a DMZ to limit their access to internal systems.
- Apply strict firewall rules to filter traffic between the DMZ and internal networks.

Use Cloud-Based Segmentation:

- In cloud environments, use VPCs, subnets, and security groups to isolate applications and enforce traffic rules.
- Apply AWS Transit Gateway or Azure VNet peering for controlled connectivity between cloud segments.

Apply Microsegmentation for Workloads:

- Use software-defined networking (SDN) tools to implement workload-level segmentation and prevent lateral movement.

Restrict Traffic with ACLs and Firewalls:

- Apply Access Control Lists (ACLs) to network devices to enforce "deny by default" policies.
- Use firewalls to restrict both north-south (external-internal) and east-west (internal-internal) traffic.

Monitor and Audit Segmented Networks:

- Regularly review firewall rules, ACLs, and segmentation policies.
- Monitor network flows for anomalies to ensure segmentation is effective.

Test Segmentation Effectiveness:

- Perform periodic penetration tests to verify that unauthorized access is blocked between network segments.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1030)

## Mitigated techniques

- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1098.001 - Additional Cloud Credentials](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.001%20-%20Additional%20Cloud%20Credentials/README.md)
- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1612 - Build Image on Host](../../Tactics/07%20TA0005%20-%20Stealth/T1612%20-%20Build%20Image%20on%20Host/README.md)
- [T1136.003 - Cloud Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.003%20-%20Cloud%20Account/README.md)
- [T1613 - Container and Resource Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1613%20-%20Container%20and%20Resource%20Discovery/README.md)
- [T1552.007 - Container API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.007%20-%20Container%20API/README.md)
- [T1136 - Create Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md)
- [T1602 - Data from Configuration Repository](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/README.md)
- [T1565 - Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/README.md)
- [T1610 - Deploy Container](../../Tactics/04%20TA0002%20-%20Execution/T1610%20-%20Deploy%20Container/README.md)
- [T1021.003 - Distributed Component Object Model](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.003%20-%20Distributed%20Component%20Object%20Model/README.md)
- [T1136.002 - Domain Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1482 - Domain Trust Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1482%20-%20Domain%20Trust%20Discovery/README.md)
- [T1048 - Exfiltration Over Alternative Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/README.md)
- [T1048.002 - Exfiltration Over Asymmetric Encrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.002%20-%20Exfiltration%20Over%20Asymmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.001 - Exfiltration Over Symmetric Encrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.001%20-%20Exfiltration%20Over%20Symmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.003 - Exfiltration Over Unencrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.003%20-%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1210 - Exploitation of Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1698 - Indirect Prompt Injection](../../Tactics/04%20TA0002%20-%20Execution/T1698%20-%20Indirect%20Prompt%20Injection/README.md)
- [T1557.001 - Name Resolution Poisoning and SMB Relay](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.001%20-%20Name%20Resolution%20Poisoning%20and%20SMB%20Relay/README.md)
- [T1602.002 - Network Device Configuration Dump](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.002%20-%20Network%20Device%20Configuration%20Dump/README.md)
- [T1046 - Network Service Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1046%20-%20Network%20Service%20Discovery/README.md)
- [T1040 - Network Sniffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1095 - Non-Application Layer Protocol](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1095%20-%20Non-Application%20Layer%20Protocol/README.md)
- [T1571 - Non-Standard Port](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1563 - Remote Service Session Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/README.md)
- [T1565.003 - Runtime Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/T1565.003%20-%20Runtime%20Data%20Manipulation/README.md)
- [T1489 - Service Stop](../../Tactics/15%20TA0040%20-%20Impact/T1489%20-%20Service%20Stop/README.md)
- [T1602.001 - SNMP (MIB Dump)](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.001%20-%20SNMP%20%28MIB%20Dump%29/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1199 - Trusted Relationship](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1199%20-%20Trusted%20Relationship/README.md)
- [T1669 - Wi-Fi Networks](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1669%20-%20Wi-Fi%20Networks/README.md)
- [T1021.006 - Windows Remote Management](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.006%20-%20Windows%20Remote%20Management/README.md)
