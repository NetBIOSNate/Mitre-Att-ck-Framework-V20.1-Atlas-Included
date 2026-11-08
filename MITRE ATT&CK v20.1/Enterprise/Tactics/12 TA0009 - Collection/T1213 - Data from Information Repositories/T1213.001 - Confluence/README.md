# T1213.001 - Confluence

[Enterprise](../../../../README.md) / [Collection](../../README.md) / [T1213 - Data from Information Repositories](../README.md)

Adversaries may leverage Confluence repositories to mine valuable information.(Citation: Confluence Standards in Data Engineering) Often found in development environments alongside Atlassian JIRA, Confluence is generally used to store development-related documentation; however, it may contain more diverse categories of useful information, such as:

* Policies, procedures, and standards
* Physical / logical network diagrams
* System architecture diagrams
* Technical system documentation
* Testing / development credentials (i.e., [Unsecured Credentials](https://attack.mitre.org/techniques/T1552))
* Work / project schedules
* Source code snippets
* Links to network shares and other internal resources

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1213/001)

**Tactics**  [Collection](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Procedure examples

- [G1004 - LAPSUS$](../../../../Threat%20Intelligence/Groups/G1004%20-%20LAPSUS%24.md) — [LAPSUS$](https://attack.mitre.org/groups/G1004) has searched a victim's network for collaboration platforms like Confluence and JIRA to discover further high-privilege account credentials.(Citation: MSTIC DEV-0537 Mar 2022) [MSTIC DEV-0537 Mar 2022](https://www.microsoft.com/security/blog/2022/03/22/dev-0537-criminal-actor-targeting-organizations-for-data-exfiltration-and-destruction/)
- [S9009 - TruffleHog](../../../../Threat%20Intelligence/Software/Tools/S9009%20-%20TruffleHog.md) — [TruffleHog](https://attack.mitre.org/software/S9009) has collected credentials and data associated with Confluence.(Citation: Github TruffleSecurity Trufflehog April 2025) [Github TruffleSecurity Trufflehog April 2025](https://github.com/trufflesecurity/trufflehog)

## Detection strategies

- [DET0358 - Programmatic and Excessive Access to Confluence Documentation](../../../../Defenses/Detection%20Strategies/DET0358%20-%20Programmatic%20and%20Excessive%20Access%20to%20Confluence%20Documentation.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Consider periodic review of accounts and privileges for critical and sensitive Confluence repositories.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least-privilege. Consider implementing access control mechanisms that include both authentication and authorization.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Develop and publish policies that define acceptable information to be stored in Confluence repositories.

## Sources

- [Confluence Standards in Data Engineering](https://medium.com/data-engineering-technical-standards-and-best/confluence-standards-in-data-engineering-b5dee98eac83)
