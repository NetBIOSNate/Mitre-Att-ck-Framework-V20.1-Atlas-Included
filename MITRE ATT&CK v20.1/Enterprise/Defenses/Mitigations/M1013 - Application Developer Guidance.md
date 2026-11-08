# M1013 - Application Developer Guidance

[Enterprise](../../README.md) / [Mitigations](README.md)

Application Developer Guidance focuses on providing developers with the knowledge, tools, and best practices needed to write secure code, reduce vulnerabilities, and implement secure design principles. By integrating security throughout the software development lifecycle (SDLC), this mitigation aims to prevent the introduction of exploitable weaknesses in applications, systems, and APIs. This mitigation can be implemented through the following measures:
 
Preventing SQL Injection (Secure Coding Practice):

- Implementation: Train developers to use parameterized queries or prepared statements instead of directly embedding user input into SQL queries.
- Use Case: A web application accepts user input to search a database. By sanitizing and validating user inputs, developers can prevent attackers from injecting malicious SQL commands.

Cross-Site Scripting (XSS) Mitigation:

- Implementation: Require developers to implement output encoding for all user-generated content displayed on a web page.
- Use Case: An e-commerce site allows users to leave product reviews. Properly encoding and escaping user inputs prevents malicious scripts from being executed in other users’ browsers.

Secure API Design:

- Implementation: Train developers to authenticate all API endpoints and avoid exposing sensitive information in API responses.
- Use Case: A mobile banking application uses APIs for account management. By enforcing token-based authentication for every API call, developers reduce the risk of unauthorized access.

Static Code Analysis in the Build Pipeline:

- Implementation: Incorporate tools into CI/CD pipelines to automatically scan for vulnerabilities during the build process.
- Use Case: A fintech company integrates static analysis tools to detect hardcoded credentials in their source code before deployment.

Threat Modeling in the Design Phase:

- Implementation: Use frameworks like STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege) to assess threats during application design.
- Use Case: Before launching a customer portal, a SaaS company identifies potential abuse cases, such as session hijacking, and designs mitigations like secure session management.

**Tools for Implementation**:

- Static Code Analysis Tools: Use tools that can scan for known vulnerabilities in source code.
- Dynamic Application Security Testing (DAST): Use tools like Burp Suite or OWASP ZAP to simulate runtime attacks and identify vulnerabilities.
- Secure Frameworks: Recommend secure-by-default frameworks (e.g., Django for Python, Spring Security for Java) that enforce security best practices.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1013)

## Mitigated techniques

- [T1550.001 - Application Access Token](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1593.003 - Code Repositories](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/T1593.003%20-%20Code%20Repositories/README.md)
- [T1195.001 - Compromise Software Dependencies and Development Tools](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.001%20-%20Compromise%20Software%20Dependencies%20and%20Development%20Tools/README.md)
- [T1574.001 - DLL](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.001%20-%20DLL/README.md)
- [T1212 - Exploitation for Credential Access](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1212%20-%20Exploitation%20for%20Credential%20Access/README.md)
- [T1564.012 - File/Path Exclusions](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.012%20-%20File%20-%20Path%20Exclusions/README.md)
- [T1564 - Hide Artifacts](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1559 - Inter-Process Communication](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/README.md)
- [T1647 - Plist File Modification](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1647%20-%20Plist%20File%20Modification/README.md)
- [T1564.009 - Resource Forking](../../Tactics/07%20TA0005%20-%20Stealth/T1564%20-%20Hide%20Artifacts/T1564.009%20-%20Resource%20Forking/README.md)
- [T1593 - Search Open Websites/Domains](../../Tactics/01%20TA0043%20-%20Reconnaissance/T1593%20-%20Search%20Open%20Websites%20-%20Domains/README.md)
- [T1496.003 - SMS Pumping](../../Tactics/15%20TA0040%20-%20Impact/T1496%20-%20Resource%20Hijacking/T1496.003%20-%20SMS%20Pumping/README.md)
- [T1195 - Supply Chain Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md)
- [T1550 - Use Alternate Authentication Material](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1559.003 - XPC Services](../../Tactics/04%20TA0002%20-%20Execution/T1559%20-%20Inter-Process%20Communication/T1559.003%20-%20XPC%20Services/README.md)
