# M1054 - Software Configuration

[Enterprise](../../README.md) / [Mitigations](README.md)

Software configuration refers to making security-focused adjustments to the settings of applications, middleware, databases, or other software to mitigate potential threats. These changes help reduce the attack surface, enforce best practices, and protect sensitive data. This mitigation can be implemented through the following measures:

Conduct a Security Review of Application Settings:

- Review the software documentation to identify recommended security configurations.
- Compare default settings against organizational policies and compliance requirements.

Implement Access Controls and Permissions:

- Restrict access to sensitive features or data within the software.
- Enforce least privilege principles for all roles and accounts interacting with the software.

Enable Logging and Monitoring:

- Configure detailed logging for key application events such as authentication failures, configuration changes, or unusual activity.
- Integrate logs with a centralized monitoring solution, such as a SIEM.

Update and Patch Software Regularly:

- Ensure the software is kept up-to-date with the latest security patches to address known vulnerabilities.
- Use automated patch management tools to streamline the update process.

Disable Unnecessary Features or Services:

- Turn off unused functionality or components that could introduce vulnerabilities, such as debugging interfaces or deprecated APIs.

Test Configuration Changes:

- Perform configuration changes in a staging environment before applying them in production.
- Conduct regular audits to ensure that settings remain aligned with security policies.

*Tools for Implementation*

Configuration Management Tools:

- Ansible: Automates configuration changes across multiple applications and environments.
- Chef: Ensures consistent application settings through code-based configuration management.
- Puppet: Automates software configurations and audits changes for compliance.

Security Benchmarking Tools:

- CIS-CAT: Provides benchmarks and audits for secure software configurations.
- Aqua Security Trivy: Scans containerized applications for configuration issues.

Vulnerability Management Solutions:

- Nessus: Identifies misconfigurations and suggests corrective actions.

Logging and Monitoring Tools:

- Splunk: Aggregates and analyzes application logs to detect suspicious activity.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1054)

## Mitigated techniques

- [T1543.005 - Container Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.005%20-%20Container%20Service/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1213.004 - Customer Relationship Management Software](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.004%20-%20Customer%20Relationship%20Management%20Software/README.md)
- [T1602 - Data from Configuration Repository](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/README.md)
- [T1213 - Data from Information Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/README.md)
- [T1213.006 - Databases](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.006%20-%20Databases/README.md)
- [T1685 - Disable or Modify Tools](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1685%20-%20Disable%20or%20Modify%20Tools/README.md)
- [T1590.002 - DNS](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1590%20-%20Gather%20Victim%20Network%20Information/T1590.002%20-%20DNS/README.md)
- [T1689 - Downgrade Attack](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1689%20-%20Downgrade%20Attack/README.md)
- [T1559.002 - Dynamic Data Exchange](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.002%20-%20Dynamic%20Data%20Exchange/README.md)
- [T1667 - Email Bombing](../../Tactics/15%20TA0040%20-%20Impact/T1667%20-%20Email%20Bombing/README.md)
- [T1684.002 - Email Spoofing](../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/T1684.002%20-%20Email%20Spoofing/README.md)
- [T1606 - Forge Web Credentials](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/README.md)
- [T1553.004 - Install Root Certificate](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.004%20-%20Install%20Root%20Certificate/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1666 - Modify Cloud Resource Hierarchy](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1666%20-%20Modify%20Cloud%20Resource%20Hierarchy/README.md)
- [T1602.002 - Network Device Configuration Dump](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.002%20-%20Network%20Device%20Configuration%20Dump/README.md)
- [T1137 - Office Application Startup](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/README.md)
- [T1137.002 - Office Test](../../Tactics/05%20TA0003%20-%20Persistence/T1137%20-%20Office%20Application%20Startup/T1137.002%20-%20Office%20Test/README.md)
- [T1555.005 - Password Managers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.005%20-%20Password%20Managers/README.md)
- [T1566 - Phishing](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/README.md)
- [T1598 - Phishing for Information](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/README.md)
- [T1677 - Poisoned Pipeline Execution](../../Tactics/04%20TA0002%20-%20Execution/T1677%20-%20Poisoned%20Pipeline%20Execution/README.md)
- [T1546.013 - PowerShell Profile](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.013%20-%20PowerShell%20Profile/README.md)
- [T1688 - Safe Mode Boot](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1688%20-%20Safe%20Mode%20Boot/README.md)
- [T1602.001 - SNMP (MIB Dump)](../../Tactics/12%20TA0009%20-%20Collection/T1602%20-%20Data%20from%20Configuration%20Repository/T1602.001%20-%20SNMP%20%28MIB%20Dump%29/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1598.002 - Spearphishing Attachment](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/T1598.002%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1598.003 - Spearphishing Link](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1598%20-%20Phishing%20for%20Information/T1598.003%20-%20Spearphishing%20Link/README.md)
- [T1539 - Steal Web Session Cookie](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md)
- [T1553 - Subvert Trust Controls](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/README.md)
- [T1537 - Transfer Data to Cloud Account](../../Tactics/14%20TA0010%20-%20Exfiltration/T1537%20-%20Transfer%20Data%20to%20Cloud%20Account/README.md)
- [T1535 - Unused/Unsupported Cloud Regions](../../Tactics/07%20TA0005%20-%20Stealth/T1535%20-%20Unused%20-%20Unsupported%20Cloud%20Regions/README.md)
- [T1606.001 - Web Cookies](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1606%20-%20Forge%20Web%20Credentials/T1606.001%20-%20Web%20Cookies/README.md)
- [T1550.004 - Web Session Cookie](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.004%20-%20Web%20Session%20Cookie/README.md)
