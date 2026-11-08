# T1505 - Server Software Component

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may abuse legitimate extensible development features of servers to establish persistent access to systems. Enterprise server applications may include features that allow developers to write and install software or scripts to extend the functionality of the main application. Adversaries may install malicious components to extend and abuse server applications.(Citation: volexity_0day_sophos_FW)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1505)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Network Devices](../../../Platforms/Network%20Devices.md), [ESXi](../../../Platforms/ESXi.md)

## Sub-techniques

- [T1505.004 - IIS Components](T1505.004%20-%20IIS%20Components/README.md)
- [T1505.001 - SQL Stored Procedures](T1505.001%20-%20SQL%20Stored%20Procedures/README.md)
- [T1505.005 - Terminal Services DLL](T1505.005%20-%20Terminal%20Services%20DLL/README.md)
- [T1505.002 - Transport Agent](T1505.002%20-%20Transport%20Agent/README.md)
- [T1505.006 - vSphere Installation Bundles](T1505.006%20-%20vSphere%20Installation%20Bundles/README.md)
- [T1505.003 - Web Shell](T1505.003%20-%20Web%20Shell/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Regularly check component software on critical services that adversaries may target for persistence to verify the integrity of the systems and identify if unexpected changes have been made.
- [M1046 - Boot Integrity](../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Enabling secure boot allows validation of software and drivers during initial system boot.
- [M1045 - Code Signing](../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Ensure all application component binaries are signed by the correct application developers.
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider disabling software components from servers when possible to prevent abuse by adversaries.(Citation: ITSyndicate Disabling PHP functions) [ITSyndicate Disabling PHP functions](https://itsyndicate.org/blog/disabling-dangerous-php-functions/)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Do not allow administrator accounts that have permissions to add component software on these services to be used for day-to-day operations that may expose them to potential adversaries on unprivileged systems.
- [M1024 - Restrict Registry Permissions](../../../Defenses/Mitigations/M1024%20-%20Restrict%20Registry%20Permissions.md) — Consider using Group Policy to configure and block modifications to service and other critical server parameters in the Registry.(Citation: Microsoft System Services Fundamentals) [Microsoft System Services Fundamentals](https://social.technet.microsoft.com/wiki/contents/articles/12229.windows-system-services-fundamentals.aspx)
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Enforce the principle of least privilege by limiting privileges of user accounts so only authorized accounts can modify and/or add server software components.(Citation: NSA and ASD Detect and Prevent Web Shells 2020) [NSA and ASD Detect and Prevent Web Shells 2020](https://media.defense.gov/2020/Jun/09/2002313081/-1/-1/0/CSI-DETECT-AND-PREVENT-WEB-SHELL-MALWARE-20200422.PDF)

## Detection strategies

- [DET0547 - Detection Strategy for T1505 - Server Software Component](../../../Defenses/Detection%20Strategies/DET0547%20-%20Detection%20Strategy%20for%20T1505%20-%20Server%20Software%20Component.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary had Claude Code discover and utilize pre-established stored procedures to query the victim database.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)

## Sources

- [volexity_0day_sophos_FW](https://www.volexity.com/blog/2022/06/15/driftingcloud-zero-day-sophos-firewall-exploitation-and-an-insidious-breach/)
- [US-CERT Alert TA15-314A Web Shells](https://www.us-cert.gov/ncas/alerts/TA15-314A)
