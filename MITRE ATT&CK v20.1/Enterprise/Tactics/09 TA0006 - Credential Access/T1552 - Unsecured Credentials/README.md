# T1552 - Unsecured Credentials

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may search compromised systems to find and obtain insecurely stored credentials. These credentials can be stored and/or misplaced in many locations on a system, including plaintext files (e.g. [Shell History](https://attack.mitre.org/techniques/T1552/003)), operating system or application-specific repositories (e.g. [Credentials in Registry](https://attack.mitre.org/techniques/T1552/002)),  or other specialized files/artifacts (e.g. [Private Keys](https://attack.mitre.org/techniques/T1552/004)).(Citation: Brining MimiKatz to Unix)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1552)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [SaaS](../../../Platforms/SaaS.md), [IaaS](../../../Platforms/IaaS.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Containers](../../../Platforms/Containers.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md)

## Sub-techniques

- [T1552.008 - Chat Messages](T1552.008%20-%20Chat%20Messages/README.md)
- [T1552.005 - Cloud Instance Metadata API](T1552.005%20-%20Cloud%20Instance%20Metadata%20API/README.md)
- [T1552.007 - Container API](T1552.007%20-%20Container%20API/README.md)
- [T1552.001 - Credentials In Files](T1552.001%20-%20Credentials%20In%20Files/README.md)
- [T1552.002 - Credentials in Registry](T1552.002%20-%20Credentials%20in%20Registry/README.md)
- [T1552.006 - Group Policy Preferences](T1552.006%20-%20Group%20Policy%20Preferences/README.md)
- [T1552.004 - Private Keys](T1552.004%20-%20Private%20Keys/README.md)
- [T1552.003 - Shell History](T1552.003%20-%20Shell%20History/README.md)

## Mitigations

- [M1015 - Active Directory Configuration](../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — Remove vulnerable Group Policy Preferences.(Citation: Microsoft MS14-025) [Microsoft MS14-025](http://support.microsoft.com/kb/2962486)
- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Preemptively search for files containing passwords or other credentials and take actions to reduce the exposure risk when found.
- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — When possible, store keys on separate cryptographic hardware instead of on the local system.
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Limit access to the Instance Metadata API. A properly configured Web Application Firewall (WAF) may help prevent external adversaries from exploiting Server-side Request Forgery (SSRF) attacks that allow access to the Cloud Instance Metadata API.(Citation: RedLock Instance Metadata API 2018) [RedLock Instance Metadata API 2018](https://redlock.io/blog/instance-metadata-api-a-modern-day-trojan-horse)
- [M1035 - Limit Access to Resource Over Network](../../../Defenses/Mitigations/M1035%20-%20Limit%20Access%20to%20Resource%20Over%20Network.md) — Limit network access to sensitive services, such as the Instance Metadata API.
- [M1028 - Operating System Configuration](../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — There are multiple methods of preventing a user's command history from being flushed to their .bash_history file, including use of the following commands: <code>set +o history</code> and <code>set -o history</code> to start logging again; <code>unset HISTFILE</code> being added to a user's .bash_rc file; and <code>ln -s /dev/null ~/.bash_history</code> to write commands to <code>/dev/null</code>instead.
- [M1027 - Password Policies](../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Use strong passphrases for private keys to make cracking difficult. Do not store credentials within the Registry. Establish an organizational policy that prohibits password storage in files.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — If it is necessary that software must store credentials in the Registry, then ensure the associated accounts have limited permissions so they cannot be abused if obtained by an adversary.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict file shares to specific directories with access only to necessary users.
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Apply patch KB2962486 which prevents credentials from being stored in GPPs.(Citation: ADSecurity Finding Passwords in SYSVOL)(Citation: MS14-025) [ADSecurity Finding Passwords in SYSVOL](https://adsecurity.org/?p=2288) · [MS14-025](https://support.microsoft.com/en-us/help/2962486/ms14-025-vulnerability-in-group-policy-preferences-could-allow-elevati)
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Ensure that developers and system administrators are aware of the risk associated with having plaintext passwords in software configuration files that may be left on endpoint systems or servers.

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code with attempting to search for credentials through the webshell.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [S0373 - Astaroth](../../../Threat%20Intelligence/Software/Malware/S0373%20-%20Astaroth.md) — [Astaroth](https://attack.mitre.org/software/S0373) uses an external software known as NetPass to recover passwords. (Citation: Cybereason Astaroth Feb 2019) [Cybereason Astaroth Feb 2019](https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research)
- [S1111 - DarkGate](../../../Threat%20Intelligence/Software/Malware/S1111%20-%20DarkGate.md) — [DarkGate](https://attack.mitre.org/software/S1111) uses NirSoft tools to steal user credentials from the infected machine.(Citation: Ensilo Darkgate 2018) NirSoft tools are executed via process hollowing in a newly-created instance of vbc.exe or regasm.exe. [Ensilo Darkgate 2018](https://www.fortinet.com/blog/threat-research/enter-the-darkgate-new-cryptocurrency-mining-and-ransomware-campaign)
- [C0049 - Leviathan Australian Intrusions](../../../Threat%20Intelligence/Campaigns/C0049%20-%20Leviathan%20Australian%20Intrusions.md) — [Leviathan](https://attack.mitre.org/groups/G0065) gathered credentials hardcoded in binaries located on victim devices during [Leviathan Australian Intrusions](https://attack.mitre.org/campaigns/C0049).(Citation: CISA Leviathan 2024) [CISA Leviathan 2024](https://www.cisa.gov/news-events/cybersecurity-advisories/aa24-190a)
- [G1059 - NIMBUS MANTICORE](../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has obtained credentials from internal service ticketing systems.(Citation: Mandiant_UNC1549TTPsTools_Nov2025) [Mandiant_UNC1549TTPsTools_Nov2025](https://cloud.google.com/blog/topics/threat-intelligence/analysis-of-unc1549-ttps-targeting-aerospace-defense)
- [S1131 - NPPSPY](../../../Threat%20Intelligence/Software/Tools/S1131%20-%20NPPSPY.md) — [NPPSPY](https://attack.mitre.org/software/S1131) captures credentials by recording them through an alternative network listener registered to the <code>mpnotify.exe</code> process, allowing for cleartext recording of logon information.(Citation: Huntress NPPSPY 2022) [Huntress NPPSPY 2022](https://www.huntress.com/blog/cleartext-shenanigans-gifting-user-passwords-to-adversaries-with-nppspy)
- [S1091 - Pacu](../../../Threat%20Intelligence/Software/Tools/S1091%20-%20Pacu.md) — [Pacu](https://attack.mitre.org/software/S1091) can search for sensitive data: for example, in Code Build environment variables, EC2 user data, and Cloud Formation templates.(Citation: GitHub Pacu) [GitHub Pacu](https://github.com/RhinoSecurityLabs/pacu)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has obtained credentials insecurely stored on targeted network appliances.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0412 - Detect Access or Search for Unsecured Credentials Across Platforms](../../../Defenses/Detection%20Strategies/DET0412%20-%20Detect%20Access%20or%20Search%20for%20Unsecured%20Credentials%20Across%20Platforms.md)

## Sources

- [Brining MimiKatz to Unix](https://labs.portcullis.co.uk/download/eu-18-Wadhwa-Brown-Where-2-worlds-collide-Bringing-Mimikatz-et-al-to-UNIX.pdf)
