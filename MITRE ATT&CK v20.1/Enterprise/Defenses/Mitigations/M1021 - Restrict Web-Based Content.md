# M1021 - Restrict Web-Based Content

[Enterprise](../../README.md) / [Mitigations](README.md)

Restricting web-based content involves enforcing policies and technologies that limit access to potentially malicious websites, unsafe downloads, and unauthorized browser behaviors. This can include URL filtering, download restrictions, script blocking, and extension control to protect against exploitation, phishing, and malware delivery. This mitigation can be implemented through the following measures:

Deploy Web Proxy Filtering:

- Use solutions to filter web traffic based on categories, reputation, and content types.
- Enforce policies that block unsafe websites or file types at the gateway level.

Enable DNS-Based Filtering:

- Implement tools to restrict access to domains associated with malware or phishing campaigns.
- Use public DNS filtering services to enhance protection.

Enforce Content Security Policies (CSP):

- Configure CSP headers on internal and external web applications to restrict script execution, iframe embedding, and cross-origin requests.

Control Browser Features:

- Disable unapproved browser features like automatic downloads, developer tools, or unsafe scripting.
- Enforce policies through tools like Group Policy Management to control browser settings.

Monitor and Alert on Web-Based Threats:

- Use SIEM tools to collect and analyze web proxy logs for signs of anomalous or malicious activity.
- Configure alerts for access attempts to blocked domains or repeated file download failures.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1021)

## Mitigated techniques

- [T1550.001 - Application Access Token](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1102.002 - Bidirectional Communication](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/T1102.002%20-%20Bidirectional%20Communication/README.md)
- [T1127.002 - ClickOnce](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.002%20-%20ClickOnce/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1218.001 - Compiled HTML File](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/T1218.001%20-%20Compiled%20HTML%20File/README.md)
- [T1659 - Content Injection](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1659%20-%20Content%20Injection/README.md)
- [T1555.003 - Credentials from Web Browsers](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1555%20-%20Credentials%20from%20Password%20Stores/T1555.003%20-%20Credentials%20from%20Web%20Browsers/README.md)
- [T1102.001 - Dead Drop Resolver](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/T1102.001%20-%20Dead%20Drop%20Resolver/README.md)
- [T1568.002 - Domain Generation Algorithms](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1568%20-%20Dynamic%20Resolution/T1568.002%20-%20Domain%20Generation%20Algorithms/README.md)
- [T1189 - Drive-by Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1189%20-%20Drive-by%20Compromise/README.md)
- [T1568 - Dynamic Resolution](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1568%20-%20Dynamic%20Resolution/README.md)
- [T1567 - Exfiltration Over Web Service](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1567.001 - Exfiltration to Code Repository](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.001%20-%20Exfiltration%20to%20Code%20Repository/README.md)
- [T1567.003 - Exfiltration to Text Storage Sites](../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.003%20-%20Exfiltration%20to%20Text%20Storage%20Sites/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1059.007 - JavaScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.007%20-%20JavaScript/README.md)
- [T1204.004 - Malicious Copy and Paste](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.004%20-%20Malicious%20Copy%20and%20Paste/README.md)
- [T1204.001 - Malicious Link](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.001%20-%20Malicious%20Link/README.md)
- [T1102.003 - One-Way Communication](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/T1102.003%20-%20One-Way%20Communication/README.md)
- [T1566 - Phishing](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/README.md)
- [T1566.001 - Spearphishing Attachment](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.001%20-%20Spearphishing%20Attachment/README.md)
- [T1566.002 - Spearphishing Link](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.002%20-%20Spearphishing%20Link/README.md)
- [T1566.003 - Spearphishing via Service](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1566%20-%20Phishing/T1566.003%20-%20Spearphishing%20via%20Service/README.md)
- [T1528 - Steal Application Access Token](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1528%20-%20Steal%20Application%20Access%20Token/README.md)
- [T1539 - Steal Web Session Cookie](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md)
- [T1218 - System Binary Proxy Execution](../../Tactics/07%20TA0005%20-%20Stealth/T1218%20-%20System%20Binary%20Proxy%20Execution/README.md)
- [T1127 - Trusted Developer Utilities Proxy Execution](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/README.md)
- [T1204 - User Execution](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md)
- [T1059.005 - Visual Basic](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.005%20-%20Visual%20Basic/README.md)
- [T1102 - Web Service](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1102%20-%20Web%20Service/README.md)
