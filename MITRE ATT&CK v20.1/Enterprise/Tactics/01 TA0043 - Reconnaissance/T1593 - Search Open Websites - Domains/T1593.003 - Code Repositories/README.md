# T1593.003 - Code Repositories

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1593 - Search Open Websites/Domains](../README.md)

Adversaries may search public code repositories for information about victims that can be used during targeting. Victims may store code in repositories on various third-party websites such as GitHub, GitLab, SourceForge, and BitBucket. Users typically interact with code repositories through a web application or command-line utilities such as git.  

Adversaries may search various public code repositories for various information about a victim. Public code repositories can often be a source of various general information about victims, such as commonly used programming languages and libraries as well as the names of employees. Adversaries may also identify more sensitive data, including accidentally leaked credentials or API keys.(Citation: GitHub Cloud Service Credentials) Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598)), establishing operational resources (ex: [Compromise Accounts](https://attack.mitre.org/techniques/T1586) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [Valid Accounts](https://attack.mitre.org/techniques/T1078) or [Phishing](https://attack.mitre.org/techniques/T1566)). 

**Note:** This is distinct from [Code Repositories](https://attack.mitre.org/techniques/T1213/003), which focuses on [Collection](https://attack.mitre.org/tactics/TA0009) from private and internally hosted code repositories.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1593/003)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G1052 - Contagious Interview](../../../../Threat%20Intelligence/Groups/G1052%20-%20Contagious%20Interview.md) — [Contagious Interview](https://attack.mitre.org/groups/G1052) had identified and solicited victims through code repositories such as GitHub.(Citation: PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023) [PaloAlto ContagiousInterview BeaverTail InvisibleFerret November 2023](https://unit42.paloaltonetworks.com/two-campaigns-by-north-korea-bad-actors-target-job-hunters/)
- [G0125 - HAFNIUM](../../../../Threat%20Intelligence/Groups/G0125%20-%20HAFNIUM.md) — [HAFNIUM](https://attack.mitre.org/groups/G0125) has discovered leaked corporate credentials on public repositories including GitHub.(Citation: Microsoft Silk Typhoon MAR 2025) [Microsoft Silk Typhoon MAR 2025](https://www.microsoft.com/en-us/security/blog/2025/03/05/silk-typhoon-targeting-it-supply-chain/)
- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has searched public code repositories for exposed credentials.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has the ability to search open sites and code repositories for compromised credentials.(Citation: Aikido Shai-Hulud September 2025)(Citation: Microsoft Shai-Hulud December 2025) [Shai-Hulud](https://attack.mitre.org/software/S9008) has discovered packages associated with compromised accounts.(Citation: Netskope Shai-Hulud November 2025) [Shai-Hulud](https://attack.mitre.org/software/S9008) has also searched code repositories for other compromised repositories that include predefined parameters or markers to include “Second Coming” combined with an 18-character alphanumeric string.(Citation: Netskope Shai-Hulud November 2025) [Aikido Shai-Hulud September 2025](https://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again) · [Netskope Shai-Hulud November 2025](https://www.netskope.com/blog/shai-hulud-2-0-aggressive-automated-one-of-fastest-spreading-npm-supply-chain-attacks-ever-observed) · [Microsoft Shai-Hulud December 2025](https://www.microsoft.com/en-us/security/blog/2025/12/09/shai-hulud-2-0-guidance-for-detecting-investigating-and-defending-against-the-supply-chain-attack/)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has searched through target companies’ GitHub repositories for login credentials or API keys.(Citation: SOCRadar_ShinyHunters_Mar2024) [SOCRadar_ShinyHunters_Mar2024](https://socradar.io/dark-web-profile-shinyhunters/)

## Detection strategies

- [DET0805 - Detection of Code Repositories](../../../../Defenses/Detection%20Strategies/DET0805%20-%20Detection%20of%20Code%20Repositories.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Application developers uploading to public code repositories should be careful to avoid publishing sensitive information such as credentials and API keys.
- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Scan public code repositories for exposed credentials or other sensitive information before making commits. Ensure that any leaked credentials are removed from the commit history, not just the current latest version of the code.

## Sources

- [GitHub Cloud Service Credentials](https://www.forbes.com/sites/runasandvik/2014/01/14/attackers-scrape-github-for-cloud-service-credentials-hijack-account-to-mine-virtual-currency/)
