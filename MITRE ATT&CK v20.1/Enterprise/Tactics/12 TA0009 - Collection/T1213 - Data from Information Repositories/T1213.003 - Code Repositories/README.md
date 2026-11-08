# T1213.003 - Code Repositories

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1213 - Data from Information Repositories](../README.md)

Adversaries may leverage code repositories to collect valuable information. Code repositories are tools/services that store source code and automate software builds. They may be hosted internally or privately on third party sites such as Github, GitLab, SourceForge, and BitBucket. Users typically interact with code repositories through a web application or command-line utilities such as git.

Once adversaries gain access to a victim network or a private code repository, they may collect sensitive information such as proprietary source code or [Unsecured Credentials](https://attack.mitre.org/techniques/T1552) contained within software's source code.  Having access to software's source code may allow adversaries to develop [Exploits](https://attack.mitre.org/techniques/T1587/004), while credentials may provide access to additional resources using [Valid Accounts](https://attack.mitre.org/techniques/T1078).(Citation: Wired Uber Breach)(Citation: Krebs Adobe)

**Note:** This is distinct from [Code Repositories](https://attack.mitre.org/techniques/T1593/003), which focuses on conducting [Reconnaissance](https://attack.mitre.org/tactics/TA0043) via public code repositories.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1213/003)

**Tactics**  [Collection](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Consider periodic reviews of accounts and privileges for critical and sensitive code repositories. Scan code repositories for exposed credentials or other sensitive information.
- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Use multi-factor authentication for logons to code repositories.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least-privilege. Consider implementing access control mechanisms that include both authentication and authorization for code repositories.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored in code repositories.

## Procedure examples

- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) cloned victim user Git repositories during intrusions.(Citation: Rostovcev APT41 2021) [Rostovcev APT41 2021](https://www.group-ib.com/blog/apt41-world-tour-2021/)
- [S9010 - GlassWorm](../../../../Threat%20Intelligence/Software/Malware/S9010%20-%20GlassWorm.md) — [GlassWorm](https://attack.mitre.org/software/S9010) has gathered code repository authentication materials for NPM and GitHub.(Citation: Koi Glassworm New Tricks December 2025)(Citation: Koi Glassworm InvisibleCode October 2025)(Citation: Socket GlassWorm January 2026) [GlassWorm](https://attack.mitre.org/software/S9010) has collected details pertaining to the npm configuration data for `_authToken`.(Citation: Koi Glassworm InvisibleCode October 2025)(Citation: Socket GlassWorm January 2026) [Koi Glassworm New Tricks December 2025](https://www.koi.ai/blog/glassworm-goes-mac-fresh-infrastructure-new-tricks) · [Koi Glassworm InvisibleCode October 2025](https://www.koi.ai/blog/glassworm-first-self-propagating-worm-using-invisible-code-hits-openvsx-marketplace) · [Socket GlassWorm January 2026](https://socket.dev/blog/glassworm-loader-hits-open-vsx-via-suspected-developer-account-compromise)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has searched a victim's network for code repositories like GitLab and GitHub to discover further high-privilege account credentials.(Citation: MSTIC DEV-0537 Mar 2022)(Citation: NCC Group LAPSUS Apr 2022) [NCC Group LAPSUS Apr 2022](https://www.nccgroup.com/research-blog/lapsus-recent-techniques-tactics-and-procedures/) · [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has gathered and downloaded data stored on both compromised and publicly accessible code repositories.(Citation: Phoenix TeamPCP 20 MAY 2026) [Phoenix TeamPCP 20 MAY 2026](https://phoenix.security/teampcp-github-breach-durabletask-pypi-supply-chain-wave-four-2026/)
- [G1015 - Scattered Spider](../../../../Threat%20Intelligence/Groups/G1015%20-%20Scattered%20Spider.md) — [Scattered Spider](https://attack.mitre.org/groups/G1015) enumerates data stored within victim code repositories, such as internal GitHub repositories.(Citation: CISA Scattered Spider Advisory November 2023)(Citation: MSTIC Octo Tempest Operations October 2023) [CISA Scattered Spider Advisory November 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-320a) · [MSTIC Octo Tempest Operations October 2023](https://www.microsoft.com/en-us/security/blog/2023/10/25/octo-tempest-crosses-boundaries-to-facilitate-extortion-encryption-and-destruction/)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has downloaded existing packages from code repositories and extracted data stored within them.(Citation: Aikido Shai-Hulud September 2025) [Aikido Shai-Hulud September 2025](https://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has gathered information from and has searched for vulnerabilities in the target company’s GitHub repository source code.(Citation: Intel471_SH_Aug2021) [Intel471_SH_Aug2021](https://www.intel471.com/blog/shinyhunters-data-breach-mitre-attack)
- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) downloaded source code from code repositories.(Citation: Microsoft Internal Solorigate Investigation Blog) [Microsoft Internal Solorigate Investigation Blog](https://msrc-blog.microsoft.com/2021/02/18/microsoft-internal-solorigate-investigation-final-update/)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can target sensitive file paths in Git repos to extract credentials.(Citation: Wiz Trivy Compromise MAR 2026)(Citation: Aqua Security Blog Trivy Compromise APR 2026) [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know) · [Wiz Trivy Compromise MAR 2026](https://www.wiz.io/blog/trivy-compromised-teampcp-supply-chain-attack)
- [S9009 - TruffleHog](../../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) has gathered data and credentials from code repositories.(Citation: Github TruffleSecurity Trufflehog April 2025) [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Detection strategies

- [DET0263 - Detecting Bulk or Anomalous Access to Private Code Repositories via SaaS Platforms](../../../../Defenses/Detection%20Strategies/DET0263%20-%20Detecting%20Bulk%20or%20Anomalous%20Access%20to%20Private%20Code%20Repositories%20via%20SaaS%20Platforms.md)

## Sources

- [Wired Uber Breach](https://www.wired.com/story/uber-paid-off-hackers-to-hide-a-57-million-user-data-breach/)
- [Krebs Adobe](https://krebsonsecurity.com/2013/10/adobe-to-announce-source-code-customer-data-breach/)
