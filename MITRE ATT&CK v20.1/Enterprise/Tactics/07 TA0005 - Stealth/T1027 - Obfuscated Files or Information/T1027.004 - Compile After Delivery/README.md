# T1027.004 - Compile After Delivery

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may attempt to make payloads difficult to discover and analyze by delivering files to victims as uncompiled code. Text-based source code files may subvert analysis and scrutiny from protections targeting executables/binaries. These payloads will need to be compiled before execution; typically via native utilities such as ilasm.exe(Citation: ATTACK IQ), csc.exe, or GCC/MinGW.(Citation: ClearSky MuddyWater Nov 2018)

Source code payloads may also be encrypted, encoded, and/or embedded within other files, such as those delivered as a [Phishing](https://attack.mitre.org/techniques/T1566). Payloads may also be delivered in formats unrecognizable and inherently benign to the native OS (ex: EXEs on macOS/Linux) before later being (re)compiled into a proper executable binary with a bundled compiler and execution framework.(Citation: TrendMicro WindowsAppMac)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/004)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0348 - Cardinal RAT](../../../../Threat%20Intelligence/Software/Malware/S0348%20-%20Cardinal%20RAT.md) — [Cardinal RAT](https://attack.mitre.org/software/S0348) and its watchdog component are compiled and executed after being delivered to victims as embedded, uncompiled source code.(Citation: PaloAlto CardinalRat Apr 2017) [PaloAlto CardinalRat Apr 2017](https://researchcenter.paloaltonetworks.com/2017/04/unit42-cardinal-rat-active-two-years/)
- [S0673 - DarkWatchman](../../../../Threat%20Intelligence/Software/Malware/S0673%20-%20DarkWatchman.md) — [DarkWatchman](https://attack.mitre.org/software/S0673) has used the <code>csc.exe</code> tool to compile a C# executable.(Citation: Prevailion DarkWatchman 2021) [Prevailion DarkWatchman 2021](https://web.archive.org/web/20220629230035/https://www.prevailion.com/darkwatchman-new-fileless-techniques/)
- [S0661 - FoggyWeb](../../../../Threat%20Intelligence/Software/Malware/S0661%20-%20FoggyWeb.md) — [FoggyWeb](https://attack.mitre.org/software/S0661) can compile and execute source code sent to the compromised AD FS server via a specific HTTP POST.(Citation: MSTIC FoggyWeb September 2021) [MSTIC FoggyWeb September 2021](https://www.microsoft.com/security/blog/2021/09/27/foggyweb-targeted-nobelium-malware-leads-to-persistent-backdoor/)
- [G0047 - Gamaredon Group](../../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has compiled the source code for a downloader directly on the infected system using the built-in <code>Microsoft.CSharp.CSharpCodeProvider</code> class.(Citation: ESET Gamaredon June 2020) [ESET Gamaredon June 2020](https://www.welivesecurity.com/2020/06/11/gamaredon-group-grows-its-game/)
- [G0069 - MuddyWater](../../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has used the .NET csc.exe tool to compile executables from downloaded C# code.(Citation: ClearSky MuddyWater Nov 2018) [ClearSky MuddyWater Nov 2018](https://www.clearskysec.com/wp-content/uploads/2018/11/MuddyWater-Operations-in-Lebanon-and-Oman.pdf)
- [S0385 - njRAT](../../../../Threat%20Intelligence/Software/Malware/S0385%20-%20njRAT.md) — [njRAT](https://attack.mitre.org/software/S0385) has used AutoIt to compile the payload and main script into a single executable after delivery.(Citation: Trend Micro njRAT 2018) [Trend Micro njRAT 2018](https://blog.trendmicro.com/trendlabs-security-intelligence/autoit-compiled-worm-affecting-removable-media-delivers-fileless-version-of-bladabindi-njrat-backdoor/)
- [G0106 - Rocke](../../../../Threat%20Intelligence/Groups/G0106%20-%20Rocke.md) — [Rocke](https://attack.mitre.org/groups/G0106) has compiled malware, delivered to victims as .c files, with the GNU Compiler Collection (GCC).(Citation: Anomali Rocke March 2019) [Anomali Rocke March 2019](https://www.anomali.com/blog/rocke-evolves-its-arsenal-with-a-new-malware-family-written-in-golang)
- [S1099 - Samurai](../../../../Threat%20Intelligence/Software/Malware/S1099%20-%20Samurai.md) — [Samurai](https://attack.mitre.org/software/S1099) can compile and execute downloaded modules at runtime.(Citation: Kaspersky ToddyCat June 2022) [Kaspersky ToddyCat June 2022](https://securelist.com/toddycat/106799/)
- [G1041 - Sea Turtle](../../../../Threat%20Intelligence/Groups/G1041%20-%20Sea%20Turtle.md) — [Sea Turtle](https://attack.mitre.org/groups/G1041) downloaded source code files from remote addresses then compiled them locally via GCC in victim environments.(Citation: Hunt Sea Turtle 2024) [Hunt Sea Turtle 2024](https://www.huntandhackett.com/blog/turkish-espionage-campaigns)
- [S0633 - Sliver](../../../../Threat%20Intelligence/Software/Tools/S0633%20-%20Sliver.md) — [Sliver](https://attack.mitre.org/software/S0633) includes functionality to retrieve source code and compile locally prior to execution in victim environments.(Citation: Cybereason Sliver Undated) [Cybereason Sliver Undated](https://www.cybereason.com/blog/sliver-c2-leveraged-by-many-threat-actors)

## Detection strategies

- [DET0501 - Detection Strategy for Compile After Delivery - Source Code to Executable Transformation](../../../../Defenses/Detection%20Strategies/DET0501%20-%20Detection%20Strategy%20for%20Compile%20After%20Delivery%20-%20Source%20Code%20to%20Executable%20Transformat.md)

## Sources

- [ClearSky MuddyWater Nov 2018](https://www.clearskysec.com/wp-content/uploads/2018/11/MuddyWater-Operations-in-Lebanon-and-Oman.pdf)
- [ATTACK IQ](https://www.attackiq.com/2023/03/16/hiding-in-plain-sight/)
- [TrendMicro WindowsAppMac](https://blog.trendmicro.com/trendlabs-security-intelligence/windows-app-runs-on-mac-downloads-info-stealer-and-adware/)
