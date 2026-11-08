# T1558 - Steal or Forge Kerberos Tickets

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may attempt to subvert Kerberos authentication by stealing or forging Kerberos tickets to enable [Pass the Ticket](https://attack.mitre.org/techniques/T1550/003). Kerberos is an authentication protocol widely used in modern Windows domain environments. In Kerberos environments, referred to as “realms”, there are three basic participants: client, service, and Key Distribution Center (KDC).(Citation: ADSecurity Kerberos Ring Decoder) Clients request access to a service and through the exchange of Kerberos tickets, originating from KDC, they are granted access after having successfully authenticated. The KDC is responsible for both authentication and ticket granting.  Adversaries may attempt to abuse Kerberos by stealing tickets or forging tickets to enable unauthorized access.

On Windows, the built-in <code>klist</code> utility can be used to list and analyze cached Kerberos tickets.(Citation: Microsoft Klist)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1558)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1558.004 - AS-REP Roasting](T1558.004%20-%20AS-REP%20Roasting/README.md)
- [T1558.005 - Ccache Files](T1558.005%20-%20Ccache%20Files/README.md)
- [T1558.001 - Golden Ticket](T1558.001%20-%20Golden%20Ticket/README.md)
- [T1558.003 - Kerberoasting](T1558.003%20-%20Kerberoasting/README.md)
- [T1558.002 - Silver Ticket](T1558.002%20-%20Silver%20Ticket/README.md)

## Mitigations

- [M1015 - Active Directory Configuration](../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — For containing the impact of a previously generated golden ticket, reset the built-in KRBTGT account password twice, which will invalidate any existing golden tickets that have been created with the KRBTGT hash and other Kerberos tickets derived from it. For each domain, change the KRBTGT account password once, force replication, and then change the password a second time. Consider rotating the KRBTGT account password every 180 days.(Citation: STIG krbtgt reset) [STIG krbtgt reset](https://web.archive.org/web/20240428080127/https://www.stigviewer.com/stig/windows_server_2016/2019-12-12/finding/V-91779)
- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Perform audits or scans of systems, permissions, insecure software, insecure configurations, etc. to identify potential weaknesses.
- [M1043 - Credential Access Protection](../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — On Linux systems, protect resources with Security Enhanced Linux (SELinux) by defining entry points, process types, and file labels.(Citation: Brining MimiKatz to Unix) [Brining MimiKatz to Unix](https://labs.portcullis.co.uk/download/eu-18-Wadhwa-Brown-Where-2-worlds-collide-Bringing-Mimikatz-et-al-to-UNIX.pdf)
- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Enable AES Kerberos encryption (or another stronger encryption algorithm), rather than RC4, where possible.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure strong password length (ideally 25+ characters) and complexity for service accounts and that these passwords periodically expire.(Citation: AdSecurity Cracking Kerberos Dec 2015) Also consider using Group Managed Service Accounts or another third party product such as password vaulting.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit domain admin account permissions to domain controllers and limited servers. Delegate other admin functions to separate accounts. Limit service accounts to minimal required privileges, including membership in privileged groups such as Domain Administrators.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used the [Rubeus](https://attack.mitre.org/software/S1071) tool to forge a Diamond Ticket that is a modified legitimate Kerberos ticket.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G1024 - Akira](../../../Threat%20Intelligence/Groups/G1024%20-%20Akira.md) — [Akira](https://attack.mitre.org/groups/G1024) have used scripts to dump Kerberos authentication credentials.(Citation: Cisco Akira Ransomware OCT 2024) [Cisco Akira Ransomware OCT 2024](https://blog.talosintelligence.com/akira-ransomware-continues-to-evolve/)

## Detection strategies

- [DET0522 - Detect Kerberos Ticket Theft or Forgery (T1558)](../../../Defenses/Detection%20Strategies/DET0522%20-%20Detect%20Kerberos%20Ticket%20Theft%20or%20Forgery%20%28T1558%29.md)

## Sources

- [CERT-EU Golden Ticket Protection](https://cert.europa.eu/static/WhitePapers/UPDATED%20-%20CERT-EU_Security_Whitepaper_2014-007_Kerberos_Golden_Ticket_Protection_v1_4.pdf)
- [Microsoft Detecting Kerberoasting Feb 2018](https://blogs.technet.microsoft.com/motiba/2018/02/23/detecting-kerberoasting-activity-using-azure-security-center/)
- [Medium Detecting Attempts to Steal Passwords from Memory](https://medium.com/threatpunter/detecting-attempts-to-steal-passwords-from-memory-558f16dce4ea)
- [Stealthbits Detect PtT 2019](https://blog.stealthbits.com/detect-pass-the-ticket-attacks)
- [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)
- [ADSecurity Detecting Forged Tickets](https://adsecurity.org/?p=1515)
- [Microsoft Kerberos Golden Ticket](https://gallery.technet.microsoft.com/scriptcenter/Kerberos-Golden-Ticket-b4814285)
- [Microsoft Klist](https://docs.microsoft.com/windows-server/administration/windows-commands/klist)
- [ADSecurity Kerberos Ring Decoder](https://adsecurity.org/?p=227)
