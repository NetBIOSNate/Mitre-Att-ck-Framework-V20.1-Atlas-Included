# T1558.004 - AS-REP Roasting

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1558 - Steal or Forge Kerberos Tickets](../README.md)

Adversaries may reveal credentials of accounts that have disabled Kerberos preauthentication by [Password Cracking](https://attack.mitre.org/techniques/T1110/002) Kerberos messages.(Citation: Harmj0y Roasting AS-REPs Jan 2017) 

Preauthentication offers protection against offline [Password Cracking](https://attack.mitre.org/techniques/T1110/002). When enabled, a user requesting access to a resource initiates communication with the Domain Controller (DC) by sending an Authentication Server Request (AS-REQ) message with a timestamp that is encrypted with the hash of their password. If and only if the DC is able to successfully decrypt the timestamp with the hash of the user’s password, it will then send an Authentication Server Response (AS-REP) message that contains the Ticket Granting Ticket (TGT) to the user. Part of the AS-REP message is signed with the user’s password.(Citation: Microsoft Kerberos Preauth 2014)

For each account found without preauthentication, an adversary may send an AS-REQ message without the encrypted timestamp and receive an AS-REP message with TGT data which may be encrypted with an insecure algorithm such as RC4. The recovered encrypted data may be vulnerable to offline [Password Cracking](https://attack.mitre.org/techniques/T1110/002) attacks similarly to [Kerberoasting](https://attack.mitre.org/techniques/T1558/003) and expose plaintext credentials.(Citation: Harmj0y Roasting AS-REPs Jan 2017)(Citation: Stealthbits Cracking AS-REP Roasting Jun 2019) 

An account registered to a domain, with or without special privileges, can be abused to list all domain accounts that have preauthentication disabled by utilizing Windows tools like [PowerShell](https://attack.mitre.org/techniques/T1059/001) with an LDAP filter. Alternatively, the adversary may send an AS-REQ message for each user. If the DC responds without errors, the account does not require preauthentication and the AS-REP message will already contain the encrypted data.(Citation: Harmj0y Roasting AS-REPs Jan 2017)(Citation: Stealthbits Cracking AS-REP Roasting Jun 2019)

Cracked hashes may enable [Persistence](https://attack.mitre.org/tactics/TA0003), [Privilege Escalation](https://attack.mitre.org/tactics/TA0004), and [Lateral Movement](https://attack.mitre.org/tactics/TA0008) via access to [Valid Accounts](https://attack.mitre.org/techniques/T1078).(Citation: SANS Attacking Kerberos Nov 2014)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1558/004)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Kerberos preauthentication is enabled by default. Older protocols might not support preauthentication therefore it is possible to have this setting disabled. Make sure that all accounts have preauthentication whenever possible and audit changes to setting. Windows tools such as PowerShell may be used to easily find which accounts have preauthentication disabled. (Citation: Microsoft Preauthentication Jul 2012)(Citation: Stealthbits Cracking AS-REP Roasting Jun 2019) [Microsoft Preauthentication Jul 2012](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-2000-server/cc961961%28v=technet.10%29?redirectedfrom=MSDN) · [Stealthbits Cracking AS-REP Roasting Jun 2019](https://blog.stealthbits.com/cracking-active-directory-passwords-with-as-rep-roasting/)
- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Enable AES Kerberos encryption (or another stronger encryption algorithm), rather than RC4, where possible.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure strong password length (ideally 25+ characters) and complexity for service accounts and that these passwords periodically expire. Also consider using Group Managed Service Accounts or another third party product such as password vaulting. (Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)

## Detection strategies

- [DET0113 - Detect AS-REP Roasting Attempts (T1558.004)](../../../../Defenses/Detection%20Strategies/DET0113%20-%20Detect%20AS-REP%20Roasting%20Attempts%20%28T1558.004%29.md)

## Procedure examples

- [S1071 - Rubeus](../../../../Threat%20Intelligence/Software/Tools/S1071%20-%20Rubeus.md) — [Rubeus](https://attack.mitre.org/software/S1071) can reveal the credentials of accounts that have Kerberos pre-authentication disabled through AS-REP roasting.(Citation: GitHub Rubeus March 2023)(Citation: DFIR Ryuk's Return October 2020)(Citation: DFIR Ryuk 2 Hour Speed Run November 2020) [GitHub Rubeus March 2023](https://github.com/GhostPack/Rubeus) · [DFIR Ryuk 2 Hour Speed Run November 2020](https://thedfirreport.com/2020/11/05/ryuk-speed-run-2-hours-to-ransom/) · [DFIR Ryuk's Return October 2020](https://thedfirreport.com/2020/10/08/ryuks-return/)

## Sources

- [Harmj0y Roasting AS-REPs Jan 2017](https://blog.harmj0y.net/activedirectory/roasting-as-reps/)
- [Stealthbits Cracking AS-REP Roasting Jun 2019](https://blog.stealthbits.com/cracking-active-directory-passwords-with-as-rep-roasting/)
- [SANS Attacking Kerberos Nov 2014](https://redsiege.com/kerberoast-slides)
- [Microsoft Kerberos Preauth 2014](https://social.technet.microsoft.com/wiki/contents/articles/23559.kerberos-pre-authentication-why-it-should-not-be-disabled.aspx)
