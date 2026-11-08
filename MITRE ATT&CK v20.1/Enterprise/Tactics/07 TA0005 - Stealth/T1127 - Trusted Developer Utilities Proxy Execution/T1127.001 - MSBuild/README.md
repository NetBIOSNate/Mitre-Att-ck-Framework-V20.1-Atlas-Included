# T1127.001 - MSBuild

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1127 - Trusted Developer Utilities Proxy Execution](../README.md)

Adversaries may use MSBuild to proxy execution of code through a trusted Windows utility. MSBuild.exe (Microsoft Build Engine) is a software build platform used by Visual Studio. It handles XML formatted project files that define requirements for loading and building various platforms and configurations.(Citation: MSDN MSBuild)

Adversaries can abuse MSBuild to proxy execution of malicious code. The inline task capability of MSBuild that was introduced in .NET version 4 allows for C# or Visual Basic code to be inserted into an XML project file.(Citation: MSDN MSBuild)(Citation: Microsoft MSBuild Inline Tasks 2017) MSBuild will compile and execute the inline task. MSBuild.exe is a signed Microsoft binary, so when it is used this way it can execute arbitrary code and bypass application control defenses that are configured to allow MSBuild.exe execution.(Citation: LOLBAS Msbuild)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1127/001)

**Tactics**  [Execution](../../../04%20TA0002%20-%20Execution/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can use built-in modules to abuse trusted utilities like MSBuild.exe.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [C0001 - Frankenstein](../../../../Threat%20Intelligence/Campaigns/C0001%20-%20Frankenstein.md) — During [Frankenstein](https://attack.mitre.org/campaigns/C0001), the threat actors used MSbuild to execute an actor-created file.(Citation: Talos Frankenstein June 2019) [Talos Frankenstein June 2019](https://blog.talosintelligence.com/2019/06/frankenstein-campaign.html)
- [S9025 - NOOPLDR](../../../../Threat%20Intelligence/Software/Malware/S9025%20-%20NOOPLDR.md) — [NOOPLDR](https://attack.mitre.org/software/S9025) can be executed via MSBuild.(Citation: JPCERT MirrorFace JUL 2024) [JPCERT MirrorFace JUL 2024](https://blogs.jpcert.or.jp/en/2024/07/mirrorface-attack-against-japanese-organisations.html)
- [C0060 - Operation AkaiRyū](../../../../Threat%20Intelligence/Campaigns/C0060%20-%20Operation%20AkaiRy%C5%AB.md) — During [Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060), [MirrorFace](https://attack.mitre.org/groups/G1054) used MSBuild to compile and execute its FaceXInjector injection tool.(Citation: ESET MirrorFace 2025) [ESET MirrorFace 2025](https://www.welivesecurity.com/en/eset-research/operation-akairyu-mirrorface-invites-europe-expo-2025-revives-anel-backdoor/)
- [S0013 - PlugX](../../../../Threat%20Intelligence/Software/Malware/S0013%20-%20PlugX.md) — A version of [PlugX](https://attack.mitre.org/software/S0013) loads as shellcode within a .NET Framework project using msbuild.exe, presumably to bypass application control techniques.(Citation: Palo Alto PlugX June 2017) [Palo Alto PlugX June 2017](https://researchcenter.paloaltonetworks.com/2017/06/unit42-paranoid-plugx/)

## Detection strategies

- [DET0556 - Behavior-chain detection strategy for T1127.001 Trusted Developer Utilities Proxy Execution: MSBuild (Windows)](../../../../Defenses/Detection%20Strategies/DET0556%20-%20Behavior-chain%20detection%20strategy%20for%20T1127.001%20Trusted%20Developer%20Utilities%20Proxy%20Exe.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — MSBuild.exe may not be necessary within an environment and should be removed if not being used.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control configured to block execution of <code>msbuild.exe</code> if it is not required for a given system or network to prevent potential misuse by adversaries. For example, in Windows 10 and Windows Server 2016 and above, Windows Defender Application Control (WDAC) policy rules may be applied to block the <code>msbuild.exe</code> application and to prevent abuse.(Citation: Microsoft WDAC) [Microsoft WDAC](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/microsoft-recommended-block-rules)

## Sources

- [LOLBAS Msbuild](https://lolbas-project.github.io/lolbas/Binaries/Msbuild/)
- [Microsoft MSBuild Inline Tasks 2017](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild-inline-tasks?view=vs-2019#code-element)
- [MSDN MSBuild](https://msdn.microsoft.com/library/dd393574.aspx)
