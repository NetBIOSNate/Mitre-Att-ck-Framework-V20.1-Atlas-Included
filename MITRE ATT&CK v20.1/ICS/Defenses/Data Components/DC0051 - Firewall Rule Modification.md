# DC0051 - Firewall Rule Modification

[ICS](../../README.md) / [Data Components](README.md)

The creation, deletion, or alteration of firewall rules to allow or block specific network traffic. Monitoring changes to these rules is critical for detecting misconfigurations, unauthorized access, or malicious attempts to bypass network protections. Examples: 

- Rule Creation: Adding a new rule to allow inbound traffic on port 3389 (RDP).
- Rule Deletion: Deleting a rule that blocks inbound traffic from untrusted IP ranges.
- Rule Modification: Changing a rule to allow traffic from "any" source IP instead of a specific trusted range.
- Audit Log Metadata: Logs indicating "Firewall rule modified by admin@domain.com."
- Platform-Specific Scenarios
    - Azure: Altering rules in an Azure Network Security Group (NSG).
    - AWS: Modifying Security Group rules to allow traffic.
    - Windows: Changes tracked in Security Event Logs (EID 4950 or 4951).

This data component can be collected through the following measures:

Cloud Control Plane

- Azure: Collect rule modification logs from Azure Firewall Activity Logs.
    - Example Command: `az network firewall policy rule-collection-group rule-collection list --policy-name <policy-name>`
- AWS: Use CloudTrail to track `AuthorizeSecurityGroupIngress` or `RevokeSecurityGroupIngress` actions.
    Example: `aws ec2 describe-security-groups`
- Google Cloud: Use gcloud commands to extract firewall rules: `gcloud compute firewall-rules list --format=json`

Host-Based Firewalls

- Windows: 
    - Collect events from the Windows Security Event Log (EID 4950: A rule has been modified).
    - Use PowerShell to track rule changes: `Get-NetFirewallRule -PolicyStore PersistentStore`
- Linux:
    - Monitor iptables or nftables rule modifications: `iptables -L -v`
    - Use auditd for real-time monitoring: `auditctl -w /etc/iptables.rules -p wa`
- macOS: Use pfctl to monitor rule changes: `sudo pfctl -sr`

SIEM Integration

- Collect logs from cloud platforms, host systems, and network appliances for centralized monitoring.

API Monitoring

- Monitor API calls for firewall rule modifications.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0051)

## Log sources and channels

- **AWS:CloudTrail** — AuthorizeSecurityGroupIngress
- **AWS:CloudTrail** — Create egress rule allowing UDP to port 53, 123, 11211
- **AWS:CloudTrail** — Ingress rule creation or modification for security group
- **AWS:CloudTrail** — New security group created with permissive rules
- **esxi:hostd** — vSphere API calls modifying firewall settings
- **Firewall Audit Logs** — Config Change
- **Firewall Audit Logs** — Outbound NAT Rule Changes
- **linux:syslog** — iptables or nftables rule changes
- **networkdevice:cli** — firewall disable commands or suspicious ACL modifications
- **networkdevice:Firewall** — update_rule: Access control or NAT rule modified or disabled outside maintenance window
- **NSM:Firewall** — Policy Change / Rule Update
- **NSM:Firewall** — rule_modification: New or modified firewall rules related to wireless interfaces
- **WinEventLog:Microsoft-Windows-Windows Firewall With Advanced Security/Firewall** — new rule allowing inbound or outbound connections for remote desktop software
- **WinEventLog:Security** — Firewall Rule Modification
- **WinEventLog:Security** — Windows Security Windows Filtering Platform / Firewall audit events (policy-dependent): firewall rule change blocking unsolicited Industrial Control Systems (ICS) reporting traffic while command/polling traffic continues
- **WinEventLog:Security** — Windows Security Windows Filtering Platform / Firewall audit events (policy-dependent): firewall rule change selectively blocking one Industrial Control Systems (ICS) traffic type from Supervisory Control and Data Acquisition (SCADA)/Distributed Control System (DCS) host without corresponding change ticket

## Analytics using this component

- [AN2264 - Analytic 2264](../Analytics/AN2264.md)
- [AN2266 - Analytic 2266](../Analytics/AN2266.md)
