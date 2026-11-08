# T1697 - Steal Application Specific Passwords

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may steal Application Specific Passwords (ASPs) to gain access to [Valid Accounts](https://attack.mitre.org/techniques/T1078), bypassing multifactor authentication (MFA) methods. ASPs are passwords typically used to give third-party applications or legacy devices (which do not support MFA methods) account access.(Citation: Application Specific Passwords)(Citation: Application Specific Passwords Push Sec) 
 
An adversary may socially engineer a user into providing an ASP(Citation: UNC6293 ASP Creative Phishing Attack)(Citation: Application Specific Passwords Phishing) (using methods like [Phishing for Information](https://attack.mitre.org/techniques/T1598)), generate an ASP for an already compromised account,(Citation: Mandiant APT42-untangling)(Citation: TAG APT42) or obtain an ASP stored on a system. Afterward, adversaries may use the ASP to access [Valid Accounts](https://attack.mitre.org/techniques/T1078) and, in some cases, maintain [Persistence](https://attack.mitre.org/tactics/TA0003), bypassing any form of MFA set on the account.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1697)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md), [SaaS](../../../Platforms/SaaS.md)

## Mitigations

- [M1036 - Account Use Policies](../../../Defenses/Mitigations/M1036%20-%20Account%20Use%20Policies.md) — Restrict authentication paths/clients/locations through which accounts using legacy/app-password authentication can authenticate. This matters because an ASP that has been stolen shouldn't automatically have unrestricted account reach.
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable ASP functionality where modern authentication is available. Microsoft specifically supports disabling users' ability to create app passwords and recommends disabling legacy authentication so existing app passwords no longer work.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Restrict which users may create/use ASPs; disable ASP creation where unnecessary; remove existing ASPs. Microsoft allows admins to disable creation and separately delete existing ASPs; Google administrators can view/revoke users' application-specific passwords.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — ASPs can be obtained through social engineering, which your technique explicitly includes. Train users not to generate or disclose ASPs in response to unsolicited instructions.

## Procedure examples

- [G1044 - APT42](../../../Threat%20Intelligence/Groups/G1044%20-%20APT42.md) — [APT42](https://attack.mitre.org/groups/G1044) has stolen application specific passwords in order to bypass MFA requirements to include victim environments who leverage the Microsoft App Password feature. (Citation: Mandiant APT42-charms) [Mandiant APT42-charms](https://services.google.com/fh/files/misc/apt42-crooked-charms-cons-and-compromises.pdf)

## Detection strategies

- [DET0926 - Suspicious Acquisition and Use of Application-Specific Passwords](../../../Defenses/Detection%20Strategies/DET0926%20-%20Suspicious%20Acquisition%20and%20Use%20of%20Application-Specific%20Passwords.md)

## Sources

- [Application Specific Passwords](https://astrix.security/learn/blog/app-specific-passwords-origins-functionality-security-risks/)
- [Application Specific Passwords Push Sec](https://pushsecurity.com/blog/app-specific-password-phishing)
- [UNC6293 ASP Creative Phishing Attack](https://cloud.google.com/blog/topics/threat-intelligence/creative-phishing-academics-critics-of-russia)
- [TAG APT42](https://blog.google/threat-analysis-group/iranian-backed-group-steps-up-phishing-campaigns-against-israel-us/)
- [Application Specific Passwords Phishing](https://citizenlab.ca/research/russian-government-linked-social-engineering-targets-app-specific-passwords/)
- [Mandiant APT42-untangling](https://cloud.google.com/blog/topics/threat-intelligence/untangling-iran-apt42-operations)
