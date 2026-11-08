# T1218.003 - CMSTP

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse CMSTP to proxy execution of malicious code. The Microsoft Connection Manager Profile Installer (CMSTP.exe) is a command-line program used to install Connection Manager service profiles.(Citation: Microsoft Connection Manager Oct 2009) CMSTP.exe accepts an installation information file (INF) as a parameter and installs a service profile leveraged for remote access connections.

Adversaries may supply CMSTP.exe with INF files infected with malicious commands.(Citation: Twitter CMSTP Usage Jan 2018) Similar to [Regsvr32](https://attack.mitre.org/techniques/T1218/010) / ”Squiblydoo”, CMSTP.exe may be abused to load and execute DLLs(Citation: MSitPros CMSTP Aug 2017)  and/or COM scriptlets (SCT) from remote servers.(Citation: Twitter CMSTP Jan 2018)(Citation: GitHub Ultimate AppLocker Bypass List)(Citation: Endurant CMSTP July 2018) This execution may also bypass AppLocker and other application control defenses since CMSTP.exe is a legitimate binary that may be signed by Microsoft.

CMSTP.exe can also be abused to [Bypass User Account Control](https://attack.mitre.org/techniques/T1548/002) and execute arbitrary commands from a malicious INF through an auto-elevated COM interface.(Citation: MSitPros CMSTP Aug 2017)(Citation: GitHub Ultimate AppLocker Bypass List)(Citation: Endurant CMSTP July 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/003)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1149 - CHIMNEYSWEEP](../../../../Threat%20Intelligence/Software/Malware/S1149%20-%20CHIMNEYSWEEP.md) — [CHIMNEYSWEEP](https://attack.mitre.org/software/S1149) can use CMSTP.exe to install a malicious Microsoft Connection Manager Profile.(Citation: Mandiant ROADSWEEP August 2022) [Mandiant ROADSWEEP August 2022](https://cloud.google.com/blog/topics/threat-intelligence/likely-iranian-threat-actor-conducts-politically-motivated-disruptive-activity-against/)
- [G0080 - Cobalt Group](../../../../Threat%20Intelligence/Groups/G0080%20-%20Cobalt%20Group.md) — [Cobalt Group](https://attack.mitre.org/groups/G0080) has used the command <code>cmstp.exe /s /ns C:\Users\ADMINI~W\AppData\Local\Temp\XKNqbpzl.txt</code> to bypass AppLocker and launch a malicious script.(Citation: Talos Cobalt Group July 2018)(Citation: Morphisec Cobalt Gang Oct 2018)(Citation: Unit 42 Cobalt Gang Oct 2018) [Talos Cobalt Group July 2018](https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html) · [Morphisec Cobalt Gang Oct 2018](https://blog.morphisec.com/cobalt-gang-2.0) · [Unit 42 Cobalt Gang Oct 2018](https://researchcenter.paloaltonetworks.com/2018/10/unit42-new-techniques-uncover-attribute-cobalt-gang-commodity-builders-infrastructure-revealed/)
- [S1202 - LockBit 3.0](../../../../Threat%20Intelligence/Software/Malware/S1202%20-%20LockBit%203.0.md) — [LockBit 3.0](https://attack.mitre.org/software/S1202) can attempt a CMSTP UAC bypass if it does not have administrative privileges.(Citation: Sentinel Labs LockBit 3.0 JUL 2022) [Sentinel Labs LockBit 3.0 JUL 2022](https://www.sentinelone.com/labs/lockbit-3-0-update-unpicking-the-ransomwares-latest-anti-analysis-and-evasion-techniques)
- [G0069 - MuddyWater](../../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has used CMSTP.exe and a malicious INF to execute its [POWERSTATS](https://attack.mitre.org/software/S0223) payload.(Citation: FireEye MuddyWater Mar 2018) [FireEye MuddyWater Mar 2018](https://www.fireeye.com/blog/threat-research/2018/03/iranian-threat-group-updates-ttps-in-spear-phishing-campaign.html)

## Detection strategies

- [DET0328 - Detection of Malicious Profile Installation via CMSTP.exe](../../../../Defenses/Detection%20Strategies/DET0328%20-%20Detection%20of%20Malicious%20Profile%20Installation%20via%20CMSTP.exe.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — CMSTP.exe may not be necessary within a given environment (unless using it for VPN connection installation).
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Consider using application control configured to block execution of CMSTP.exe if it is not required for a given system or network to prevent potential misuse by adversaries.

## Sources

- [Twitter CMSTP Usage Jan 2018](https://x.com/ItsReallyNick/status/958789644165894146)
- [Microsoft Connection Manager Oct 2009](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc786431%28v=ws.10%29)
- [MSitPros CMSTP Aug 2017](https://msitpros.com/?p=3960)
- [GitHub Ultimate AppLocker Bypass List](https://github.com/api0cradle/UltimateAppLockerByPassList)
- [Endurant CMSTP July 2018](https://web.archive.org/web/20190316220149/http://www.endurant.io/cmstp/detecting-cmstp-enabled-code-execution-and-uac-bypass-with-sysmon/)
- [Twitter CMSTP Jan 2018](https://x.com/NickTyrer/status/958450014111633408)
