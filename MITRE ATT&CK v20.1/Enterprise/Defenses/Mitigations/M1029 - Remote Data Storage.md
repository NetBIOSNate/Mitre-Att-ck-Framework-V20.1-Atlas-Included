# M1029 - Remote Data Storage

[Enterprise](../../README.md) / [Mitigations](README.md)

Remote Data Storage focuses on moving critical data, such as security logs and sensitive files, to secure, off-host locations to minimize unauthorized access, tampering, or destruction by adversaries. By leveraging remote storage solutions, organizations enhance the protection of forensic evidence, sensitive information, and monitoring data. This mitigation can be implemented through the following measures:

Centralized Log Management:

- Configure endpoints to forward security logs to a centralized log collector or SIEM.
- Use tools like Splunk Graylog, or Security Onion to aggregate and store logs.
- Example command (Linux): `sudo auditd | tee /var/log/audit/audit.log | nc <remote-log-server> 514`

Remote File Storage Solutions:

- Utilize cloud storage solutions like AWS S3, Google Cloud Storage, or Azure Blob Storage for sensitive data.
- Ensure proper encryption at rest and access control policies (IAM roles, ACLs).

Intrusion Detection Log Forwarding:

- Forward logs from IDS/IPS systems (e.g., Zeek/Suricata) to a remote security information system.
- Example for Suricata log forwarding:
`outputs:
  - type: syslog
    protocol: tls
    address: <remote-syslog-server>`

Immutable Backup Configurations:

- Enable immutable storage settings for backups to prevent adversaries from modifying or deleting data.
- Example: AWS S3 Object Lock.

Data Encryption:

- Ensure encryption for sensitive data using AES-256 at rest and TLS 1.2+ for data in transit.
Tools: OpenSSL, BitLocker, LUKS for Linux.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1029)

## Mitigated techniques

- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1070.003 - Clear Command History](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.003%20-%20Clear%20Command%20History/README.md)
- [T1685.006 - Clear Linux or Mac System Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.006%20-%20Clear%20Linux%20or%20Mac%20System%20Logs/README.md)
- [T1070.008 - Clear Mailbox Data](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.008%20-%20Clear%20Mailbox%20Data/README.md)
- [T1070.007 - Clear Network Connection History and Configurations](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.007%20-%20Clear%20Network%20Connection%20History%20and%20Configurations/README.md)
- [T1070.009 - Clear Persistence](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.009%20-%20Clear%20Persistence/README.md)
- [T1685.005 - Clear Windows Event Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1565 - Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/README.md)
- [T1070 - Indicator Removal](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1565.001 - Stored Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/T1565.001%20-%20Stored%20Data%20Manipulation/README.md)
