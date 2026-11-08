# T1003.008 - /etc/passwd and /etc/shadow

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1003 - OS Credential Dumping](../README.md)

Adversaries may attempt to dump the contents of <code>/etc/passwd</code> and <code>/etc/shadow</code> to enable offline password cracking. Most modern Linux operating systems use a combination of <code>/etc/passwd</code> and <code>/etc/shadow</code> to store user account information, including password hashes in <code>/etc/shadow</code>. By default, <code>/etc/shadow</code> is only readable by the root user.(Citation: Linux Password and Shadow File Formats)

Linux stores user information such as user ID, group ID, home directory path, and login shell in <code>/etc/passwd</code>. A "user" on the system may belong to a person or a service. All password hashes are stored in <code>/etc/shadow</code> - including entries for users with no passwords and users with locked or disabled accounts.(Citation: Linux Password and Shadow File Formats)

Adversaries may attempt to read or dump the <code>/etc/passwd</code> and <code>/etc/shadow</code> files on Linux systems via command line utilities such as the <code>cat</code> command.(Citation: Arctic Wolf) Additionally, the Linux utility <code>unshadow</code> can be used to combine the two files in a format suited for password cracking utilities such as John the Ripper - for example, via the command <code>/usr/bin/unshadow /etc/passwd /etc/shadow > /tmp/crack.password.db</code>(Citation: nixCraft - John the Ripper). Since the user information stored in <code>/etc/passwd</code> is linked to the password hashes in <code>/etc/shadow</code>, an adversary would need to have access to both.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1003/008)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code with extracting the root password hash from the `/etc/shadow` file within the victim server.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [S0349 - LaZagne](../../../../Threat%20Intelligence/Software/Tools/S0349%20-%20LaZagne.md) — [LaZagne](https://attack.mitre.org/software/S0349) can obtain credential information from /etc/shadow using the shadow.py module.(Citation: GitHub LaZagne Dec 2018) [GitHub LaZagne Dec 2018](https://github.com/AlessandroZ/LaZagne)
- [C0045 - ShadowRay](../../../../Threat%20Intelligence/Campaigns/C0045%20-%20ShadowRay.md) — During [ShadowRay](https://attack.mitre.org/campaigns/C0045), threat actors used `cat /etc/shadow` to steal password hashes.(Citation: Oligo ShadowRay Campaign MAR 2024) [Oligo ShadowRay Campaign MAR 2024](https://www.oligo.security/blog/shadowray-attack-ai-workloads-actively-exploited-in-the-wild)

## Mitigations

- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure that root accounts have complex, unique passwords across all systems on the network.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Follow best practices in restricting access to privileged accounts to avoid hostile programs from accessing such sensitive information.

## Detection strategies

- [DET0446 - Credential Access via /etc/passwd and /etc/shadow Parsing](../../../../Defenses/Detection%20Strategies/DET0446%20-%20Credential%20Access%20via%20-%20etc%20-%20passwd%20and%20-%20etc%20-%20shadow%20Parsing.md)

## Sources

- [Arctic Wolf](https://arcticwolf.com/resources/blog/arctic-wolf-observes-threat-campaign-targeting-palo-alto-networks-firewall-devices/)
- [Linux Password and Shadow File Formats](https://www.tldp.org/LDP/lame/LAME/linux-admin-made-easy/shadow-file-formats.html)
- [nixCraft - John the Ripper](https://www.cyberciti.biz/faq/unix-linux-password-cracking-john-the-ripper/)
