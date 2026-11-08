# M1036 - Account Use Policies

[Enterprise](../../README.md) / [Mitigations](README.md)

Account Use Policies help mitigate unauthorized access by configuring and enforcing rules that govern how and when accounts can be used. These policies include enforcing account lockout mechanisms, restricting login times, and setting inactivity timeouts. Proper configuration of these policies reduces the risk of brute-force attacks, credential theft, and unauthorized access by limiting the opportunities for malicious actors to exploit accounts. This mitigation can be implemented through the following measures:

Account Lockout Policies:

- Implementation: Configure account lockout settings so that after a defined number of failed login attempts (e.g., 3-5 attempts), the account is locked for a specific time period (e.g., 15 minutes) or requires an administrator to unlock it.
- Use Case: This prevents brute-force attacks by limiting how many incorrect password attempts can be made before the account is temporarily disabled, reducing the likelihood of an attacker successfully guessing a password.

Login Time Restrictions:

- Implementation: Set up login time policies to restrict when users or groups can log into systems. For example, only allowing login during standard business hours (e.g., 8 AM to 6 PM) for non-administrative accounts.
- Use Case: This prevents unauthorized access outside of approved working hours, where login attempts might be more suspicious or harder to monitor. For example, if an account that is only supposed to be active during the day logs in at 2 AM, it should raise an alert or be blocked.

Inactivity Timeout and Session Termination:

- Implementation: Enforce session timeouts after a period of inactivity (e.g., 10-15 minutes) and require users to re-authenticate if they wish to resume the session.
- Use Case: This policy prevents attackers from hijacking active sessions left unattended. For example, if an employee walks away from their computer without locking it, an attacker with physical access to the system would be unable to exploit the session.

Password Aging Policies:

- Implementation: Enforce password aging rules, requiring users to change their passwords after a defined period (e.g., 90 days) and ensure passwords are not reused by maintaining a password history.
- Use Case: This limits the risk of compromised passwords being used indefinitely. Regular password changes make it more difficult for attackers to reuse stolen credentials.

Account Expiration and Deactivation:

- Implementation: Configure user accounts, especially for temporary or contract workers, to automatically expire after a set date or event. Accounts that remain unused for a specific period should be deactivated automatically.
- Use Case: This prevents dormant accounts from becoming an attack vector. For example, an attacker can exploit unused accounts if they are not properly monitored or deactivated.

**Tools for Implementation**:

- Group Policy Objects (GPOs) in Windows: To enforce account lockout thresholds, login time restrictions, session timeouts, and password policies.
- Identity and Access Management (IAM) solutions: For centralized management of user accounts, session policies, and automated deactivation of accounts.
- Security Information and Event Management (SIEM) platforms: To monitor and alert on unusual login activity, such as failed logins or out-of-hours access attempts.
- Multi-Factor Authentication (MFA) Tools: To further enforce secure login attempts, preventing brute-force or credential stuffing attacks.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1036)

## Mitigated techniques

- [T1550.001 - Application Access Token](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md)
- [T1110 - Brute Force](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1078.004 - Cloud Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1110.004 - Credential Stuffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.004%20-%20Credential%20Stuffing/README.md)
- [T1621 - Multi-Factor Authentication Request Generation](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1621%20-%20Multi-Factor%20Authentication%20Request%20Generation/README.md)
- [T1110.001 - Password Guessing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.001%20-%20Password%20Guessing/README.md)
- [T1110.003 - Password Spraying](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1648 - Serverless Execution](../../Tactics/04%20TA0002%20-%20Execution/T1648%20-%20Serverless%20Execution/README.md)
- [T1684 - Social Engineering](../../Tactics/07%20TA0005%20-%20Stealth/T1684%20-%20Social%20Engineering/README.md)
- [T1697 - Steal Application Specific Passwords](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1697%20-%20Steal%20Application%20Specific%20Passwords/README.md)
- [T1550 - Use Alternate Authentication Material](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
