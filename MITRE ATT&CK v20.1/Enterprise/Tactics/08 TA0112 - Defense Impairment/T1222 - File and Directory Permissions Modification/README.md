# T1222 - File and Directory Permissions Modification

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may modify file or directory permissions/attributes to evade access control lists (ACLs) and access protected files.(Citation: Hybrid Analysis Icacls1 June 2018)(Citation: Hybrid Analysis Icacls2 May 2018) File and directory permissions are commonly managed by ACLs configured by the file or directory owner, or users with the appropriate permissions. File and directory ACL implementations vary by platform, but generally explicitly designate which users or groups can perform which actions (read, write, execute, etc.).

Modifications may include changing specific access rights, which may require taking ownership of a file or directory and/or elevated permissions depending on the file or directory’s existing permissions. This may enable malicious activity such as modifying, replacing, or deleting specific files or directories. Specific file and directory modifications may be a required step for many techniques, such as establishing Persistence via [Accessibility Features](https://attack.mitre.org/techniques/T1546/008), [Boot or Logon Initialization Scripts](https://attack.mitre.org/techniques/T1037), [Unix Shell Configuration Modification](https://attack.mitre.org/techniques/T1546/004), or tainting/hijacking other instrumental binary/configuration files via [Hijack Execution Flow](https://attack.mitre.org/techniques/T1574).

Adversaries may also change permissions of symbolic links. For example, malware (particularly ransomware) may modify symbolic links and associated settings to enable access to files from local shortcuts with remote paths.(Citation: new_rust_based_ransomware)(Citation: bad_luck_blackcat)(Citation: falconoverwatch_blackcat_attack)(Citation: blackmatter_blackcat)(Citation: fsutil_behavior)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1222)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [ESXi](../../../Platforms/ESXi.md), [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1222.002 - Linux and Mac Permissions](T1222.002%20-%20Linux%20and%20Mac%20Permissions/README.md)
- [T1222.001 - Windows Permissions](T1222.001%20-%20Windows%20Permissions/README.md)

## Detection strategies

- [DET0299 - Multi-Platform File and Directory Permissions Modification Detection Strategy](../../../Defenses/Detection%20Strategies/DET0299%20-%20Multi-Platform%20File%20and%20Directory%20Permissions%20Modification%20Detection%20Strategy.md)

## Mitigations

- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Ensure critical system files as well as those known to be abused by adversaries have restrictive permissions and are owned by an appropriately privileged account, especially if access is not required by users nor will inhibit system functionality.
- [M1022 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Applying more restrictive permissions to files and directories could prevent adversaries from modifying their access control lists. Additionally, ensure that user settings regarding local and remote symbolic links are properly set or disabled where unneeded.(Citation: create_sym_links) [create_sym_links](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/create-symbolic-links)

## Procedure examples

- [S1242 - Qilin](../../../Threat%20Intelligence/Software/Malware/S1242%20-%20Qilin.md) — [Qilin](https://attack.mitre.org/software/S1242) can use symbolic links to redirect file paths for remote and local objects and can use `chmod +x` to make its payload binary executable.(Citation: Picus Qilin MAR 2025)(Citation: Cisco Talos Qilin Ransomware OCT 2025) [Picus Qilin MAR 2025](https://www.picussecurity.com/resource/blog/qilin-ransomware) · [Cisco Talos Qilin Ransomware OCT 2025](https://blog.talosintelligence.com/uncovering-qilin-attack-methods-exposed-through-multiple-cases/)

## Sources

- [falconoverwatch_blackcat_attack](https://www.crowdstrike.com/blog/falcon-overwatch-contributes-to-blackcat-protection/)
- [Hybrid Analysis Icacls1 June 2018](https://www.hybrid-analysis.com/sample/ef0d2628823e8e0a0de3b08b8eacaf41cf284c086a948bdfd67f4e4373c14e4d?environmentId=100)
- [Hybrid Analysis Icacls2 May 2018](https://www.hybrid-analysis.com/sample/22dab012c3e20e3d9291bce14a2bfc448036d3b966c6e78167f4626f5f9e38d6?environmentId=110)
- [bad_luck_blackcat](https://go.kaspersky.com/rs/802-IJN-240/images/TR_BlackCat_Report.pdf)
- [fsutil_behavior](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/fsutil-behavior)
- [blackmatter_blackcat](https://blog.talosintelligence.com/2022/03/from-blackmatter-to-blackcat-analyzing.html)
- [new_rust_based_ransomware](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/noberus-blackcat-alphv-rust-ransomware)
