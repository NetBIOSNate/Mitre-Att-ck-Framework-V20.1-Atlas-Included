# T1110.001 - Password Guessing

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1110 - Brute Force](../README.md)

Adversaries with no prior knowledge of legitimate credentials within the system or environment may guess passwords to attempt access to accounts. Without knowledge of the password for an account, an adversary may opt to systematically guess the password using a repetitive or iterative mechanism. An adversary may guess login credentials without prior knowledge of system or environment passwords during an operation by using a list of common passwords. Password guessing may or may not take into account the target's policies on password complexity or use policies that may lock accounts out after a number of failed attempts.

Guessing passwords can be a risky option because it could cause numerous authentication failures and account lockouts, depending on the organization's login failure policies.(Citation: Cylance Cleaver)

Typically, management services over commonly used ports are used when guessing passwords. Commonly targeted services include the following:

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
* SNMP (161/UDP and 162/TCP/UDP)

In addition to management services, adversaries may "target single sign-on (SSO) and cloud-based applications utilizing federated authentication protocols," as well as externally facing email applications, such as Office 365.(Citation: US-CERT TA18-068A 2018) Further, adversaries may abuse network device interfaces (such as `wlanAPI`) to brute force accessible wifi-router(s) via wireless authentication protocols.(Citation: Trend Micro Emotet 2020)

In default environments, LDAP and Kerberos connection attempts are less likely to trigger events over SMB, which creates Windows "logon failure" event ID 4625.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1110/001)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md), [ESXi](../../../../Platforms/ESXi.md), [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has used a brute-force/password-spray tooling that operated in two modes: in brute-force mode it typically sent over 300 authentication attempts per hour per targeted account over the course of several hours or days.(Citation: Microsoft STRONTIUM New Patterns Cred Harvesting Sept 2020) [APT28](https://attack.mitre.org/groups/G0007) has also used a Kubernetes cluster to conduct distributed, large-scale password guessing attacks.(Citation: Cybersecurity Advisory GRU Brute Force Campaign July 2021) [Microsoft STRONTIUM New Patterns Cred Harvesting Sept 2020](https://www.microsoft.com/security/blog/2020/09/10/strontium-detecting-new-patters-credential-harvesting/) · [Cybersecurity Advisory GRU Brute Force Campaign July 2021](https://media.defense.gov/2021/Jul/01/2002753896/-1/-1/1/CSA_GRU_GLOBAL_BRUTE_FORCE_CAMPAIGN_UOO158036-21.PDF)
- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has successfully conducted password guessing attacks against a list of mailboxes.(Citation: Mandiant APT29 Microsoft 365 2022) [Mandiant APT29 Microsoft 365 2022](https://www.mandiant.com/resources/blog/apt29-continues-targeting-microsoft)
- [S0020 - China Chopper](../../../../Threat%20Intelligence/Software/Malware/S0020%20-%20China%20Chopper.md) — [China Chopper](https://attack.mitre.org/software/S0020)'s server component can perform brute force password guessing against authentication portals.(Citation: FireEye Periscope March 2018) [FireEye Periscope March 2018](https://www.fireeye.com/blog/threat-research/2018/03/suspected-chinese-espionage-group-targeting-maritime-and-engineering-industries.html)
- [S0488 - CrackMapExec](../../../../Threat%20Intelligence/Software/Tools/S0488%20-%20CrackMapExec.md) — [CrackMapExec](https://attack.mitre.org/software/S0488) can brute force passwords for a specified user on a single target system or across an entire network.(Citation: CME Github September 2018) [CME Github September 2018](https://github.com/byt3bl33d3r/CrackMapExec/wiki/SMB-Command-Reference)
- [S0367 - Emotet](../../../../Threat%20Intelligence/Software/Malware/S0367%20-%20Emotet.md) — [Emotet](https://attack.mitre.org/software/S0367) has been observed using a hard coded list of passwords to brute force user accounts. (Citation: Malwarebytes Emotet Dec 2017)(Citation: Symantec Emotet Jul 2018)(Citation: US-CERT Emotet Jul 2018)(Citation: Secureworks Emotet Nov 2018)(Citation: CIS Emotet Dec 2018)(Citation: Binary Defense Emotes Wi-Fi Spreader) [Binary Defense Emotes Wi-Fi Spreader](https://www.binarydefense.com/resources/blog/emotet-evolves-with-new-wi-fi-spreader/) · [CIS Emotet Dec 2018](https://www.cisecurity.org/white-papers/ms-isac-security-primer-emotet/) · [Secureworks Emotet Nov 2018](https://www.secureworks.com/blog/lazy-passwords-become-rocket-fuel-for-emotet-smb-spreader) · [Malwarebytes Emotet Dec 2017](https://support.malwarebytes.com/docs/DOC-2295) · [Symantec Emotet Jul 2018](https://www.symantec.com/blogs/threat-intelligence/evolution-emotet-trojan-distributor) · [US-CERT Emotet Jul 2018](https://www.us-cert.gov/ncas/alerts/TA18-201A)
- [S0698 - HermeticWizard](../../../../Threat%20Intelligence/Software/Malware/S0698%20-%20HermeticWizard.md) — [HermeticWizard](https://attack.mitre.org/software/S0698) can use a list of hardcoded credentials in attempt to authenticate to SMB shares.(Citation: ESET Hermetic Wizard March 2022) [ESET Hermetic Wizard March 2022](https://www.welivesecurity.com/2022/03/01/isaacwiper-hermeticwizard-wiper-worm-targeting-ukraine)
- [S0532 - Lucifer](../../../../Threat%20Intelligence/Software/Malware/S0532%20-%20Lucifer.md) — [Lucifer](https://attack.mitre.org/software/S0532) has attempted to brute force TCP ports 135 (RPC) and 1433 (MSSQL) with the default username or list of usernames and passwords.(Citation: Unit 42 Lucifer June 2020) [Unit 42 Lucifer June 2020](https://unit42.paloaltonetworks.com/lucifer-new-cryptojacking-and-ddos-hybrid-malware/)
- [S0598 - P.A.S. Webshell](../../../../Threat%20Intelligence/Software/Malware/S0598%20-%20P.A.S.%20Webshell.md) — [P.A.S. Webshell](https://attack.mitre.org/software/S0598) can use predefined users and passwords to execute brute force attacks against SSH, FTP, POP3, MySQL, MSSQL, and PostgreSQL services.(Citation: ANSSI Sandworm January 2021) [ANSSI Sandworm January 2021](https://www.cert.ssi.gouv.fr/uploads/CERTFR-2021-CTI-005.pdf)
- [S0453 - Pony](../../../../Threat%20Intelligence/Software/Malware/S0453%20-%20Pony.md) — [Pony](https://attack.mitre.org/software/S0453) has used a small dictionary of common passwords against a collected list of local accounts.(Citation: Malwarebytes Pony April 2016) [Malwarebytes Pony April 2016](https://blog.malwarebytes.com/threat-analysis/2015/11/no-money-but-pony-from-a-mail-to-a-trojan-horse/)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has used weak credentials to gain access to victim devices.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a)
- [S0374 - SpeakUp](../../../../Threat%20Intelligence/Software/Malware/S0374%20-%20SpeakUp.md) — [SpeakUp](https://attack.mitre.org/software/S0374) can perform brute forcing using a pre-defined list of usernames and passwords in an attempt to log in to administrative panels. (Citation: CheckPoint SpeakUp Feb 2019) [CheckPoint SpeakUp Feb 2019](https://research.checkpoint.com/speakup-a-new-undetected-backdoor-linux-trojan/)
- [G1055 - VOID MANTICORE](../../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has conducted password guessing to gain initial access.(Citation: Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026) [Domain Tools Handala Hack Karma Homeland Justice MOIS April 2026](https://dti.domaintools.com/research/handala-mois-linked-cyber-influence-ecosystem-threat-intelligence-assessment)
- [S0341 - Xbash](../../../../Threat%20Intelligence/Software/Malware/S0341%20-%20Xbash.md) — [Xbash](https://attack.mitre.org/software/S0341) can obtain a list of weak passwords from the C2 server to use for brute forcing as well as attempt to brute force services with open ports.(Citation: Unit42 Xbash Sept 2018)(Citation: Trend Micro Xbash Sept 2018) [Unit42 Xbash Sept 2018](https://researchcenter.paloaltonetworks.com/2018/09/unit42-xbash-combines-botnet-ransomware-coinmining-worm-targets-linux-windows/) · [Trend Micro Xbash Sept 2018](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/new-multi-platform-xbash-packs-obfuscation-ransomware-coinminer-worm-and-botnet)

## Mitigations

- [M1036 - Account Use Policies](../../../../Defenses/Mitigations/M1036%20-%20Account%20Use%20Policies.md) — Set account lockout policies after a certain number of failed login attempts to prevent passwords from being guessed. Too strict a policy may create a denial of service condition and render environments un-usable, with all accounts used in the brute force being locked-out. Use conditional access policies to block logins from non-compliant devices or from outside defined organization IP ranges.(Citation: Microsoft Common Conditional Access Policies) Consider blocking risky authentication requests, such as those originating from anonymizing services/proxies.(Citation: Okta Block Anonymizing Services) [Microsoft Common Conditional Access Policies](https://learn.microsoft.com/en-us/azure/active-directory/conditional-access/concept-conditional-access-policy-common) · [Okta Block Anonymizing Services](https://sec.okta.com/blockanonymizers)
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication. Where possible, also enable multi-factor authentication on externally facing services.
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Upgrade management services to the latest supported and compatible version. Specifically, any version providing increased password complexity or policy enforcement preventing default or weak passwords.

## Detection strategies

- [DET0551 - Password Guessing via Multi-Source Authentication Failure Correlation](../../../../Defenses/Detection%20Strategies/DET0551%20-%20Password%20Guessing%20via%20Multi-Source%20Authentication%20Failure%20Correlation.md)

## Sources

- [Trend Micro Emotet 2020](https://www.trendmicro.com/vinfo/us/security/news/cybercrime-and-digital-threats/emotet-now-spreads-via-wi-fi)
- [Cylance Cleaver](https://web.archive.org/web/20200302085133/https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf)
- [US-CERT TA18-068A 2018](https://www.us-cert.gov/ncas/alerts/TA18-086A)
