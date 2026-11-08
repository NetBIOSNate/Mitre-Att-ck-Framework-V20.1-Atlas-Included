# T1648 - Serverless Execution

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may abuse serverless computing, integration, and automation services to execute arbitrary code in cloud environments. Many cloud providers offer a variety of serverless resources, including compute engines, application integration services, and web servers. 

Adversaries may abuse these resources in various ways as a means of executing arbitrary commands. For example, adversaries may use serverless functions to execute malicious code, such as crypto-mining malware (i.e. [Resource Hijacking](https://attack.mitre.org/techniques/T1496)).(Citation: Cado Security Denonia) Adversaries may also create functions that enable further compromise of the cloud environment. For example, an adversary may use the `IAM:PassRole` permission in AWS or the `iam.serviceAccounts.actAs` permission in Google Cloud to add [Additional Cloud Roles](https://attack.mitre.org/techniques/T1098/003) to a serverless cloud function, which may then be able to perform actions the original user cannot.(Citation: Rhino Security Labs AWS Privilege Escalation)(Citation: Rhingo Security Labs GCP Privilege Escalation)

Serverless functions can also be invoked in response to cloud events (i.e. [Event Triggered Execution](https://attack.mitre.org/techniques/T1546)), potentially enabling persistent execution over time. For example, in AWS environments, an adversary may create a Lambda function that automatically adds [Additional Cloud Credentials](https://attack.mitre.org/techniques/T1098/001) to a user and a corresponding CloudWatch events rule that invokes that function whenever a new user is created.(Citation: Backdooring an AWS account) This is also possible in many cloud-based office application suites. For example, in Microsoft 365 environments, an adversary may create a Power Automate workflow that forwards all emails a user receives or creates anonymous sharing links whenever a user is granted access to a document in SharePoint.(Citation: Varonis Power Automate Data Exfiltration)(Citation: Microsoft DART Case Report 001) In Google Workspace environments, they may instead create an Apps Script that exfiltrates a user's data when they open a file.(Citation: Cloud Hack Tricks GWS Apps Script)(Citation: OWN-CERT Google App Script 2024)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1648)

**Tactics**  [Execution](../README.md)

**Platforms**  [SaaS](../../../Platforms/SaaS.md), [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Procedure examples

- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can create malicious Lambda functions.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)

## Mitigations

- [M1036 - Account Use Policies](../../../Defenses/Mitigations/M1036%20-%20Account%20Use%20Policies.md) — Where possible, consider restricting access to and use of serverless functions. For examples, conditional access policies can be applied to users attempting to create workflows in Microsoft Power Automate. Google Apps Scripts that use OAuth can be limited by restricting access to high-risk OAuth scopes.(Citation: Microsoft Developer Support Power Apps Conditional Access)(Citation: Google Workspace Apps Script Restrict OAuth Scopes) [Google Workspace Apps Script Restrict OAuth Scopes](https://developers.google.com/apps-script/guides/admin/monitor-restrict-oauth-scopes) · [Microsoft Developer Support Power Apps Conditional Access](https://devblogs.microsoft.com/premier-developer/control-access-to-power-apps-and-power-automate-with-azure-ad-conditional-access-policies/)
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Remove permissions to create, modify, or run serverless resources from users that do not explicitly require them.

## Detection strategies

- [DET0374 - Detection Strategy for Serverless Execution (T1648)](../../../Defenses/Detection%20Strategies/DET0374%20-%20Detection%20Strategy%20for%20Serverless%20Execution%20%28T1648%29.md)

## Sources

- [Microsoft DART Case Report 001](https://www.microsoft.com/security/blog/2020/03/09/real-life-cybercrime-stories-dart-microsoft-detection-and-response-team)
- [Backdooring an AWS account](https://medium.com/daniel-grzelak/backdooring-an-aws-account-da007d36f8f9)
- [Varonis Power Automate Data Exfiltration](https://www.varonis.com/blog/power-automate-data-exfiltration)
- [Cloud Hack Tricks GWS Apps Script](https://cloud.hacktricks.xyz/pentesting-cloud/workspace-security/gws-google-platforms-phishing/gws-app-scripts)
- [OWN-CERT Google App Script 2024](https://www.own.security/ressources/blog/google-workspace-malicious-app-script-analysis)
- [Cado Security Denonia](https://www.cadosecurity.com/cado-discovers-denonia-the-first-malware-specifically-targeting-lambda/)
- [Rhino Security Labs AWS Privilege Escalation](https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/)
- [Rhingo Security Labs GCP Privilege Escalation](https://rhinosecuritylabs.com/gcp/privilege-escalation-google-cloud-platform-part-1/)
