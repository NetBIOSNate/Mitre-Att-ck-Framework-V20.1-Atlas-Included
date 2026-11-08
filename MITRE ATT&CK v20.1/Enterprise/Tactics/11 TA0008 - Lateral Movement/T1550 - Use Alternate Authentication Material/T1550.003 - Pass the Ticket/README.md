# T1550.003 - Pass the Ticket

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1550 - Use Alternate Authentication Material](../README.md)

Adversaries may “pass the ticket” using stolen Kerberos tickets to move laterally within an environment, bypassing normal system access controls. Pass the ticket (PtT) is a method of authenticating to a system using Kerberos tickets without having access to an account's password. Kerberos authentication can be used as the first step to lateral movement to a remote system.

When performing PtT, valid Kerberos tickets for [Valid Accounts](https://attack.mitre.org/techniques/T1078) are captured by [OS Credential Dumping](https://attack.mitre.org/techniques/T1003). A user's service tickets or ticket granting ticket (TGT) may be obtained, depending on the level of access. A service ticket allows for access to a particular resource, whereas a TGT can be used to request service tickets from the Ticket Granting Service (TGS) to access any resource the user has privileges to access.(Citation: ADSecurity AD Kerberos Attacks)(Citation: GentilKiwi Pass the Ticket)

A [Silver Ticket](https://attack.mitre.org/techniques/T1558/002) can be obtained for services that use Kerberos as an authentication mechanism and are used to generate tickets to access that particular resource and the system that hosts the resource (e.g., SharePoint).(Citation: ADSecurity AD Kerberos Attacks)

A [Golden Ticket](https://attack.mitre.org/techniques/T1558/001) can be obtained for the domain using the Key Distribution Service account KRBTGT account NTLM hash, which enables generation of TGTs for any account in Active Directory.(Citation: Campbell 2014)

Adversaries may also create a valid Kerberos ticket using other user information, such as stolen password hashes or AES keys. For example, "overpassing the hash" involves using an NTLM password hash to authenticate as a user (i.e. [Pass the Hash](https://attack.mitre.org/techniques/T1550/002)) while also using the password hash to create a valid Kerberos ticket.(Citation: Stealthbits Overpass-the-Hash)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1550/003)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) used Kerberos ticket attacks for lateral movement.(Citation: Mandiant No Easy Breach) [Mandiant No Easy Breach](https://www.slideshare.net/slideshow/no-easy-breach-derby-con-2016/66447908)
- [G0050 - APT32](../../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) successfully gained remote access by using pass the ticket.(Citation: Cybereason Cobalt Kitty 2017) [Cybereason Cobalt Kitty 2017](https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf)
- [G0060 - BRONZE BUTLER](../../../../Threat%20Intelligence/Groups/G0060%20-%20BRONZE%20BUTLER.md) — [BRONZE BUTLER](https://attack.mitre.org/groups/G0060) has created forged Kerberos Ticket Granting Ticket (TGT) and Ticket Granting Service (TGS) tickets to maintain administrative access.(Citation: Secureworks BRONZE BUTLER Oct 2017) [Secureworks BRONZE BUTLER Oct 2017](https://www.secureworks.com/research/bronze-butler-targets-japanese-businesses)
- [S0002 - Mimikatz](../../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — [Mimikatz](https://attack.mitre.org/software/S0002)’s <code>LSADUMP::DCSync</code> and <code>KERBEROS::PTT</code> modules implement the three steps required to extract the krbtgt account hash and create/use Kerberos tickets.(Citation: Adsecurity Mimikatz Guide)(Citation: AdSecurity Kerberos GT Aug 2015)(Citation: Harmj0y DCSync Sept 2015)(Citation: NCSC Joint Report Public Tools) [AdSecurity Kerberos GT Aug 2015](https://adsecurity.org/?p=1640) · [Adsecurity Mimikatz Guide](https://adsecurity.org/?page_id=1821) · [Harmj0y DCSync Sept 2015](https://web.archive.org/web/20150923020927/http://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/) · [NCSC Joint Report Public Tools](https://www.ncsc.gov.uk/report/joint-report-on-publicly-available-hacking-tools)
- [S0192 - Pupy](../../../../Threat%20Intelligence/Software/Tools/S0192%20-%20Pupy.md) — [Pupy](https://attack.mitre.org/software/S0192) can also perform pass-the-ticket.(Citation: GitHub Pupy) [GitHub Pupy](https://github.com/n1nj4sec/pupy)
- [S0053 - SeaDuke](../../../../Threat%20Intelligence/Software/Malware/S0053%20-%20SeaDuke.md) — Some [SeaDuke](https://attack.mitre.org/software/S0053) samples have a module to use pass the ticket with Kerberos for authentication.(Citation: Symantec Seaduke 2015) [Symantec Seaduke 2015](https://web.archive.org/web/20150717011546/http://www.symantec.com/connect/blogs/forkmeiamfamous-seaduke-latest-weapon-duke-armory)

## Mitigations

- [M1015 - Active Directory Configuration](../../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — To contain the impact of a previously generated golden ticket, reset the built-in KRBTGT account password twice, which will invalidate any existing golden tickets that have been created with the KRBTGT hash and other Kerberos tickets derived from it.(Citation: ADSecurity Kerberos and KRBTGT) For each domain, change the KRBTGT account password once, force replication, and then change the password a second time. Consider rotating the KRBTGT account password every 180 days.(Citation: STIG krbtgt reset) [ADSecurity Kerberos and KRBTGT](https://adsecurity.org/?p=483) · [STIG krbtgt reset](https://web.archive.org/web/20240428080127/https://www.stigviewer.com/stig/windows_server_2016/2019-12-12/finding/V-91779)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure that local administrator accounts have complex, unique passwords.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit domain admin account permissions to domain controllers and limited servers. Delegate other admin functions to separate accounts.(Citation: ADSecurity AD Kerberos Attacks) [ADSecurity AD Kerberos Attacks](https://adsecurity.org/?p=556)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Do not allow a user to be a local administrator for multiple systems.

## Detection strategies

- [DET0352 - Detection Strategy for T1550.003 - Pass the Ticket (Windows)](../../../../Defenses/Detection%20Strategies/DET0352%20-%20Detection%20Strategy%20for%20T1550.003%20-%20Pass%20the%20Ticket%20%28Windows%29.md)

## Sources

- [Campbell 2014](https://defcon.org/images/defcon-22/dc-22-presentations/Campbell/DEFCON-22-Christopher-Campbell-The-Secret-Life-of-Krbtgt.pdf)
- [GentilKiwi Pass the Ticket](https://web.archive.org/web/20210515214027/https://blog.gentilkiwi.com/securite/mimikatz/pass-the-ticket-kerberos)
- [ADSecurity AD Kerberos Attacks](https://adsecurity.org/?p=556)
- [Stealthbits Overpass-the-Hash](https://stealthbits.com/blog/how-to-detect-overpass-the-hash-attacks/)
