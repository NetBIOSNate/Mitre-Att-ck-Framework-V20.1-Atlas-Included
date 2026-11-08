# M1032 - Multi-factor Authentication

[Enterprise](../../README.md) / [Mitigations](README.md)

Multi-Factor Authentication (MFA) enhances security by requiring users to provide at least two forms of verification to prove their identity before granting access. These factors typically include:

- *Something you know*: Passwords, PINs.
- *Something you have*: Physical tokens, smartphone authenticator apps.
- *Something you are*: Biometric data such as fingerprints, facial recognition, or retinal scans.

Implementing MFA across all critical systems and services ensures robust protection against account takeover and unauthorized access. This mitigation can be implemented through the following measures:

Identity and Access Management (IAM):

- Use IAM solutions like Azure Active Directory, Okta, or AWS IAM to enforce MFA policies for all user logins, especially for privileged roles.
- Enable conditional access policies to enforce MFA for risky sign-ins (e.g., unfamiliar devices, geolocations).
- Enable Conditional Access policies to only allow logins from trusted devices, such as those enrolled in Intune or joined via Hybrid/Entra.

Authentication Tools and Methods:

- Use authenticator applications such as Google Authenticator, Microsoft Authenticator, or Authy for time-based one-time passwords (TOTP).
- Deploy hardware-based tokens like YubiKey, RSA SecurID, or smart cards for additional security.
- Enforce biometric authentication for compatible devices and applications.

Secure Legacy Systems:

- Integrate MFA solutions with older systems using third-party tools like Duo Security or Thales SafeNet.
- Enable RADIUS/NPS servers to facilitate MFA for VPNs, RDP, and other network logins.

Monitoring and Alerting:

- Use SIEM tools to monitor failed MFA attempts, login anomalies, or brute-force attempts against MFA systems.
- Implement alerts for suspicious MFA activities, such as repeated failed codes or new device registrations.

Training and Policy Enforcement:

- Educate employees on the importance of MFA and secure authenticator usage.
- Enforce policies that require MFA on all critical systems, especially for remote access, privileged accounts, and cloud applications.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1032)

## Mitigated techniques

- [T1098 - Account Manipulation](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/README.md)
- [T1098.001 - Additional Cloud Credentials](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.001%20-%20Additional%20Cloud%20Credentials/README.md)
- [T1098.003 - Additional Cloud Roles](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.003%20-%20Additional%20Cloud%20Roles/README.md)
- [T1098.006 - Additional Container Cluster Roles](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.006%20-%20Additional%20Container%20Cluster%20Roles/README.md)
- [T1098.002 - Additional Email Delegate Permissions](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.002%20-%20Additional%20Email%20Delegate%20Permissions/README.md)
- [T1110 - Brute Force](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/README.md)
- [T1136.003 - Cloud Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.003%20-%20Cloud%20Account/README.md)
- [T1078.004 - Cloud Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.004%20-%20Cloud%20Accounts/README.md)
- [T1021.007 - Cloud Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.007%20-%20Cloud%20Services/README.md)
- [T1213.003 - Code Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.003%20-%20Code%20Repositories/README.md)
- [T1136 - Create Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/README.md)
- [T1110.004 - Credential Stuffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.004%20-%20Credential%20Stuffing/README.md)
- [T1485 - Data Destruction](../../Tactics/15%20TA0040%20-%20Impact/T1485%20-%20Data%20Destruction/README.md)
- [T1530 - Data from Cloud Storage](../../Tactics/12%20TA0009%20-%20Collection/T1530%20-%20Data%20from%20Cloud%20Storage/README.md)
- [T1213 - Data from Information Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/README.md)
- [T1078.001 - Default Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.001%20-%20Default%20Accounts/README.md)
- [T1098.005 - Device Registration](../../Tactics/05%20TA0003%20-%20Persistence/T1098%20-%20Account%20Manipulation/T1098.005%20-%20Device%20Registration/README.md)
- [T1136.002 - Domain Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.002%20-%20Domain%20Account/README.md)
- [T1078.002 - Domain Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.002%20-%20Domain%20Accounts/README.md)
- [T1556.001 - Domain Controller Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.001%20-%20Domain%20Controller%20Authentication/README.md)
- [T1601.002 - Downgrade System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.002%20-%20Downgrade%20System%20Image/README.md)
- [T1114 - Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/README.md)
- [T1133 - External Remote Services](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1133%20-%20External%20Remote%20Services/README.md)
- [T1556.007 - Hybrid Identity](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.007%20-%20Hybrid%20Identity/README.md)
- [T1136.001 - Local Account](../../Tactics/05%20TA0003%20-%20Persistence/T1136%20-%20Create%20Account/T1136.001%20-%20Local%20Account/README.md)
- [T1078.003 - Local Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/T1078.003%20-%20Local%20Accounts/README.md)
- [T1556 - Modify Authentication Process](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/README.md)
- [T1601 - Modify System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/README.md)
- [T1556.006 - Multi-Factor Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.006%20-%20Multi-Factor%20Authentication/README.md)
- [T1621 - Multi-Factor Authentication Request Generation](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1621%20-%20Multi-Factor%20Authentication%20Request%20Generation/README.md)
- [T1599.001 - Network Address Translation Traversal](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/T1599.001%20-%20Network%20Address%20Translation%20Traversal/README.md)
- [T1599 - Network Boundary Bridging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/README.md)
- [T1556.004 - Network Device Authentication](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.004%20-%20Network%20Device%20Authentication/README.md)
- [T1040 - Network Sniffing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1040%20-%20Network%20Sniffing/README.md)
- [T1110.002 - Password Cracking](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.002%20-%20Password%20Cracking/README.md)
- [T1110.001 - Password Guessing](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.001%20-%20Password%20Guessing/README.md)
- [T1110.003 - Password Spraying](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1110%20-%20Brute%20Force/T1110.003%20-%20Password%20Spraying/README.md)
- [T1601.001 - Patch System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.001%20-%20Patch%20System%20Image/README.md)
- [T1556.003 - Pluggable Authentication Modules](../../Tactics/05%20TA0003%20-%20Persistence/T1556%20-%20Modify%20Authentication%20Process/T1556.003%20-%20Pluggable%20Authentication%20Modules/README.md)
- [T1021.001 - Remote Desktop Protocol](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.001%20-%20Remote%20Desktop%20Protocol/README.md)
- [T1114.002 - Remote Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.002%20-%20Remote%20Email%20Collection/README.md)
- [T1021 - Remote Services](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/README.md)
- [T1072 - Software Deployment Tools](../../Tactics/04%20TA0002%20-%20Execution/T1072%20-%20Software%20Deployment%20Tools/README.md)
- [T1021.004 - SSH](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1021%20-%20Remote%20Services/T1021.004%20-%20SSH/README.md)
- [T1539 - Steal Web Session Cookie](../../Tactics/09%20TA0006%20-%20Credential%20Access/T1539%20-%20Steal%20Web%20Session%20Cookie/README.md)
- [T1199 - Trusted Relationship](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1199%20-%20Trusted%20Relationship/README.md)
- [T1078 - Valid Accounts](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1078%20-%20Valid%20Accounts/README.md)
- [T1669 - Wi-Fi Networks](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1669%20-%20Wi-Fi%20Networks/README.md)
