# M1035 - Limit Access to Resource Over Network

[Enterprise](../../README.md) / [Mitigations](README.md)

Restrict access to network resources, such as file shares, remote systems, and services, to only those users, accounts, or systems with a legitimate business requirement. This can include employing technologies like network concentrators, RDP gateways, and zero-trust network access (ZTNA) models, alongside hardening services and protocols. This mitigation can be implemented through the following measures:

Audit and Restrict Access:

- Regularly audit permissions for file shares, network services, and remote access tools.
- Remove unnecessary access and enforce least privilege principles for users and services.
- Use Active Directory and IAM tools to restrict access based on roles and attributes.

Deploy Secure Remote Access Solutions:

- Use RDP gateways, VPN concentrators, and ZTNA solutions to aggregate and secure remote access connections.
- Configure access controls to restrict connections based on time, device, and user identity.
- Enforce MFA for all remote access mechanisms.

Disable Unnecessary Services:

- Identify running services using tools like netstat (Windows/Linux) or Nmap.
- Disable unused services, such as Telnet, FTP, and legacy SMB, to reduce the attack surface.
- Use firewall rules to block traffic on unused ports and protocols.

Network Segmentation and Isolation:

- Use VLANs, firewalls, or micro-segmentation to isolate critical network resources from general access.
- Restrict communication between subnets to prevent lateral movement.

Monitor and Log Access:

- Monitor access attempts to file shares, RDP, and remote network resources using SIEM tools.
- Enable auditing and logging for successful and failed attempts to access restricted resources.

*Tools for Implementation*

File Share Management:

- Microsoft Active Directory Group Policies
- Samba (Linux/Unix file share management)
- AccessEnum (Windows access auditing tool)

Secure Remote Access:

- Microsoft Remote Desktop Gateway
- Apache Guacamole (open-source RDP/VNC gateway)
- Zero Trust solutions: Tailscale, Cloudflare Zero Trust

Service and Protocol Hardening:

- Nmap or Nessus for network service discovery
- Windows Group Policy Editor for disabling SMBv1, Telnet, and legacy protocols
- iptables or firewalld (Linux) for blocking unnecessary traffic

Network Segmentation:

- pfSense for open-source network isolation

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1035)

## Mitigated techniques

- [T1546.008 - Accessibility Features](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.008%20-%20Accessibility%20Features/README.md)
- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1557.002 - ARP Cache Poisoning](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.002%20-%20ARP%20Cache%20Poisoning/README.md)
- [T1612 - Build Image on Host](../../Tactics/07%20TA0005%20-%20Stealth/T1612%20-%20Build%20Image%20on%20Host/README.md)
- [T1552.005 - Cloud Instance Metadata API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.005%20-%20Cloud%20Instance%20Metadata%20API/README.md)
- [T1609 - Container Administration Command](../../Tactics/04%20TA0002%20-%20Execution/T1609%20-%20Container%20Administration%20Command/README.md)
- [T1613 - Container and Resource Discovery](../../Tactics/10%20TA0007%20-%20Discovery/T1613%20-%20Container%20and%20Resource%20Discovery/README.md)
- [T1552.007 - Container API](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.007%20-%20Container%20API/README.md)
- [T1610 - Deploy Container](../../Tactics/04%20TA0002%20-%20Execution/T1610%20-%20Deploy%20Container/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1200 - Hardware Additions](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1200%20-%20Hardware%20Additions/README.md)
- [T1542 - Pre-OS Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/README.md)
- [T1563.002 - RDP Hijacking](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1563%20-%20Remote%20Service%20Session%20Hijacking/T1563.002%20-%20RDP%20Hijacking/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1021 - Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1021.002 - SMB/Windows Admin Shares](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.002%20-%20SMB%20-%20Windows%20Admin%20Shares/README.md)
- [T1542.005 - TFTP Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.005%20-%20TFTP%20Boot/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
