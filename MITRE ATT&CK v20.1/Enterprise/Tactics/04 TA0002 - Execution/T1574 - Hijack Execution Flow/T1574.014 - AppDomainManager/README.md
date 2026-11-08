# T1574.014 - AppDomainManager

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1574 - Hijack Execution Flow](../README.md)

Adversaries may execute their own malicious payloads by hijacking how the .NET `AppDomainManager` loads assemblies. The .NET framework uses the `AppDomainManager` class to create and manage one or more isolated runtime environments (called application domains) inside a process to host the execution of .NET applications. Assemblies (`.exe` or `.dll` binaries compiled to run as .NET code) may be loaded into an application domain as executable code.(Citation: Microsoft App Domains) 

Known as "AppDomainManager injection," adversaries may execute arbitrary code by hijacking how .NET applications load assemblies. For example, malware may create a custom application domain inside a target process to load and execute an arbitrary assembly. Alternatively, configuration files (`.config`) or process environment variables that define .NET runtime settings may be tampered with to instruct otherwise benign .NET applications to load a malicious assembly (identified by name) into the target process.(Citation: PenTestLabs AppDomainManagerInject)(Citation: PwC Yellow Liderc)(Citation: Rapid7 AppDomain Manager Injection)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1574/014)

**Tactics**  [Execution](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0517 - Detection Strategy for Hijack Execution Flow through the AppDomainManager on Windows.](../../../../Defenses/Detection%20Strategies/DET0517%20-%20Detection%20Strategy%20for%20Hijack%20Execution%20Flow%20through%20the%20AppDomainManager%20on%20Windows.md)

## Procedure examples

- [S1152 - IMAPLoader](../../../../Threat%20Intelligence/Software/Malware/S1152%20-%20IMAPLoader.md) — [IMAPLoader](https://attack.mitre.org/software/S1152) is executed via the AppDomainManager injection technique.(Citation: PWC Yellow Liderc 2023) [PWC Yellow Liderc 2023](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/yellow-liderc-ships-its-scripts-delivers-imaploader-malware.html)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has leveraged AppDomain Hijacking facilitated through a trojanized `.config` file.(Citation: CheckPoint_NimbusManticore_May2026) [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/)

## Mitigations

- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Install .NET applications and related software in write-protected locations. Set directory access controls to prevent file writes to the search paths for .NET applications, both in the folders where applications are run from and the standard resources folders.

## Sources

- [PenTestLabs AppDomainManagerInject](https://pentestlaboratories.com/2020/05/26/appdomainmanager-injection-and-detection/)
- [Microsoft App Domains](https://learn.microsoft.com/dotnet/framework/app-domains/application-domains)
- [PwC Yellow Liderc](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/yellow-liderc-ships-its-scripts-delivers-imaploader-malware.html)
- [Rapid7 AppDomain Manager Injection](https://www.rapid7.com/blog/post/2023/05/05/appdomain-manager-injection-new-techniques-for-red-teams/)
