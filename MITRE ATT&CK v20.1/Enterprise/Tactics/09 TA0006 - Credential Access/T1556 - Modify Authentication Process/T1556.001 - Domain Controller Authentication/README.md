# T1556.001 - Domain Controller Authentication

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may patch the authentication process on a domain controller to bypass the typical authentication mechanisms and enable access to accounts. 

Malware may be used to inject false credentials into the authentication process on a domain controller with the intent of creating a backdoor used to access any user’s account and/or credentials (ex: [Skeleton Key](https://attack.mitre.org/software/S0007)). Skeleton key works through a patch on an enterprise domain controller authentication process (LSASS) with credentials that adversaries may use to bypass the standard authentication system. Once patched, an adversary can use the injected password to successfully authenticate as any domain user account (until the skeleton key is erased from memory by a reboot of the domain controller). Authenticated access may enable unfettered access to hosts and/or resources within single-factor authentication environments.(Citation: Dell Skeleton)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/001)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md), [Credential Access](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0114 - Chimera](../../../../Threat%20Intelligence/Groups/G0114%20-%20Chimera.md) — [Chimera](https://attack.mitre.org/groups/G0114)'s malware has altered the NTLM authentication program on domain controllers to allow [Chimera](https://attack.mitre.org/groups/G0114) to login without a valid credential.(Citation: Cycraft Chimera April 2020) [Cycraft Chimera April 2020](https://web.archive.org/web/20231214094657/https://cycraft.com/download/CyCraft-Whitepaper-Chimera_V4.1.pdf)
- [S0007 - Skeleton Key](../../../../Threat%20Intelligence/Software/Malware/S0007%20-%20Skeleton%20Key.md) — [Skeleton Key](https://attack.mitre.org/software/S0007) is used to patch an enterprise domain controller authentication process with a backdoor password. It allows adversaries to bypass the standard authentication system to use a defined password for all accounts authenticating to that domain controller.(Citation: Dell Skeleton) [Dell Skeleton](https://www.secureworks.com/research/skeleton-key-malware-analysis)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Integrating multi-factor authentication (MFA) as part of organizational policy can greatly reduce the risk of an adversary gaining control of valid credentials that may be used for additional tactics such as initial access, lateral movement, and collecting information. MFA can also be used to restrict access to cloud resources and APIs.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Audit domain and local accounts as well as their permission levels routinely to look for situations that could allow an adversary to gain wide access by obtaining credentials of a privileged account. (Citation: TechNet Credential Theft) (Citation: TechNet Least Privilege) These audits should also include if default accounts have been enabled, or if new local accounts are created that have not be authorized. Follow best practices for design and administration of an enterprise network to limit privileged account use across administrative tiers. (Citation: Microsoft Securing Privileged Access) [TechNet Credential Theft](https://technet.microsoft.com/en-us/library/dn535501.aspx) · [TechNet Least Privilege](https://technet.microsoft.com/en-us/library/dn487450.aspx) · [Microsoft Securing Privileged Access](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach)
- [M1025 - Privileged Process Integrity](../../../../Defenses/Mitigations/M1025%20-%20Privileged%20Process%20Integrity.md) — Enabled features, such as Protected Process Light (PPL), for LSA.(Citation: Microsoft LSA) [Microsoft LSA](https://technet.microsoft.com/en-us/library/dn408187.aspx)
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to recognize and handle suspicious email attachments. Emphasize the importance of caution when opening attachments from unknown or unexpected sources, even if they appear legitimate. Implement email warning banners to alert users about emails originating from outside the organization or containing attachments, reinforcing awareness and helping users identify potential spearphishing attempts.

## Detection strategies

- [DET0271 - Detect Domain Controller Authentication Process Modification (Skeleton Key)](../../../../Defenses/Detection%20Strategies/DET0271%20-%20Detect%20Domain%20Controller%20Authentication%20Process%20Modification%20%28Skeleton%20Key%29.md)

## Sources

- [Dell Skeleton](https://www.secureworks.com/research/skeleton-key-malware-analysis)
