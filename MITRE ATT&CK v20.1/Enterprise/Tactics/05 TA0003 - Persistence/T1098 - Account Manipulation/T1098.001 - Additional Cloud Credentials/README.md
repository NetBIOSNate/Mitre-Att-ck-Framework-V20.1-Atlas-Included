# T1098.001 - Additional Cloud Credentials

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1098 - Account Manipulation](../README.md)

Adversaries may add adversary-controlled credentials to a cloud account to maintain persistent access to victim accounts and instances within the environment.

For example, adversaries may add credentials for Service Principals and Applications in addition to existing legitimate credentials in Azure / Entra ID.(Citation: Microsoft SolarWinds Customer Guidance)(Citation: Blue Cloud of Death)(Citation: Blue Cloud of Death Video) These credentials include both x509 keys and passwords.(Citation: Microsoft SolarWinds Customer Guidance) With sufficient permissions, there are a variety of ways to add credentials including the Azure Portal, Azure command line interface, and Azure or Az PowerShell modules.(Citation: Demystifying Azure AD Service Principals)

In infrastructure-as-a-service (IaaS) environments, after gaining access through [Cloud Accounts](https://attack.mitre.org/techniques/T1078/004), adversaries may generate or import their own SSH keys using either the <code>CreateKeyPair</code> or <code>ImportKeyPair</code> API in AWS or the <code>gcloud compute os-login ssh-keys add</code> command in GCP.(Citation: GCP SSH Key Add) This allows persistent access to instances within the cloud environment without further usage of the compromised cloud accounts.(Citation: Expel IO Evil in AWS)(Citation: Expel Behind the Scenes)

Adversaries may also use the <code>CreateAccessKey</code> API in AWS or the <code>gcloud iam service-accounts keys create</code> command in GCP to add access keys to an account. Alternatively, they may use the <code>CreateLoginProfile</code> API in AWS to add a password that can be used to log into the AWS Management Console for [Cloud Service Dashboard](https://attack.mitre.org/techniques/T1538).(Citation: Permiso Scattered Spider 2023)(Citation: Lacework AI Resource Hijacking 2024) If the target account has different permissions from the requesting account, the adversary may also be able to escalate their privileges in the environment (i.e. [Cloud Accounts](https://attack.mitre.org/techniques/T1078/004)).(Citation: Rhino Security Labs AWS Privilege Escalation)(Citation: Sysdig ScarletEel 2.0) For example, in Entra ID environments, an adversary with the Application Administrator role can add a new set of credentials to their application's service principal. In doing so the adversary would be able to access the service principal’s roles and permissions, which may be different from those of the Application Administrator.(Citation: SpecterOps Azure Privilege Escalation) 

In AWS environments, adversaries with the appropriate permissions may also use the `sts:GetFederationToken` API call to create a temporary set of credentials to [Forge Web Credentials](https://attack.mitre.org/techniques/T1606) tied to the permissions of the original user account. These temporary credentials may remain valid for the duration of their lifetime even if the original account’s API credentials are deactivated.(Citation: Crowdstrike AWS User Federation Persistence)

In Entra ID environments with the app password feature enabled, adversaries may be able to add an app password to a user account.(Citation: Mandiant APT42-untangling) As app passwords are intended to be used with legacy devices that do not support multi-factor authentication (MFA), adding an app password can allow an adversary to bypass MFA requirements. Additionally, app passwords may remain valid even if the user’s primary password is reset.(Citation: Microsoft Entra ID App Passwords)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098/001)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Remove unnecessary and potentially abusable authentication mechanisms where possible. For example, in Entra ID environments, disable the app password feature unless explicitly required.
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for user and privileged accounts. Consider enforcing multi-factor authentication for the <code>CreateKeyPair</code> and <code>ImportKeyPair</code> API calls through IAM policies.(Citation: Expel IO Evil in AWS) [Expel IO Evil in AWS](https://expel.io/blog/finding-evil-in-aws/)
- [M1030 - Network Segmentation](../../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Configure access controls and firewalls to limit access to critical systems and domain controllers. Most cloud environments support separate virtual private cloud (VPC) instances that enable further segmentation of cloud systems.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow domain administrator or root accounts to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that low-privileged user accounts do not have permission to add access keys to accounts. In AWS environments, prohibit users from calling the `sts:GetFederationToken` API unless explicitly required.(Citation: Crowdstrike AWS User Federation Persistence) [Crowdstrike AWS User Federation Persistence](https://www.crowdstrike.com/blog/how-adversaries-persist-with-aws-user-federation/)

## Detection strategies

- [DET0531 - Detection Strategy for Additional Cloud Credentials in IaaS/IdP/SaaS](../../../../Defenses/Detection%20Strategies/DET0531%20-%20Detection%20Strategy%20for%20Additional%20Cloud%20Credentials%20in%20IaaS%20-%20IdP%20-%20SaaS.md)

## Procedure examples

- [C0027 - C0027](../../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) used aws_consoler to create temporary federated credentials for fake users in order to obfuscate which AWS credential is compromised and enable pivoting from the AWS CLI to console sessions without MFA.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [S1091 - Pacu](../../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can generate SSH and API keys for AWS infrastructure and additional API keys for other IAM users.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) added credentials to OAuth Applications and Service Principals.(Citation: Microsoft - Customer Guidance on Recent Nation-State Cyber Attacks)(Citation: CrowdStrike StellarParticle January 2022) [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/) · [Microsoft - Customer Guidance on Recent Nation-State Cyber Attacks](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has reset the password of identified administrator accounts that lack MFA and registered their own MFA method.(Citation: Microsoft Storm-0501 Embargo Ransomware August 2025) [Microsoft Storm-0501 Embargo Ransomware August 2025](https://www.microsoft.com/en-us/security/blog/2025/08/27/storm-0501s-evolving-techniques-lead-to-cloud-based-ransomware/)

## Sources

- [Crowdstrike AWS User Federation Persistence](https://www.crowdstrike.com/blog/how-adversaries-persist-with-aws-user-federation/)
- [Expel IO Evil in AWS](https://expel.io/blog/finding-evil-in-aws/)
- [SpecterOps Azure Privilege Escalation](https://posts.specterops.io/azure-privilege-escalation-via-service-principal-abuse-210ae2be2a5)
- [Demystifying Azure AD Service Principals](https://nedinthecloud.com/2019/07/16/demystifying-azure-ad-service-principals/)
- [Lacework AI Resource Hijacking 2024](https://www.lacework.com/blog/detecting-ai-resource-hijacking-with-composite-alerts)
- [GCP SSH Key Add](https://cloud.google.com/sdk/gcloud/reference/compute/os-login/ssh-keys/add)
- [Permiso Scattered Spider 2023](https://permiso.io/blog/lucr-3-scattered-spider-getting-saas-y-in-the-cloud)
- [Blue Cloud of Death Video](https://www.youtube.com/watch?v=wQ1CuAPnrLM&feature=youtu.be&t=2815)
- [Blue Cloud of Death](https://speakerdeck.com/tweekfawkes/blue-cloud-of-death-red-teaming-azure-1)
- [Microsoft Entra ID App Passwords](https://learn.microsoft.com/en-us/entra/identity/authentication/howto-mfa-app-passwords)
- [Microsoft SolarWinds Customer Guidance](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)
- [Mandiant APT42-untangling](https://cloud.google.com/blog/topics/threat-intelligence/untangling-iran-apt42-operations)
- [Expel Behind the Scenes](https://expel.io/blog/behind-the-scenes-expel-soc-alert-aws/)
- [Sysdig ScarletEel 2.0](https://sysdig.com/blog/scarleteel-2-0/)
- [Rhino Security Labs AWS Privilege Escalation](https://rhinosecuritylabs.com/aws/aws-privilege-escalation-methods-mitigation/)
