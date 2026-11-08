# T1111 - Multi-Factor Authentication Interception

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may target multi-factor authentication (MFA) mechanisms, (i.e., smart cards, token generators, etc.) to gain access to credentials that can be used to access systems, services, and network resources. Use of MFA is recommended and provides a higher level of security than usernames and passwords alone, but organizations should be aware of techniques that could be used to intercept and bypass these security mechanisms. 

If a smart card is used for multi-factor authentication, then a keylogger will need to be used to obtain the password associated with a smart card during normal use. With both an inserted card and access to the smart card password, an adversary can connect to a network resource using the infected system to proxy the authentication with the inserted hardware token.(Citation: Mandiant M Trends 2011)

Adversaries may also employ a keylogger to similarly target other hardware tokens, such as RSA SecurID. Capturing token input (including a user's personal identification code) may provide temporary access (i.e. replay the one-time passcode until the next value rollover) as well as possibly enabling adversaries to reliably predict future authentication values (given access to both the algorithm and any seed values used to generate appended temporary codes).(Citation: GCN RSA June 2011)

Other methods of MFA may be intercepted and used by an adversary to authenticate. It is common for one-time codes to be sent via out-of-band communications (email, SMS). If the device and/or service is not secured, then it may be vulnerable to interception. Service providers can also be targeted: for example, an adversary may compromise an SMS messaging service in order to steal MFA codes sent to users’ phones.(Citation: Okta Scatter Swine 2022)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1111)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [G1044 - APT42](../../../Threat%20Intelligence/Groups/G1044%20-%20APT42.md) — [APT42](https://attack.mitre.org/groups/G1044) has intercepted SMS-based one-time passwords and has set up two-factor authentication.(Citation: Mandiant APT42-charms) Additionally, [APT42](https://attack.mitre.org/groups/G1044) has used cloned or fake websites to capture MFA tokens.(Citation: Mandiant APT42-untangling) [Mandiant APT42-charms](https://services.google.com/fh/files/misc/apt42-crooked-charms-cons-and-compromises.pdf) · [Mandiant APT42-untangling](https://cloud.google.com/blog/topics/threat-intelligence/untangling-iran-apt42-operations)
- [G0114 - Chimera](../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114) has registered alternate phone numbers for compromised users to intercept 2FA codes sent via SMS.(Citation: NCC Group Chimera January 2021) [NCC Group Chimera January 2021](https://web.archive.org/web/20230218064220/https://research.nccgroup.com/2021/01/12/abusing-cloud-services-to-fly-under-the-radar/)
- [S9003 - evilginx2](../../../Threat%20Intelligence/Software/Tools/S9003%20-%20evilginx2.md) — [evilginx2](https://attack.mitre.org/software/S9003) can intercept authentication tokens to enable bypass of non-phishing resistant forms of MFA.(Citation: Evilginx 2 July 2018) [Evilginx 2 July 2018](https://breakdev.org/evilginx-2-next-generation-of-phishing-2fa-tokens/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used a proprietary tool to intercept one time passwords required for two-factor authentication.(Citation: KISA Operation Muzabi) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf)
- [G1004 - LAPSUS$](../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has replayed stolen session token and passwords to trigger simple-approval MFA prompts in hope of the legitimate user will grant necessary approval.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [C0049 - Leviathan Australian Intrusions](../../../Threat%20Intelligence/Campaigns/C0049%20-%20Leviathan%20Australian%20Intrusions.md) — [Leviathan](https://attack.mitre.org/groups/G0065) abused compromised appliance access to collect multifactor authentication token values during [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049).(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [C0014 - Operation Wocao](../../../Threat%20Intelligence/Campaigns/C0014%20-%20Operation%20Wocao.md) — During [Operation Wocao](https://attack.mitre.org/campaigns/C0014), threat actors used a custom collection method to intercept two-factor authentication soft tokens.(Citation: FoxIT Wocao December 2019) [FoxIT Wocao December 2019](https://www.fox-it.com/media/kadlze5c/201912_report_operation_wocao.pdf)
- [S1104 - SLOWPULSE](../../../Threat%20Intelligence/Software/Malware/S1104%20-%20SLOWPULSE.md) — [SLOWPULSE](https://attack.mitre.org/software/S1104) can log credentials on compromised Pulse Secure VPNs during the `DSAuth::AceAuthServer::checkUsernamePassword`ACE-2FA authentication procedure.(Citation: Mandiant Pulse Secure Zero-Day April 2021) [Mandiant Pulse Secure Zero-Day April 2021](https://www.mandiant.com/resources/blog/suspected-apt-actors-leverage-bypass-techniques-pulse-secure-zero-day)
- [S0018 - Sykipot](../../../Threat%20Intelligence/Software/Malware/S0018%20-%20Sykipot.md) — [Sykipot](https://attack.mitre.org/software/S0018) is known to contain functionality that enables targeting of smart card technologies to proxy authentication for connections to restricted network resources using detected hardware tokens.(Citation: Alienvault Sykipot DOD Smart Cards) [Alienvault Sykipot DOD Smart Cards](https://www.alienvault.com/open-threat-exchange/blog/sykipot-variant-hijacks-dod-and-windows-smart-cards)

## Detection strategies

- [DET0246 - Detection Strategy for MFA Interception via Input Capture and Smart Card Proxying](../../../Defenses/Detection%20Strategies/DET0246%20-%20Detection%20Strategy%20for%20MFA%20Interception%20via%20Input%20Capture%20and%20Smart%20Card%20Proxying.md)

## Mitigations

- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Remove smart cards when not in use.

## Sources

- [GCN RSA June 2011](https://www.route-fifty.com/cybersecurity/2011/06/rsa-confirms-its-tokens-used-in-lockheed-hack/282818/)
- [Mandiant M Trends 2011](https://dl.mandiant.com/EE/assets/PDF_MTrends_2011.pdf)
- [Okta Scatter Swine 2022](https://sec.okta.com/scatterswine)
