# T1606.002 - SAML Tokens

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1606 - Forge Web Credentials](../README.md)

An adversary may forge SAML tokens with any permissions claims and lifetimes if they possess a valid SAML token-signing certificate.(Citation: Microsoft SolarWinds Steps) The default lifetime of a SAML token is one hour, but the validity period can be specified in the <code>NotOnOrAfter</code> value of the <code>conditions ...</code> element in a token. This value can be changed using the <code>AccessTokenLifetime</code> in a <code>LifetimeTokenPolicy</code>.(Citation: Microsoft SAML Token Lifetimes) Forged SAML tokens enable adversaries to authenticate across services that use SAML 2.0 as an SSO (single sign-on) mechanism.(Citation: Cyberark Golden SAML)

An adversary may utilize [Private Keys](https://attack.mitre.org/techniques/T1552/004) to compromise an organization's token-signing certificate to create forged SAML tokens. If the adversary has sufficient permissions to establish a new federation trust with their own Active Directory Federation Services (AD FS) server, they may instead generate their own trusted token-signing certificate.(Citation: Microsoft SolarWinds Customer Guidance) This differs from [Steal Application Access Token](https://attack.mitre.org/techniques/T1528) and other similar behaviors in that the tokens are new and forged by the adversary, rather than stolen or intercepted from legitimate users.

An adversary may gain administrative Entra ID privileges if a SAML token is forged which claims to represent a highly privileged account. This may lead to [Use Alternate Authentication Material](https://attack.mitre.org/techniques/T1550), which may bypass multi-factor and other authentication protection mechanisms.(Citation: Microsoft SolarWinds Customer Guidance)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1606/002)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md), [IaaS](../../../../Platforms/IaaS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can be used to create SAML tokens using the AD Federated Services token signing certificate.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) created tokens using compromised SAML signing certificates.(Citation: Microsoft - Customer Guidance on Recent Nation-State Cyber Attacks)(Citation: Secureworks IRON RITUAL Profile) [Microsoft - Customer Guidance on Recent Nation-State Cyber Attacks](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/) · [Secureworks IRON RITUAL Profile](https://www.sophos.com/en-us/threat-profiles/iron-ritual)

## Mitigations

- [M1015 - Active Directory Configuration](../../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — For containing the impact of a previously forged SAML token, rotate the token-signing AD FS certificate in rapid succession twice, which will invalidate any tokens generated using the previous certificate.(Citation: Mandiant Defend UNC2452 White Paper) [Mandiant Defend UNC2452 White Paper](https://www.mandiant.com/resources/blog/remediation-and-hardening-strategies-for-microsoft-365-to-defend-against-unc2452)
- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Enable advanced auditing on AD FS. Check the success and failure audit options in the AD FS Management snap-in. Enable Audit Application Generated events on the AD FS farm via Group Policy Object.(Citation: FireEye ADFS) [FireEye ADFS](https://www.troopers.de/troopers19/agenda/fpxwmn/)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict permissions and access to the AD FS server to only originate from privileged access workstations.(Citation: FireEye ADFS) [FireEye ADFS](https://www.troopers.de/troopers19/agenda/fpxwmn/)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that user accounts with administrative rights follow best practices, including use of privileged access workstations, Just in Time/Just Enough Administration (JIT/JEA), and strong authentication. Reduce the number of users that are members of highly privileged Directory Roles.(Citation: Microsoft SolarWinds Customer Guidance) [Microsoft SolarWinds Customer Guidance](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)

## Detection strategies

- [DET0148 - Detection Strategy for Forged SAML Tokens](../../../../Defenses/Detection%20Strategies/DET0148%20-%20Detection%20Strategy%20for%20Forged%20SAML%20Tokens.md)

## Sources

- [Microsoft SolarWinds Steps](https://blogs.microsoft.com/on-the-issues/2020/12/13/customers-protect-nation-state-cyberattacks/)
- [Microsoft SAML Token Lifetimes](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-configurable-token-lifetimes)
- [Microsoft SolarWinds Customer Guidance](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)
- [Cyberark Golden SAML](https://www.cyberark.com/resources/threat-research-blog/golden-saml-newly-discovered-attack-technique-forges-authentication-to-cloud-apps)
- [Sygnia Golden SAML](https://www.sygnia.co/threat-reports-and-advisories/golden-saml-attack/)
