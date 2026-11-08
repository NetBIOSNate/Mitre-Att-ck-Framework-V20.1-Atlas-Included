# M1041 - Encrypt Sensitive Information

[Enterprise](../../README.md) / [Mitigations](README.md)

Protect sensitive information at rest, in transit, and during processing by using strong encryption algorithms. Encryption ensures the confidentiality and integrity of data, preventing unauthorized access or tampering. This mitigation can be implemented through the following measures:

Encrypt Data at Rest:

- Use Case: Use full-disk encryption or file-level encryption to secure sensitive data stored on devices.
- Implementation: Implement BitLocker for Windows systems or FileVault for macOS devices to encrypt hard drives.

Encrypt Data in Transit:

- Use Case: Use secure communication protocols (e.g., TLS, HTTPS) to encrypt sensitive data as it travels over networks.
- Implementation: Enable HTTPS for all web applications and configure mail servers to enforce STARTTLS for email encryption.

Encrypt Backups:

- Use Case: Ensure that backup data is encrypted both during storage and transfer to prevent unauthorized access.
- Implementation: Encrypt cloud backups using AES-256 before uploading them to Amazon S3 or Google Cloud.

Encrypt Application Secrets:

- Use Case: Store sensitive credentials, API keys, and configuration files in encrypted vaults.
- Implementation: Use HashiCorp Vault or AWS Secrets Manager to manage and encrypt secrets.

Database Encryption:

- Use Case: Enable Transparent Data Encryption (TDE) or column-level encryption in database management systems.
- Implementation: Use MySQL’s built-in encryption features to encrypt sensitive database fields such as social security numbers.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1041)

## Mitigated techniques

- [T1557 - Adversary-in-the-Middle](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/README.md)
- [T1550.001 - Application Access Token](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1557.002 - ARP Cache Poisoning](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1557%20-%20Adversary-in-the-Middle/T1557.002%20-%20ARP%20Cache%20Poisoning/README.md)
- [T1558.004 - AS-REP Roasting](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.004%20-%20AS-REP%20Roasting/README.md)
- [T1119 - Automated Collection](../../Tactics/12%20TA0009%20-%20Collection/T1119%20-%20Automated%20Collection/README.md)
- [T1685.006 - Clear Linux or Mac System Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.006%20-%20Clear%20Linux%20or%20Mac%20System%20Logs/README.md)
- [T1685.005 - Clear Windows Event Logs](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/T1685.005%20-%20Clear%20Windows%20Event%20Logs/README.md)
- [T1659 - Content Injection](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1659%20-%20Content%20Injection/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1602 - Data from Configuration Repository](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/README.md)
- [T1213 - Data from Information Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/README.md)
- [T1565 - Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1114 - Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/README.md)
- [T1114.003 - Email Forwarding Rule](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.003%20-%20Email%20Forwarding%20Rule/README.md)
- [T1070 - Indicator Removal](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/README.md)
- [T1558.003 - Kerberoasting](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.003%20-%20Kerberoasting/README.md)
- [T1114.001 - Local Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1602.002 - Network Device Configuration Dump](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.002%20-%20Network%20Device%20Configuration%20Dump/README.md)
- [T1040 - Network Sniffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1003.003 - NTDS](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/T1003.003%20-%20NTDS/README.md)
- [T1003 - OS Credential Dumping](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1003%20-%20OS%20Credential%20Dumping/README.md)
- [T1552.004 - Private Keys](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/T1552.004%20-%20Private%20Keys/README.md)
- [T1114.002 - Remote Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.002%20-%20Remote%20Email%20Collection/README.md)
- [T1558.002 - Silver Ticket](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/T1558.002%20-%20Silver%20Ticket/README.md)
- [T1602.001 - SNMP (MIB Dump)](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.001%20-%20SNMP%20%28MIB%20Dump%29/README.md)
- [T1649 - Steal or Forge Authentication Certificates](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1649%20-%20Steal%20or%20Forge%20Authentication%20Certificates/README.md)
- [T1558 - Steal or Forge Kerberos Tickets](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1558%20-%20Steal%20or%20Forge%20Kerberos%20Tickets/README.md)
- [T1565.001 - Stored Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/T1565.001%20-%20Stored%20Data%20Manipulation/README.md)
- [T1020.001 - Traffic Duplication](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/T1020.001%20-%20Traffic%20Duplication/README.md)
- [T1565.002 - Transmitted Data Manipulation](../../Tactics/15%20TA0040%20-%20Impact/T1565%20-%20Data%20Manipulation/T1565.002%20-%20Transmitted%20Data%20Manipulation/README.md)
- [T1552 - Unsecured Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md)
- [T1669 - Wi-Fi Networks](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1669%20-%20Wi-Fi%20Networks/README.md)
