# T1556.002 - Password Filter DLL

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may register malicious password filter dynamic link libraries (DLLs) into the authentication process to acquire user credentials as they are validated. 

Windows password filters are password policy enforcement mechanisms for both domain and local accounts. Filters are implemented as DLLs containing a method to validate potential passwords against password policies. Filter DLLs can be positioned on local computers for local accounts and/or domain controllers for domain accounts. Before registering new passwords in the Security Accounts Manager (SAM), the Local Security Authority (LSA) requests validation from each registered filter. Any potential changes cannot take effect until every registered filter acknowledges validation. 

Adversaries can register malicious password filters to harvest credentials from local computers and/or entire domains. To perform proper validation, filters must receive plain-text credentials from the LSA. A malicious password filter would receive these plain-text credentials every time a password request is made.(Citation: Carnal Ownage Password Filters Sept 2013)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/002)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Defense Impairment](../../README.md), [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1054 - MirrorFace](../../../../Threat%20Intelligence/Groups/G1054%20-%20MirrorFace.md) — [MirrorFace](https://attack.mitre.org/groups/G1054) has used a tool named MRSAStealer as a password filter to collect credentials on password changes.(Citation: ESET MirrorFace DEC 2022) [ESET MirrorFace DEC 2022](https://www.welivesecurity.com/2022/12/14/unmasking-mirrorface-operation-liberalface-targeting-japanese-political-entities/)
- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has registered a password filter DLL in order to drop malware.(Citation: Trend Micro Earth Simnavaz October 2024) [Trend Micro Earth Simnavaz October 2024](https://www.trendmicro.com/en_us/research/24/j/earth-simnavaz-cyberattacks.html)
- [S0125 - Remsec](../../../../Threat%20Intelligence/Software/Malware/S0125%20-%20Remsec.md) — [Remsec](https://attack.mitre.org/software/S0125) harvests plain-text credentials as a password filter registered on domain controllers.(Citation: Kaspersky ProjectSauron Full Report) [Kaspersky ProjectSauron Full Report](https://securelist.com/files/2016/07/The-ProjectSauron-APT_research_KL.pdf)
- [G0041 - Strider](../../../../Threat%20Intelligence/Groups/G0041%20-%20Strider.md) — [Strider](https://attack.mitre.org/groups/G0041) has registered its persistence module on domain controllers as a Windows LSA (Local System Authority) password filter to acquire credentials any time a domain, local user, or administrator logs in or changes a password.(Citation: Kaspersky ProjectSauron Full Report) [Kaspersky ProjectSauron Full Report](https://securelist.com/files/2016/07/The-ProjectSauron-APT_research_KL.pdf)

## Mitigations

- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Ensure only valid password filters are registered. Filter DLLs must be present in Windows installation directory (C:\Windows\System32\ by default) of a domain controller and/or local computer with a corresponding entry in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\Notification Packages.

## Detection strategies

- [DET0472 - Detect Malicious Password Filter DLL Registration](../../../../Defenses/Detection%20Strategies/DET0472%20-%20Detect%20Malicious%20Password%20Filter%20DLL%20Registration.md)

## Sources

- [Carnal Ownage Password Filters Sept 2013](http://carnal0wnage.attackresearch.com/2013/09/stealing-passwords-every-time-they.html)
