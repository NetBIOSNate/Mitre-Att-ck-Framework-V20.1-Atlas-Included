# T1555.005 - Password Managers

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1555 - Credentials from Password Stores](../README.md)

Adversaries may acquire user credentials from third-party password managers.(Citation: ise Password Manager February 2019) Password managers are applications designed to store user credentials, normally in an encrypted database. Credentials are typically accessible after a user provides a master password that unlocks the database. After the database is unlocked, these credentials may be copied to memory. These databases can be stored as files on disk.(Citation: ise Password Manager February 2019)

Adversaries may acquire user credentials from password managers by extracting the master password and/or plain-text credentials from memory.(Citation: FoxIT Wocao December 2019)(Citation: Github KeeThief) Adversaries may extract credentials from memory via [Exploitation for Credential Access](https://attack.mitre.org/techniques/T1212).(Citation: NVD CVE-2019-3610)
 Adversaries may also try brute forcing via [Password Guessing](https://attack.mitre.org/techniques/T1110/001) to obtain the master password of a password manager.(Citation: Cyberreason Anchor December 2019)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1555/005)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0117 - Fox Kitten](../../../../Threat%20Intelligence/Groups/G0117%20-%20Fox%20Kitten.md) — [Fox Kitten](https://attack.mitre.org/groups/G0117) has used scripts to access credential information from the KeePass database.(Citation: CISA AA20-259A Iran-Based Actor September 2020) [CISA AA20-259A Iran-Based Actor September 2020](https://us-cert.cisa.gov/ncas/alerts/aa20-259a)
- [G0119 - Indrik Spider](../../../../Threat%20Intelligence/Groups/G0119%20-%20Indrik%20Spider.md) — [Indrik Spider](https://attack.mitre.org/groups/G0119) has accessed and exported passwords from password managers.(Citation: Mandiant_UNC2165) [Mandiant_UNC2165](https://cloud.google.com/blog/topics/threat-intelligence/unc2165-shifts-to-evade-sanctions/)
- [S1245 - InvisibleFerret](../../../../Threat%20Intelligence/Software/Malware/S1245%20-%20InvisibleFerret.md) — [InvisibleFerret](https://attack.mitre.org/software/S1245) has utilized the command `ssh_zcp` to exfiltrate data from browser extensions and password managers via Telegram and FTP.(Citation: ESET Contagious Interview BeaverTail InvisibleFerret February 2025)(Citation: Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024) [ESET Contagious Interview BeaverTail InvisibleFerret February 2025](https://www.welivesecurity.com/en/eset-research/deceptivedevelopment-targets-freelance-developers/) · [Zscaler ContagiousInterview BeaverTail InvisibleFerret November 2024](https://www.zscaler.com/blogs/security-research/pyongyang-your-payroll-rise-north-korean-remote-workers-west)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has accessed local password managers and databases to obtain further credentials from a compromised network.(Citation: NCC Group LAPSUS Apr 2022) [NCC Group LAPSUS Apr 2022](https://www.nccgroup.com/research-blog/lapsus-recent-techniques-tactics-and-procedures/)
- [S0652 - MarkiRAT](../../../../Threat%20Intelligence/Software/Malware/S0652%20-%20MarkiRAT.md) — [MarkiRAT](https://attack.mitre.org/software/S0652) can gather information from the Keepass password manager.(Citation: Kaspersky Ferocious Kitten Jun 2021) [Kaspersky Ferocious Kitten Jun 2021](https://securelist.com/ferocious-kitten-6-years-of-covert-surveillance-in-iran/102806/)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has gathered credentials stored in password managers to include password vaults.(Citation: Wiz Mini Shai-Hulud MAY 2026)(Citation: Hunt.io TeamPCP Toolkit MAY 2026)(Citation: Phoenix TeamPCP 20 MAY 2026) [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown) · [Wiz Mini Shai-Hulud MAY 2026](https://www.wiz.io/blog/mini-shai-hulud-strikes-again-tanstack-more-npm-packages-compromised) · [Phoenix TeamPCP 20 MAY 2026](https://phoenix.security/teampcp-github-breach-durabletask-pypi-supply-chain-wave-four-2026/)
- [C0014 - Operation Wocao](../../../../Threat%20Intelligence/Campaigns/C0014%20-%20Operation%20Wocao.md) — During [Operation Wocao](https://attack.mitre.org/campaigns/C0014), threat actors accessed and collected credentials from password managers.(Citation: FoxIT Wocao December 2019) [FoxIT Wocao December 2019](https://www.fox-it.com/media/kadlze5c/201912_report_operation_wocao.pdf)
- [S0279 - Proton](../../../../Threat%20Intelligence/Software/Malware/S0279%20-%20Proton.md) — [Proton](https://attack.mitre.org/software/S0279) gathers credentials in files for 1password.(Citation: objsee mac malware 2017) [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) has searched for credentials in password vaults and Privileged Access Management (PAM) solutions including HashiCorp Vault.(Citation: Mandiant UNC3944 May 2025)(Citation: Mandiant VMware vSphere JUL 2025) [Mandiant VMware vSphere JUL 2025](https://cloud.google.com/blog/topics/threat-intelligence/defending-vsphere-from-unc3944) · [Mandiant UNC3944 May 2025](https://cloud.google.com/blog/topics/threat-intelligence/unc3944-proactive-hardening-recommendations)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has stolen credentials contained in the password manager Keepass by utilizing Find-KeePassConfig.ps1.(Citation: Microsoft Storm-501 Sabbath Ransomware Embargo September 2024) [Microsoft Storm-501 Sabbath Ransomware Embargo September 2024](https://www.microsoft.com/en-us/security/blog/2024/09/26/storm-0501-ransomware-attacks-expanding-to-hybrid-cloud-environments/)
- [G0027 - Threat Group-3390](../../../../Threat%20Intelligence/Groups/G0027%20-%20Threat%20Group-3390.md) — [Threat Group-3390](https://attack.mitre.org/groups/G0027) obtained a KeePass database from a compromised host.(Citation: Trend Micro DRBControl February 2020) [Trend Micro DRBControl February 2020](https://documents.trendmicro.com/assets/white_papers/wp-uncovering-DRBcontrol.pdf)
- [S0266 - TrickBot](../../../../Threat%20Intelligence/Software/Malware/S0266%20-%20TrickBot.md) — [TrickBot](https://attack.mitre.org/software/S0266) can steal passwords from the KeePass open source password manager.(Citation: Cyberreason Anchor December 2019) [Cyberreason Anchor December 2019](https://www.cybereason.com/blog/dropping-anchor-from-a-trickbot-infection-to-the-discovery-of-the-anchor-malware)
- [G1048 - UNC3886](../../../../Threat%20Intelligence/Groups/G1048%20-%20UNC3886.md) — [UNC3886](https://attack.mitre.org/groups/G1048) has targeted KeyPass password database files for credential access.(Citation: Google Cloud Threat Intelligence ESXi VIBs 2022) [Google Cloud Threat Intelligence ESXi VIBs 2022](https://cloud.google.com/blog/topics/threat-intelligence/esxi-hypervisors-malware-persistence)

## Mitigations

- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Refer to NIST guidelines when creating password policies for master passwords.(Citation: NIST 800-63-3) [NIST 800-63-3](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-4.pdf)
- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Consider re-locking password managers after a short timeout to limit the time plaintext credentials live in memory from decrypted databases.
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Regularly update web browsers, password managers, and all related software to the latest versions. Keeping software up-to-date reduces the risk of vulnerabilities being exploited by attackers to extract stored credentials or session cookies.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Implement strict user account management policies to prevent unnecessary accounts from accessing sensitive systems. Regularly audit user accounts to identify and disable inactive accounts that may be targeted by attackers to extract credentials or gain unauthorized access.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Provide user training on secure practices for managing credentials, including avoiding storing sensitive passwords in browsers and using password managers securely. Users should also be educated on identifying phishing attempts that could steal session cookies or credentials.

## Detection strategies

- [DET0597 - Detect Unauthorized Access to Password Managers](../../../../Defenses/Detection%20Strategies/DET0597%20-%20Detect%20Unauthorized%20Access%20to%20Password%20Managers.md)

## Sources

- [Cyberreason Anchor December 2019](https://www.cybereason.com/blog/dropping-anchor-from-a-trickbot-infection-to-the-discovery-of-the-anchor-malware)
- [FoxIT Wocao December 2019](https://www.fox-it.com/media/kadlze5c/201912_report_operation_wocao.pdf)
- [ise Password Manager February 2019](https://www.ise.io/casestudies/password-manager-hacking/)
- [Github KeeThief](https://github.com/GhostPack/KeeThief)
- [NVD CVE-2019-3610](https://nvd.nist.gov/vuln/detail/CVE-2019-3610)
