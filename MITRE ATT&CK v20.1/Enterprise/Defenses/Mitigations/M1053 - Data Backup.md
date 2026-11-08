# M1053 - Data Backup

[Enterprise](../../README.md) / [Mitigations](README.md)

Data Backup involves taking and securely storing backups of data from end-user systems and critical servers. It ensures that data remains available in the event of system compromise, ransomware attacks, or other disruptions. Backup processes should include hardening backup systems, implementing secure storage solutions, and keeping backups isolated from the corporate network to prevent compromise during active incidents. This mitigation can be implemented through the following measures:

Regular Backup Scheduling:
- Use Case: Ensure timely and consistent backups of critical data.
- Implementation: Schedule daily incremental backups and weekly full backups for all critical servers and systems.

Immutable Backups:
- Use Case: Protect backups from modification or deletion, even by attackers.
- Implementation: Use write-once-read-many (WORM) storage for backups, preventing ransomware from encrypting or deleting backup files.

Backup Encryption:
- Use Case: Protect data integrity and confidentiality during transit and storage.
- Implementation: Encrypt backups using strong encryption protocols (e.g., AES-256) before storing them in local, cloud, or remote locations.

Offsite Backup Storage:
- Use Case: Ensure data availability during physical disasters or onsite breaches.
- Implementation: Use cloud-based solutions like AWS S3, Azure Backup, or physical offsite storage to maintain a copy of critical data.

Backup Testing:
- Use Case: Validate backup integrity and ensure recoverability.
- Implementation: Regularly test data restoration processes to ensure that backups are not corrupted and can be recovered quickly.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1053)

## Mitigated techniques

- [T1485 - Data Destruction](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/README.md)
- [T1486 - Data Encrypted for Impact](../../Tactics/15%20TA0040%20-%20Impact/T1486%20-%20Data%20Encrypted%20for%20Impact/README.md)
- [T1491 - Defacement](../../Tactics/15%20TA0040%20-%20Impact/T1491%20-%20Defacement/README.md)
- [T1561.001 - Disk Content Wipe](../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.001%20-%20Disk%20Content%20Wipe/README.md)
- [T1561.002 - Disk Structure Wipe](../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/T1561.002%20-%20Disk%20Structure%20Wipe/README.md)
- [T1561 - Disk Wipe](../../Tactics/15%20TA0040%20-%20Impact/T1561%20-%20Disk%20Wipe/README.md)
- [T1491.002 - External Defacement](../../Tactics/15%20TA0040%20-%20Impact/T1491%20-%20Defacement/T1491.002%20-%20External%20Defacement/README.md)
- [T1490 - Inhibit System Recovery](../../Tactics/15%20TA0040%20-%20Impact/T1490%20-%20Inhibit%20System%20Recovery/README.md)
- [T1491.001 - Internal Defacement](../../Tactics/15%20TA0040%20-%20Impact/T1491%20-%20Defacement/T1491.001%20-%20Internal%20Defacement/README.md)
- [T1485.001 - Lifecycle-Triggered Deletion](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/T1485.001%20-%20Lifecycle-Triggered%20Deletion/README.md)
