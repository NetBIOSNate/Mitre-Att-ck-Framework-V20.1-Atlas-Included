# T1671 - Cloud Application Integration

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may achieve persistence by leveraging OAuth application integrations in a software-as-a-service environment. Adversaries may create a custom application, add a legitimate application into the environment, or even co-opt an existing integration to achieve malicious ends.(Citation: Push Security SaaS Persistence 2022)(Citation: SaaS Attacks GitHub Evil Twin Integrations)

OAuth is an open standard that allows users to authorize applications to access their information on their behalf. In a SaaS environment such as Microsoft 365 or Google Workspace, users may integrate applications to improve their workflow and achieve tasks.  

Leveraging application integrations may allow adversaries to persist in an environment – for example, by granting consent to an application from a high-privileged adversary-controlled account in order to maintain access to its data, even in the event of losing access to the account.(Citation: Wiz Midnight Blizzard 2024)(Citation: Microsoft Malicious OAuth Applications 2022)(Citation: Huntress Persistence Microsoft 365 Compromise 2024) In some cases, integrations may remain valid even after the original consenting user account is disabled.(Citation: Push Security Slack Persistence 2023) Application integrations may also allow adversaries to bypass multi-factor authentication requirements through the use of [Application Access Token](https://attack.mitre.org/techniques/T1550/001)s. Finally, they may enable persistent [Automated Exfiltration](https://attack.mitre.org/techniques/T1020) over time.(Citation: Synes Cyber Corner Malicious Azure Application 2023)

Creating or adding a new application may require the adversary to create a dedicated [Cloud Account](https://attack.mitre.org/techniques/T1136/003) for the application and assign it [Additional Cloud Roles](https://attack.mitre.org/techniques/T1098/003) – for example, in Microsoft 365 environments, an application can only access resources via an associated service principal.(Citation: Microsoft Entra ID Service Principals)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1671)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Office Suite](../../../Platforms/Office%20Suite.md), [SaaS](../../../Platforms/SaaS.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Periodically review SaaS integrations for unapproved or potentially malicious applications.
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Do not allow users to add new application integrations into a SaaS environment. In Entra ID environments, consider enforcing the “Do not allow user consent” option.(Citation: Microsoft Entra Configure OAuth Consent) [Microsoft Entra Configure OAuth Consent](https://learn.microsoft.com/en-us/entra/identity/enterprise-apps/configure-user-consent?pivots=portal)

## Procedure examples

- [C0059 - Salesforce Data Exfiltration](../../../Threat%20Intelligence/Campaigns/C0059%20-%20Salesforce%20Data%20Exfiltration.md) — During [Salesforce Data Exfiltration](https://attack.mitre.org/campaigns/C0059), threat actors deceived victims into authorizing malicious connected apps to their organization's Salesforce portal.(Citation: FBI Salesforce Data Theft SEP 2025)(Citation: Google Salesforce JUN 2025) [FBI Salesforce Data Theft SEP 2025](https://www.ic3.gov/CSA/2025/250912.pdf) · [Google Salesforce JUN 2025](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion)

## Detection strategies

- [DET0539 - Detection Strategy for Cloud Application Integration](../../../Defenses/Detection%20Strategies/DET0539%20-%20Detection%20Strategy%20for%20Cloud%20Application%20Integration.md)

## Sources

- [Wiz Midnight Blizzard 2024](https://www.wiz.io/blog/midnight-blizzard-microsoft-breach-analysis-and-best-practices)
- [Push Security SaaS Persistence 2022](https://pushsecurity.com/blog/maintaining-persistent-access-in-a-saas-first-world/)
- [Push Security Slack Persistence 2023](https://pushsecurity.com/blog/phishing-slack-persistence/)
- [Microsoft Malicious OAuth Applications 2022](https://www.microsoft.com/en-us/security/blog/2022/09/22/malicious-OAuth-applications-used-to-compromise-email-servers-and-spread-spam/)
- [Microsoft Entra ID Service Principals](https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals?tabs=browser)
- [SaaS Attacks GitHub Evil Twin Integrations](https://github.com/pushsecurity/saas-attacks/blob/main/techniques/evil_twin_integrations/description.md)
- [Huntress Persistence Microsoft 365 Compromise 2024](https://www.huntress.com/blog/legitimate-apps-as-traitorware-for-persistent-microsoft-365-compromise)
- [Synes Cyber Corner Malicious Azure Application 2023](https://cybercorner.tech/malicious-azure-application-perfectdata-software-and-office365-business-email-compromise/)
