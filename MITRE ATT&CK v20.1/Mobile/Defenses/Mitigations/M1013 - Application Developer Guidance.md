# M1013 - Application Developer Guidance

[Mobile](../../README.md) / [Mitigations](README.md)

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

- [T1626 - Abuse Elevation Control Mechanism](../../Tactics/04%20TA0029%20-%20Privilege%20Escalation/T1626%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1517 - Access Notifications](../../Tactics/06%20TA0031%20-%20Credential%20Access/T1517%20-%20Access%20Notifications/README.md)
- [T1474.001 - Compromise Software Dependencies and Development Tools](../../Tactics/01%20TA0027%20-%20Initial%20Access/T1474%20-%20Supply%20Chain%20Compromise/T1474.001%20-%20Compromise%20Software%20Dependencies%20and%20Development%20Tools/README.md)
- [T1513 - Screen Capture](../../Tactics/09%20TA0035%20-%20Collection/T1513%20-%20Screen%20Capture/README.md)
- [T1635 - Steal Application Access Token](../../Tactics/06%20TA0031%20-%20Credential%20Access/T1635%20-%20Steal%20Application%20Access%20Token/README.md)
- [T1474 - Supply Chain Compromise](../../Tactics/01%20TA0027%20-%20Initial%20Access/T1474%20-%20Supply%20Chain%20Compromise/README.md)
- [T1635.001 - URI Hijacking](../../Tactics/06%20TA0031%20-%20Credential%20Access/T1635%20-%20Steal%20Application%20Access%20Token/T1635.001%20-%20URI%20Hijacking/README.md)
