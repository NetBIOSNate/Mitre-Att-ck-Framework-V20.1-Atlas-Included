# T1558.001 - Golden Ticket

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1558 - Steal or Forge Kerberos Tickets](../README.md)

Adversaries who have the KRBTGT account password hash may forge Kerberos ticket-granting tickets (TGT), also known as a golden ticket.(Citation: AdSecurity Kerberos GT Aug 2015) Golden tickets enable adversaries to generate authentication material for any account in Active Directory.(Citation: CERT-EU Golden Ticket Protection) 

Using a golden ticket, adversaries are then able to request ticket granting service (TGS) tickets, which enable access to specific resources. Golden tickets require adversaries to interact with the Key Distribution Center (KDC) in order to obtain TGS.(Citation: ADSecurity Detecting Forged Tickets)

The KDC service runs all on domain controllers that are part of an Active Directory domain. KRBTGT is the Kerberos Key Distribution Center (KDC) service account and is responsible for encrypting and signing all Kerberos tickets.(Citation: ADSecurity Kerberos and KRBTGT) The KRBTGT password hash may be obtained using [OS Credential Dumping](https://attack.mitre.org/techniques/T1003) and privileged access to a domain controller.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1558/001)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can leverage its implementation of [Mimikatz](https://attack.mitre.org/software/S0002) to obtain and use golden tickets.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [G0004 - Ke3chang](../../../../Threat%20Intelligence/Groups/G0004%20-%20Ke3chang.md) — [Ke3chang](https://attack.mitre.org/groups/G0004) has used [Mimikatz](https://attack.mitre.org/software/S0002) to generate Kerberos golden tickets.(Citation: NCC Group APT15 Alive and Strong) [NCC Group APT15 Alive and Strong](https://research.nccgroup.com/2018/03/10/apt15-is-alive-and-strong-an-analysis-of-royalcli-and-royaldns/)
- [S0002 - Mimikatz](../../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — [Mimikatz](https://attack.mitre.org/software/S0002)'s kerberos module can create golden tickets.(Citation: GitHub Mimikatz kerberos Module)(Citation: Cobalt Strike Manual 4.3 November 2020) [GitHub Mimikatz kerberos Module](https://github.com/gentilkiwi/mimikatz/wiki/module-~-kerberos) · [Cobalt Strike Manual 4.3 November 2020](https://web.archive.org/web/20210708035426/https://www.cobaltstrike.com/downloads/csmanual43.pdf)
- [S1071 - Rubeus](../../../../Threat%20Intelligence/Software/Tools/S1071%20-%20Rubeus.md) — [Rubeus](https://attack.mitre.org/software/S1071) can forge a ticket-granting ticket.(Citation: GitHub Rubeus March 2023) [GitHub Rubeus March 2023](https://github.com/GhostPack/Rubeus)
- [S0633 - Sliver](../../../../Threat%20Intelligence/Software/Tools/S0633%20-%20Sliver.md) — [Sliver](https://attack.mitre.org/software/S0633) incorporates the [Rubeus](https://attack.mitre.org/software/S1071) framework to allow for Kerberos ticket manipulation, specifically for forging Kerberos Golden Tickets.(Citation: Cybereason Sliver Undated) [Cybereason Sliver Undated](https://www.cybereason.com/blog/sliver-c2-leveraged-by-many-threat-actors)

## Detection strategies

- [DET0144 - Detect Forged Kerberos Golden Tickets (T1558.001)](../../../../Defenses/Detection%20Strategies/DET0144%20-%20Detect%20Forged%20Kerberos%20Golden%20Tickets%20%28T1558.001%29.md)

## Mitigations

- [M1015 - Active Directory Configuration](../../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — For containing the impact of a previously generated golden ticket, reset the built-in KRBTGT account password twice, which will invalidate any existing golden tickets that have been created with the KRBTGT hash and other Kerberos tickets derived from it. For each domain, change the KRBTGT account password once, force replication, and then change the password a second time. Consider rotating the KRBTGT account password every 180 days.(Citation: STIG krbtgt reset) [STIG krbtgt reset](https://web.archive.org/web/20240428080127/https://www.stigviewer.com/stig/windows_server_2016/2019-12-12/finding/V-91779)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit domain admin account permissions to domain controllers and limited servers. Delegate other admin functions to separate accounts.

## Sources

- [AdSecurity Kerberos GT Aug 2015](https://adsecurity.org/?p=1640)
- [CERT-EU Golden Ticket Protection](https://cert.europa.eu/static/WhitePapers/UPDATED%20-%20CERT-EU_Security_Whitepaper_2014-007_Kerberos_Golden_Ticket_Protection_v1_4.pdf)
- [ADSecurity Detecting Forged Tickets](https://adsecurity.org/?p=1515)
- [ADSecurity Kerberos and KRBTGT](https://adsecurity.org/?p=483)
- [Stealthbits Detect PtT 2019](https://blog.stealthbits.com/detect-pass-the-ticket-attacks)
- [Microsoft Kerberos Golden Ticket](https://gallery.technet.microsoft.com/scriptcenter/Kerberos-Golden-Ticket-b4814285)
