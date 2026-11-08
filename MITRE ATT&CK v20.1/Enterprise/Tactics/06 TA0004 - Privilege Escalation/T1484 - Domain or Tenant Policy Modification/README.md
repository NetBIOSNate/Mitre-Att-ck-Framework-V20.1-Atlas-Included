# T1484 - Domain or Tenant Policy Modification

[Enterprise](../../../README.md) / [Privilege Escalation](../README.md)

Adversaries may modify the configuration settings of a domain or identity tenant to evade defenses and/or escalate privileges in centrally managed environments. Such services provide a centralized means of managing identity resources such as devices and accounts, and often include configuration settings that may apply between domains or tenants such as trust relationships, identity syncing, or identity federation.

Modifications to domain or tenant settings may include altering domain Group Policy Objects (GPOs) in Microsoft Active Directory (AD) or changing trust settings for domains, including federation trust relationships between domains or tenants.

With sufficient permissions, adversaries can modify domain or tenant policy settings. Since configuration settings for these services apply to a large number of identity resources, there are a great number of potential malicious outcomes that can stem from this abuse. Examples of such abuse include:  

* modifying GPOs to push a malicious [Scheduled Task](https://attack.mitre.org/techniques/T1053/005) to computers throughout the domain environment(Citation: ADSecurity GPO Persistence 2016)(Citation: Wald0 Guide to GPOs)(Citation: Harmj0y Abusing GPO Permissions)
* modifying domain trusts to include an adversary-controlled domain, allowing adversaries to  forge access tokens that will subsequently be accepted by victim domain resources(Citation: Microsoft - Customer Guidance on Recent Nation-State Cyber Attacks)
* changing configuration settings within the AD environment to implement a [Rogue Domain Controller](https://attack.mitre.org/techniques/T1207).
* adding new, adversary-controlled federated identity providers to identity tenants, allowing adversaries to authenticate as any user managed by the victim tenant(Citation: Okta Cross-Tenant Impersonation 2023)

Adversaries may temporarily modify domain or tenant policy, carry out a malicious action(s), and then revert the change to remove suspicious indicators.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1484)

**Tactics**  [Privilege Escalation](../README.md), [Defense Impairment](../../08%20TA0112%20-%20Defense%20Impairment/README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Identity Provider](../../../Platforms/Identity%20Provider.md)

## Sub-techniques

- [T1484.001 - Group Policy Modification](T1484.001%20-%20Group%20Policy%20Modification/README.md)
- [T1484.002 - Trust Modification](T1484.002%20-%20Trust%20Modification/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Identify and correct GPO permissions abuse opportunities (ex: GPO modification privileges) using auditing tools such as [BloodHound](https://attack.mitre.org/software/S0521) (version 1.5.1 and later)(Citation: GitHub Bloodhound). [GitHub Bloodhound](https://github.com/BloodHoundAD/BloodHound)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Use least privilege and protect administrative access to the Domain Controller and Active Directory Federation Services (AD FS) server. Do not create service accounts with administrative privileges.
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Consider implementing WMI and security filtering to further tailor which users and computers a GPO will apply to.(Citation: Wald0 Guide to GPOs)(Citation: Microsoft WMI Filters)(Citation: Microsoft GPO Security Filtering) [Wald0 Guide to GPOs](https://wald0.com/?p=179) · [Microsoft WMI Filters](https://blogs.technet.microsoft.com/askds/2008/09/11/fun-with-wmi-filters-in-group-policy/) · [Microsoft GPO Security Filtering](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/Policy/filtering-the-scope-of-a-gpo)

## Detection strategies

- [DET0270 - Detection of Domain or Tenant Policy Modifications via AD and Identity Provider](../../../Defenses/Detection%20Strategies/DET0270%20-%20Detection%20of%20Domain%20or%20Tenant%20Policy%20Modifications%20via%20AD%20and%20Identity%20Provider.md)

## Sources

- [ADSecurity GPO Persistence 2016](https://adsecurity.org/?p=2716)
- [Microsoft - Customer Guidance on Recent Nation-State Cyber Attacks](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)
- [Okta Cross-Tenant Impersonation 2023](https://sec.okta.com/articles/2023/08/cross-tenant-impersonation-prevention-and-detection)
- [Wald0 Guide to GPOs](https://wald0.com/?p=179)
- [Harmj0y Abusing GPO Permissions](https://blog.harmj0y.net/redteaming/abusing-gpo-permissions/)
