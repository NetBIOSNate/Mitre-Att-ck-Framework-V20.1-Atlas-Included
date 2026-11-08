# M1048 - Application Isolation and Sandboxing

[Enterprise](../../README.md) / [Mitigations](README.md)

Application Isolation and Sandboxing refers to the technique of restricting the execution of code to a controlled and isolated environment (e.g., a virtual environment, container, or sandbox). This method prevents potentially malicious code from affecting the rest of the system or network by limiting access to sensitive resources and critical operations. The goal is to contain threats and minimize their impact. This mitigation can be implemented through the following measures:

Browser Sandboxing:

- Use Case: Implement browser sandboxing to isolate untrusted web content and prevent malicious web pages or scripts from accessing sensitive system resources or initiating unauthorized downloads.
- Implementation: Use browsers with built-in sandboxing features (e.g., Google Chrome, Microsoft Edge) or deploy enhanced browser security frameworks that limit the execution scope of active content. Consider controls that monitor or restrict script-based file generation and downloads commonly abused in evasion techniques like HTML smuggling.

Application Virtualization:

- Use Case: Deploy critical or high-risk applications in a virtualized environment to ensure any compromise does not affect the host system.
- Implementation: Use application virtualization platforms to run applications in isolated environments.

Email Attachment Sandboxing:

- Use Case: Route email attachments to a sandbox environment to detect and block malware before delivering emails to end-users.
- Implementation: Integrate security solutions with sandbox capabilities to analyze email attachments.

Endpoint Sandboxing:

- Use Case: Run all downloaded files and applications in a restricted environment to monitor their behavior for malicious activity.
- Implementation: Use endpoint protection tools for sandboxing at the endpoint level.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1048)

## Mitigated techniques

- [T1700 - AI-Enabled Exfiltration](../../Tactics/14%20TA0010%20-%20Exfiltration/T1700%20-%20AI-Enabled%20Exfiltration/README.md)
- [T1559.001 - Component Object Model](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.001%20-%20Component%20Object%20Model/README.md)
- [T1021.003 - Distributed Component Object Model](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.003%20-%20Distributed%20Component%20Object%20Model/README.md)
- [T1189 - Drive-by Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md)
- [T1559.002 - Dynamic Data Exchange](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.002%20-%20Dynamic%20Data%20Exchange/README.md)
- [T1611 - Escape to Host](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1611%20-%20Escape%20to%20Host/README.md)
- [T1190 - Exploit Public-Facing Application](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1190%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1203 - Exploitation for Client Execution](../../Tactics/04%20TA0002%20-%20Execution/T1203%20-%20Exploitation%20for%20Client%20Execution/README.md)
- [T1212 - Exploitation for Credential Access](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1212%20-%20Exploitation%20for%20Credential%20Access/README.md)
- [T1068 - Exploitation for Privilege Escalation](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1068%20-%20Exploitation%20for%20Privilege%20Escalation/README.md)
- [T1211 - Exploitation for Stealth](../../Tactics/07%20TA0005%20-%20Stealth/T1211%20-%20Exploitation%20for%20Stealth/README.md)
- [T1210 - Exploitation of Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1210%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1027.006 - HTML Smuggling](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.006%20-%20HTML%20Smuggling/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1027.017 - SVG Smuggling](../../Tactics/07%20TA0005%20-%20Stealth/T1027%20-%20Obfuscated%20Files%20or%20Information/T1027.017%20-%20SVG%20Smuggling/README.md)
