# T1621 - Multi-Factor Authentication Request Generation

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may attempt to bypass multi-factor authentication (MFA) mechanisms and gain access to accounts by generating MFA requests sent to users.

Adversaries in possession of credentials to [Valid Accounts](https://attack.mitre.org/techniques/T1078) may be unable to complete the login process if they lack access to the 2FA or MFA mechanisms required as an additional credential and security control. To circumvent this, adversaries may abuse the automatic generation of push notifications to MFA services such as Duo Push, Microsoft Authenticator, Okta, or similar services to have the user grant access to their account. If adversaries lack credentials to victim accounts, they may also abuse automatic push notification generation when this option is configured for self-service password reset (SSPR).(Citation: Obsidian SSPR Abuse 2023)

In some cases, adversaries may continuously repeat login attempts in order to bombard users with MFA push notifications, SMS messages, and phone calls, potentially resulting in the user finally accepting the authentication request in response to “MFA fatigue.”(Citation: Russian 2FA Push Annoyance - Cimpanu)(Citation: MFA Fatigue Attacks - PortSwigger)(Citation: Suspected Russian Activity Targeting Government and Business Entities Around the Globe)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1621)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [IaaS](../../../Platforms/IaaS.md), [SaaS](../../../Platforms/SaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md)

## Procedure examples

- [G0016 - APT29](../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has used repeated MFA requests to gain access to victim accounts.(Citation: Suspected Russian Activity Targeting Government and Business Entities Around the Globe)(Citation: NCSC et al APT29 2024) [Suspected Russian Activity Targeting Government and Business Entities Around the Globe](https://www.mandiant.com/resources/russian-targeting-gov-business) · [NCSC et al APT29 2024](https://www.ic3.gov/Media/News/2024/240226.pdf)
- [C0027 - C0027](../../../Threat%20Intelligence/Campaigns/C0027%20-%20C0027.md) — During [C0027](https://attack.mitre.org/campaigns/C0027), [Scattered Spider](https://attack.mitre.org/groups/G1015) attempted to gain access by continuously sending MFA messages to the victim until they accept the MFA push challenge.(Citation: Crowdstrike TELCO BPO Campaign December 2022) [Crowdstrike TELCO BPO Campaign December 2022](https://www.crowdstrike.com/blog/analysis-of-intrusion-campaign-targeting-telecom-and-bpo-companies/)
- [G1004 - LAPSUS$](../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has spammed target users with MFA prompts in the hope that the legitimate user will grant necessary approval.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [G1015 - Scattered Spider](../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has used multifactor authentication (MFA) fatigue by sending repeated MFA authentication requests to targets.(Citation: CrowdStrike Scattered Spider BYOVD January 2023)(Citation: Check Point Scattered Spider JUL 2025) [Check Point Scattered Spider JUL 2025](https://blog.checkpoint.com/research/exposing-scattered-spider-new-indicators-highlight-growing-threat-to-enterprises-and-aviation/) · [CrowdStrike Scattered Spider BYOVD January 2023](https://www.crowdstrike.com/blog/scattered-spider-attempts-to-avoid-detection-with-bring-your-own-vulnerable-driver-tactic/)

## Detection strategies

- [DET0160 - Detection Strategy for Multi-Factor Authentication Request Generation (T1621)](../../../Defenses/Detection%20Strategies/DET0160%20-%20Detection%20Strategy%20for%20Multi-Factor%20Authentication%20Request%20Generation%20%28T1621%29.md)

## Mitigations

- [M1036 - Account Use Policies](../../../Defenses/Mitigations/M1036%20-%20Account%20Use%20Policies.md) — Enable account restrictions to prevent login attempts, and the subsequent 2FA/MFA service requests, from being initiated from suspicious locations or when the source of the login attempts do not match the location of the 2FA/MFA smart device. Use conditional access policies to block logins from non-compliant devices or from outside defined organization IP ranges.(Citation: Microsoft Common Conditional Access Policies) [Microsoft Common Conditional Access Policies](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common)
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Implement more secure 2FA/MFA mechanisms in replacement of simple push or one-click 2FA/MFA options. For example, having users enter a one-time code provided by the login screen into the 2FA/MFA application or utilizing other out-of-band 2FA/MFA mechanisms (such as rotating code-based hardware tokens providing rotating codes that need an accompanying user pin) may be more secure. Furthermore, change default configurations and implement limits upon the maximum number of 2FA/MFA request prompts that can be sent to users in period of time.(Citation: MFA Fatigue Attacks - PortSwigger) [MFA Fatigue Attacks - PortSwigger](https://portswigger.net/daily-swig/mfa-fatigue-attacks-users-tricked-into-allowing-device-access-due-to-overload-of-push-notifications)
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to only accept 2FA/MFA requests from login attempts they initiated, to review source location of the login attempt prompting the 2FA/MFA requests, and to report suspicious/unsolicited prompts.

## Sources

- [Russian 2FA Push Annoyance - Cimpanu](https://therecord.media/russian-hackers-bypass-2fa-by-annoying-victims-with-repeated-push-notifications/)
- [MFA Fatigue Attacks - PortSwigger](https://portswigger.net/daily-swig/mfa-fatigue-attacks-users-tricked-into-allowing-device-access-due-to-overload-of-push-notifications)
- [Suspected Russian Activity Targeting Government and Business Entities Around the Globe](https://www.mandiant.com/resources/russian-targeting-gov-business)
- [Obsidian SSPR Abuse 2023](https://www.obsidiansecurity.com/blog/behind-the-breach-self-service-password-reset-azure-ad/)
