# T1110.004 - Credential Stuffing

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1110 - Brute Force](../README.md)

Adversaries may use credentials obtained from breach dumps of unrelated accounts to gain access to target accounts through credential overlap. Occasionally, large numbers of username and password pairs are dumped online when a website or service is compromised and the user account credentials accessed. The information may be useful to an adversary attempting to compromise accounts by taking advantage of the tendency for users to use the same passwords across personal and business accounts.

Credential stuffing is a risky option because it could cause numerous authentication failures and account lockouts, depending on the organization's login failure policies.

Typically, management services over commonly used ports are used when stuffing credentials. Commonly targeted services include the following:

* SSH (22/TCP)
* Telnet (23/TCP)
* FTP (21/TCP)
* NetBIOS / SMB / Samba (139/TCP & 445/TCP)
* LDAP (389/TCP)
* Kerberos (88/TCP)
* RDP / Terminal Services (3389/TCP)
* HTTP/HTTP Management Services (80/TCP & 443/TCP)
* MSSQL (1433/TCP)
* Oracle (1521/TCP)
* MySQL (3306/TCP)
* VNC (5900/TCP)

In addition to management services, adversaries may "target single sign-on (SSO) and cloud-based applications utilizing federated authentication protocols," as well as externally facing email applications, such as Office 365.(Citation: US-CERT TA18-068A 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1110/004)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md), [ESXi](../../../../Platforms/ESXi.md), [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1036 - Account Use Policies](../../../../Defenses/Mitigations/M1036%20-%20Account%20Use%20Policies.md) — Set account lockout policies after a certain number of failed login attempts to prevent passwords from being guessed. Too strict a policy may create a denial of service condition and render environments un-usable, with all accounts used in the brute force being locked-out. Use conditional access policies to block logins from non-compliant devices or from outside defined organization IP ranges.(Citation: Microsoft Common Conditional Access Policies) Consider blocking risky authentication requests, such as those originating from anonymizing services/proxies.(Citation: Okta Block Anonymizing Services) [Microsoft Common Conditional Access Policies](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common) · [Okta Block Anonymizing Services](https://sec.okta.com/blockanonymizers)
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication. Where possible, also enable multi-factor authentication on externally facing services.
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Proactively reset accounts that are known to be part of breached credentials either immediately, or after detecting bruteforce attempts.

## Detection strategies

- [DET0460 - Credential Stuffing Detection via Reused Breached Credentials Across Services](../../../../Defenses/Detection%20Strategies/DET0460%20-%20Credential%20Stuffing%20Detection%20via%20Reused%20Breached%20Credentials%20Across%20Services.md)

## Procedure examples

- [G0114 - Chimera](../../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has used credential stuffing against victim's remote services to obtain valid accounts.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) uses brute-force attack against RDP with rdpscanDll module.(Citation: ESET Trickbot Oct 2020)(Citation: Bitdefender Trickbot March 2020) [ESET Trickbot Oct 2020](https://www.welivesecurity.com/2020/10/12/eset-takes-part-global-operation-disrupt-trickbot/) · [Bitdefender Trickbot March 2020](https://www.bitdefender.com/files/News/CaseStudies/study/316/Bitdefender-Whitepaper-TrickBot-en-EN-interactive.pdf)
- [G1055 - VOID MANTICORE](../../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has utilized credential stuffing attacks to obtain initial access to victim environments.(Citation: Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026) [Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026](https://dti.domaintools.com/research/handala-mois-linked-cyber-influence-ecosystem-threat-intelligence-assessment)

## Sources

- [US-CERT TA18-068A 2018](https://www.us-cert.gov/ncas/alerts/TA18-086A)
