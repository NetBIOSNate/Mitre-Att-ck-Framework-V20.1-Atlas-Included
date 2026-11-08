# T1110.002 - Password Cracking

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1110 - Brute Force](../README.md)

Adversaries may use password cracking to attempt to recover usable credentials, such as plaintext passwords, when credential material such as password hashes are obtained. [OS Credential Dumping](https://attack.mitre.org/techniques/T1003) can be used to obtain password hashes, this may only get an adversary so far when [Pass the Hash](https://attack.mitre.org/techniques/T1550/002) is not an option. Further,  adversaries may leverage [Data from Configuration Repository](https://attack.mitre.org/techniques/T1602) in order to obtain hashed credentials for network devices.(Citation: US-CERT-TA18-106A) 

Techniques to systematically guess the passwords used to compute hashes are available, or the adversary may use a pre-computed rainbow table to crack hashes. Cracking hashes is usually done on adversary-controlled systems outside of the target network.(Citation: Wikipedia Password cracking) The resulting plaintext password resulting from a successfully cracked hash may be used to log into systems, resources, and services to which the account has access.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1110/002)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries attempted to crack user passwords.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code with cracking database password hashes of the victim organizations.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [G0022 - APT3](../../../../Threat%20Intelligence/Groups/G0022%20-%20APT3.md) — [APT3](https://attack.mitre.org/groups/G0022) has been known to brute force password hashes to be able to leverage plain text credentials.(Citation: APT3 Adversary Emulation Plan) [APT3 Adversary Emulation Plan](https://attack.mitre.org/docs/APT3_Adversary_Emulation_Plan.pdf)
- [G0035 - Dragonfly](../../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has dropped and executed tools used for password cracking, including Hydra and [CrackMapExec](https://attack.mitre.org/software/S0488).(Citation: US-CERT TA18-074A)(Citation: Kali Hydra) [US-CERT TA18-074A](https://www.us-cert.gov/ncas/alerts/TA18-074A) · [Kali Hydra](https://tools.kali.org/password-attacks/hydra)
- [G0037 - FIN6](../../../../Threat%20Intelligence/Groups/G0037%20-%20FIN6.md) — [FIN6](https://attack.mitre.org/groups/G0037) has extracted password hashes from ntds.dit to crack offline.(Citation: FireEye FIN6 April 2016) [FireEye FIN6 April 2016](https://web.archive.org/web/20190807112824/https://www2.fireeye.com/rs/848-DID-242/images/rpt-fin6.pdf)
- [S0056 - Net Crawler](../../../../Threat%20Intelligence/Software/Malware/S0056%20-%20Net%20Crawler.md) — [Net Crawler](https://attack.mitre.org/software/S0056) uses a list of known credentials gathered through credential dumping to guess passwords to accounts as it spreads throughout a network.(Citation: Cylance Cleaver) [Cylance Cleaver](https://web.archive.org/web/20200302085133/https://www.cylance.com/content/dam/cylance/pages/operation-cleaver/Cylance_Operation_Cleaver_Report.pdf)
- [C0002 - Night Dragon](../../../../Threat%20Intelligence/Campaigns/C0002%20-%20Night%20Dragon.md) — During [Night Dragon](https://attack.mitre.org/campaigns/C0002), threat actors used Cain & Abel to crack password hashes.(Citation: McAfee Night Dragon) [McAfee Night Dragon](https://scadahacker.com/library/Documents/Cyber_Events/McAfee%20-%20Night%20Dragon%20-%20Global%20Energy%20Cyberattacks.pdf)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has cracked passwords for accounts with weak encryption obtained from the configuration files of compromised network devices.(Citation: Cisco Salt Typhoon FEB 2025) [Salt Typhoon](https://attack.mitre.org/groups/G1045) has cracked weak hashed passwords stolen from configuration files.(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a) · [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)

## Detection strategies

- [DET0105 - Post-Credential Dump Password Cracking Detection via Suspicious File Access and Hash Analysis Tools](../../../../Defenses/Detection%20Strategies/DET0105%20-%20Post-Credential%20Dump%20Password%20Cracking%20Detection%20via%20Suspicious%20File%20Access%20and%20Hash.md)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication. Where possible, also enable multi-factor authentication on externally facing services.
- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies. (Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)

## Sources

- [US-CERT-TA18-106A](https://www.us-cert.gov/ncas/alerts/TA18-106A)
- [Wikipedia Password cracking](https://en.wikipedia.org/wiki/Password_cracking)
