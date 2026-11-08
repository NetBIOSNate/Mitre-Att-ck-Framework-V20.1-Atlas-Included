# T1003.005 - Cached Domain Credentials

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1003 - OS Credential Dumping](../README.md)

Adversaries may attempt to access cached domain credentials used to allow authentication to occur in the event a domain controller is unavailable.(Citation: Microsoft - Cached Creds)

On Windows Vista and newer, the hash format is DCC2 (Domain Cached Credentials version 2) hash, also known as MS-Cache v2 hash.(Citation: PassLib mscache) The number of default cached credentials varies and can be altered per system. This hash does not allow pass-the-hash style attacks, and instead requires [Password Cracking](https://attack.mitre.org/techniques/T1110/002) to recover the plaintext password.(Citation: ired mscache)

On Linux systems, Active Directory credentials can be accessed through caches maintained by software like System Security Services Daemon (SSSD) or Quest Authentication Services (formerly VAS). Cached credential hashes are typically located at `/var/lib/sss/db/cache.[domain].ldb` for SSSD or `/var/opt/quest/vas/authcache/vas_auth.vdb` for Quest. Adversaries can use utilities, such as `tdbdump`, on these database files to dump the cached hashes and use [Password Cracking](https://attack.mitre.org/techniques/T1110/002) to obtain the plaintext password.(Citation: Brining MimiKatz to Unix) 

With SYSTEM or sudo access, the tools/utilities such as [Mimikatz](https://attack.mitre.org/software/S0002), [Reg](https://attack.mitre.org/software/S0075), and secretsdump.py for Windows or Linikatz for Linux can be used to extract the cached credentials.(Citation: Brining MimiKatz to Unix)

Note: Cached credentials for Windows Vista are derived using PBKDF2.(Citation: PassLib mscache)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1003/005)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code to use secretsdump.py against the victims Active Directory to gather credentials.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0064 - APT33](../../../../Threat%20Intelligence/Groups/G0064%20-%20APT33.md) — [APT33](https://attack.mitre.org/groups/G0064) has used a variety of publicly available tools like [LaZagne](https://attack.mitre.org/software/S0349) to gather credentials.(Citation: Symantec Elfin Mar 2019)(Citation: FireEye APT33 Guardrail) [Symantec Elfin Mar 2019](https://www.symantec.com/blogs/threat-intelligence/elfin-apt33-espionage) · [FireEye APT33 Guardrail](https://www.fireeye.com/blog/threat-research/2018/12/overruled-containing-a-potentially-destructive-adversary.html)
- [S0119 - Cachedump](../../../../Threat%20Intelligence/Software/Tools/S0119%20-%20Cachedump.md) — [Cachedump](https://attack.mitre.org/software/S0119) can extract cached password hashes from cache entry information.(Citation: Mandiant APT1) [Mandiant APT1](https://www.fireeye.com/content/dam/fireeye-www/services/pdfs/mandiant-apt1-report.pdf)
- [S0349 - LaZagne](../../../../Threat%20Intelligence/Software/Tools/S0349%20-%20LaZagne.md) — [LaZagne](https://attack.mitre.org/software/S0349) can perform credential dumping from MSCache to obtain account and password information.(Citation: GitHub LaZagne Dec 2018) [GitHub LaZagne Dec 2018](https://github.com/AlessandroZ/LaZagne)
- [G0077 - Leafminer](../../../../Threat%20Intelligence/Groups/G0077%20-%20Leafminer.md) — [Leafminer](https://attack.mitre.org/groups/G0077) used several tools for retrieving login and password information, including LaZagne.(Citation: Symantec Leafminer July 2018) [Symantec Leafminer July 2018](https://www.symantec.com/blogs/threat-intelligence/leafminer-espionage-middle-east)
- [G0069 - MuddyWater](../../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has performed credential dumping with [LaZagne](https://attack.mitre.org/software/S0349).(Citation: Unit 42 MuddyWater Nov 2017)(Citation: Symantec MuddyWater Dec 2018) [Unit 42 MuddyWater Nov 2017](https://researchcenter.paloaltonetworks.com/2017/11/unit42-muddying-the-water-targeted-attacks-in-the-middle-east/) · [Symantec MuddyWater Dec 2018](https://www.symantec.com/blogs/threat-intelligence/seedworm-espionage-group)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has used credential dumping tools such as [LaZagne](https://attack.mitre.org/software/S0349) to steal credentials to accounts logged into the compromised system and to Outlook Web Access.(Citation: Unit42 OilRig Playbook 2023)(Citation: FireEye APT34 Webinar Dec 2017)(Citation: FireEye APT35 2018)(Citation: FireEye APT34 July 2019) [FireEye APT34 July 2019](https://www.fireeye.com/blog/threat-research/2019/07/hard-pass-declining-apt34-invite-to-join-their-professional-network.html) · [FireEye APT34 Webinar Dec 2017](https://www.brighttalk.com/webcast/10703/296317/apt34-new-targeted-attack-in-the-middle-east) · [FireEye APT35 2018](https://static.carahsoft.com/concrete/files/1015/2779/3571/M-Trends-2018-Report.pdf) · [Unit42 OilRig Playbook 2023](https://web.archive.org/web/20230610050742/https://pan-unit42.github.io/playbook_viewer/?pb=evasive-serpens)
- [S0439 - Okrum](../../../../Threat%20Intelligence/Software/Malware/S0439%20-%20Okrum.md) — [Okrum](https://attack.mitre.org/software/S0439) was seen using modified Quarks PwDump to perform credential dumping.(Citation: ESET Okrum July 2019) [ESET Okrum July 2019](https://www.welivesecurity.com/wp-content/uploads/2019/07/ESET_Okrum_and_Ketrican.pdf)
- [S0192 - Pupy](../../../../Threat%20Intelligence/Software/Tools/S0192%20-%20Pupy.md) — [Pupy](https://attack.mitre.org/software/S0192) can use Lazagne for harvesting credentials.(Citation: GitHub Pupy) [GitHub Pupy](https://github.com/n1nj4sec/pupy)

## Detection strategies

- [DET0513 - Detection of Cached Domain Credential Dumping via Local Hash Cache Access](../../../../Defenses/Detection%20Strategies/DET0513%20-%20Detection%20of%20Cached%20Domain%20Credential%20Dumping%20via%20Local%20Hash%20Cache%20Access.md)

## Mitigations

- [M1015 - Active Directory Configuration](../../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — Consider adding users to the "Protected Users" Active Directory security group. This can help limit the caching of users' plaintext credentials.(Citation: Microsoft Protected Users Security Group) [Microsoft Protected Users Security Group](https://docs.microsoft.com/en-us/windows-server/security/credentials-protection-and-management/protected-users-security-group)
- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Consider limiting the number of cached credentials (HKLM\SOFTWARE\Microsoft\Windows NT\Current Version\Winlogon\cachedlogonscountvalue)(Citation: Tilbury Windows Credentials) [Tilbury Windows Credentials](https://www.first.org/resources/papers/conf2017/Windows-Credentials-Attacks-and-Mitigation-Techniques.pdf)
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure that local administrator accounts have complex, unique passwords across all systems on the network.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not put user or admin domain accounts in the local administrator groups across systems unless they are tightly controlled, as this is often equivalent to having a local administrator account with the same password on all systems. Follow best practices for design and administration of an enterprise network to limit privileged account use across administrative tiers.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Limit credential overlap across accounts and systems by training users and administrators not to use the same password for multiple accounts.

## Sources

- [PassLib mscache](https://passlib.readthedocs.io/en/stable/lib/passlib.hash.msdcc2.html)
- [ired mscache](https://ired.team/offensive-security/credential-access-and-credential-dumping/dumping-and-cracking-mscash-cached-domain-credentials)
- [Microsoft - Cached Creds](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh994565%28v%3Dws.11%29)
- [Powersploit](https://github.com/mattifestation/PowerSploit)
- [Brining MimiKatz to Unix](https://labs.portcullis.co.uk/download/eu-18-Wadhwa-Brown-Where-2-worlds-collide-Bringing-Mimikatz-et-al-to-UNIX.pdf)
