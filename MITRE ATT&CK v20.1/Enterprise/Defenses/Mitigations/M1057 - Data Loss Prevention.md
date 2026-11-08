# M1057 - Data Loss Prevention

[Enterprise](../../README.md) / [Mitigations](README.md)

Data Loss Prevention (DLP) involves implementing strategies and technologies to identify, categorize, monitor, and control the movement of sensitive data within an organization. This includes protecting data formats indicative of Personally Identifiable Information (PII), intellectual property, or financial data from unauthorized access, transmission, or exfiltration. DLP solutions integrate with network, endpoint, and cloud platforms to enforce security policies and prevent accidental or malicious data leaks. (Citation: PurpleSec Data Loss Prevention) This mitigation can be implemented through the following measures:

Sensitive Data Categorization:

- Use Case: Identify and classify data based on sensitivity (e.g., PII, financial data, trade secrets).
- Implementation: Use DLP solutions to scan and tag files containing sensitive information using predefined patterns, such as Social Security Numbers or credit card details.

Exfiltration Restrictions:

- Use Case: Prevent unauthorized transmission of sensitive data.
- Implementation: Enforce policies to block unapproved email attachments, unauthorized USB usage, or unencrypted data uploads to cloud storage.

Data-in-Transit Monitoring:

- Use Case: Detect and prevent the transmission of sensitive data over unapproved channels.
- Implementation: Deploy network-based DLP tools to inspect outbound traffic for sensitive content (e.g., financial records or PII) and block unapproved transmissions.

Endpoint Data Protection:

- Use Case: Monitor and control sensitive data usage on endpoints.
- Implementation: Use endpoint-based DLP agents to block copy-paste actions of sensitive data and unauthorized printing or file sharing.

Cloud Data Security:

- Use Case: Protect data stored in cloud platforms.
- Implementation: Integrate DLP with cloud storage platforms like Google Drive, OneDrive, or AWS to monitor and restrict sensitive data sharing or downloads.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1057)

## Mitigated techniques

- [T1005 - Data from Local System](../../Tactics/12%20TA0009%20-%20Collection/T1005%20-%20Data%20from%20Local%20System/README.md)
- [T1025 - Data from Removable Media](../../Tactics/12%20TA0009%20-%20Collection/T1025%20-%20Data%20from%20Removable%20Media/README.md)
- [T1048 - Exfiltration Over Alternative Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/README.md)
- [T1048.002 - Exfiltration Over Asymmetric Encrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.002%20-%20Exfiltration%20Over%20Asymmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1041 - Exfiltration Over C2 Channel](../../Tactics/14%20TA0010%20-%20Exfiltration/T1041%20-%20Exfiltration%20Over%20C2%20Channel/README.md)
- [T1052 - Exfiltration Over Physical Medium](../../Tactics/14%20TA0010%20-%20Exfiltration/T1052%20-%20Exfiltration%20Over%20Physical%20Medium/README.md)
- [T1048.003 - Exfiltration Over Unencrypted Non-C2 Protocol](../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.003%20-%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol/README.md)
- [T1052.001 - Exfiltration over USB](../../Tactics/14%20TA0010%20-%20Exfiltration/T1052%20-%20Exfiltration%20Over%20Physical%20Medium/T1052.001%20-%20Exfiltration%20over%20USB/README.md)
- [T1567 - Exfiltration Over Web Service](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/README.md)
- [T1567.004 - Exfiltration Over Webhook](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.004%20-%20Exfiltration%20Over%20Webhook/README.md)
- [T1020.001 - Traffic Duplication](../../Tactics/14%20TA0010%20-%20Exfiltration/T1020%20-%20Automated%20Exfiltration/T1020.001%20-%20Traffic%20Duplication/README.md)
- [T1537 - Transfer Data to Cloud Account](../../Tactics/14%20TA0010%20-%20Exfiltration/T1537%20-%20Transfer%20Data%20to%20Cloud%20Account/README.md)

## Sources

- [PurpleSec Data Loss Prevention](https://purplesec.us/data-loss-prevention/)
