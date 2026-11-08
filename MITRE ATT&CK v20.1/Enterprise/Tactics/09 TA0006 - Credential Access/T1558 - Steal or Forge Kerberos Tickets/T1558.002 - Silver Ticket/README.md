# T1558.002 - Silver Ticket

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1558 - Steal or Forge Kerberos Tickets](../README.md)

Adversaries who have the password hash of a target service account (e.g. SharePoint, MSSQL) may forge Kerberos ticket granting service (TGS) tickets, also known as silver tickets. Kerberos TGS tickets are also known as service tickets.(Citation: ADSecurity Silver Tickets)

Silver tickets are more limited in scope than golden tickets in that they only enable adversaries to access a particular resource (e.g. MSSQL) and the system that hosts the resource; however, unlike golden tickets, adversaries with the ability to forge silver tickets are able to create TGS tickets without interacting with the Key Distribution Center (KDC), potentially making detection more difficult.(Citation: ADSecurity Detecting Forged Tickets)

Password hashes for target services may be obtained using [OS Credential Dumping](https://attack.mitre.org/techniques/T1003) or [Kerberoasting](https://attack.mitre.org/techniques/T1558/003).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1558/002)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Enable AES Kerberos encryption (or another stronger encryption algorithm), rather than RC4, where possible.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure strong password length (ideally 25+ characters) and complexity for service accounts and that these passwords periodically expire.(Citation: AdSecurity Cracking Kerberos Dec 2015) Also consider using Group Managed Service Accounts or another third party product such as password vaulting.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit service accounts to minimal required privileges, including membership in privileged groups such as Domain Administrators.(Citation: AdSecurity Cracking Kerberos Dec 2015) [AdSecurity Cracking Kerberos Dec 2015](https://adsecurity.org/?p=2293)

## Procedure examples

- [S0677 - AADInternals](../../../../Threat%20Intelligence/Software/Tools/S0677%20-%20AADInternals.md) — [AADInternals](https://attack.mitre.org/software/S0677) can be used to forge Kerberos tickets using the password hash of the AZUREADSSOACC account.(Citation: AADInternals Documentation) [AADInternals Documentation](https://o365blog.com/aadinternals)
- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can leverage its implementation of [Mimikatz](https://attack.mitre.org/software/S0002) to obtain and use silver tickets.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0002 - Mimikatz](../../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — [Mimikatz](https://attack.mitre.org/software/S0002)'s kerberos module can create silver tickets.(Citation: GitHub Mimikatz kerberos Module) [GitHub Mimikatz kerberos Module](https://github.com/gentilkiwi/mimikatz/wiki/module-~-kerberos)
- [S1071 - Rubeus](../../../../Threat%20Intelligence/Software/Tools/S1071%20-%20Rubeus.md) — [Rubeus](https://attack.mitre.org/software/S1071) can create silver tickets.(Citation: GitHub Rubeus March 2023) [GitHub Rubeus March 2023](https://github.com/GhostPack/Rubeus)

## Detection strategies

- [DET0241 - Detect Forged Kerberos Silver Tickets (T1558.002)](../../../../Defenses/Detection%20Strategies/DET0241%20-%20Detect%20Forged%20Kerberos%20Silver%20Tickets%20%28T1558.002%29.md)

## Sources

- [ADSecurity Detecting Forged Tickets](https://adsecurity.org/?p=1515)
- [ADSecurity Silver Tickets](https://adsecurity.org/?p=2011)
