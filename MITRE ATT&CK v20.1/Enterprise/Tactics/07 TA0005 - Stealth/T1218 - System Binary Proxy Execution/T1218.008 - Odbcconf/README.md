# T1218.008 - Odbcconf

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse odbcconf.exe to proxy execution of malicious payloads. Odbcconf.exe is a Windows utility that allows you to configure Open Database Connectivity (ODBC) drivers and data source names.(Citation: Microsoft odbcconf.exe) The Odbcconf.exe binary may be digitally signed by Microsoft.

Adversaries may abuse odbcconf.exe to bypass application control solutions that do not account for its potential abuse. Similar to [Regsvr32](https://attack.mitre.org/techniques/T1218/010), odbcconf.exe has a <code>REGSVR</code> flag that can be misused to execute DLLs (ex: <code>odbcconf.exe /S /A &lbrace;REGSVR "C:\Users\Public\file.dll"&rbrace;</code>).(Citation: LOLBAS Odbcconf)(Citation: TrendMicro Squiblydoo Aug 2017)(Citation: TrendMicro Cobalt Group Nov 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/008)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S1039 - Bumblebee](../../../../Threat%20Intelligence/Software/Malware/S1039%20-%20Bumblebee.md) — [Bumblebee](https://attack.mitre.org/software/S1039) can use `odbcconf.exe` to run DLLs on targeted hosts.(Citation: Cybereason Bumblebee August 2022) [Cybereason Bumblebee August 2022](https://www.cybereason.com/blog/threat-analysis-report-bumblebee-loader-the-high-road-to-enterprise-domain-control)
- [G0080 - Cobalt Group](../../../../Threat%20Intelligence/Groups/G0080%20-%20Cobalt%20Group.md) — [Cobalt Group](https://attack.mitre.org/groups/G0080) has used <code>odbcconf</code> to proxy the execution of malicious DLL files.(Citation: TrendMicro Cobalt Group Nov 2017) [TrendMicro Cobalt Group Nov 2017](https://blog.trendmicro.com/trendlabs-security-intelligence/cobalt-spam-runs-use-macros-cve-2017-8759-exploit/)
- [S1130 - Raspberry Robin](../../../../Threat%20Intelligence/Software/Malware/S1130%20-%20Raspberry%20Robin.md) — [Raspberry Robin](https://attack.mitre.org/software/S1130) uses the Windows utility odbcconf.exe to execute malicious commands, using the <code>regsvr</code> flag to execute DLLs and bypass application control mechanisms that are not monitoring for odbcconf.exe abuse.(Citation: RedCanary RaspberryRobin 2022) [RedCanary RaspberryRobin 2022](https://redcanary.com/blog/threat-intelligence/raspberry-robin/)

## Detection strategies

- [DET0486 - Detecting Odbcconf Proxy Execution of Malicious DLLs](../../../../Defenses/Detection%20Strategies/DET0486%20-%20Detecting%20Odbcconf%20Proxy%20Execution%20of%20Malicious%20DLLs.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Odbcconf.exe may not be necessary within a given environment.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control configured to block execution of Odbcconf.exe if it is not required for a given system or network to prevent potential misuse by adversaries.

## Sources

- [TrendMicro Squiblydoo Aug 2017](https://blog.trendmicro.com/trendlabs-security-intelligence/backdoor-carrying-emails-set-sights-on-russian-speaking-businesses/)
- [TrendMicro Cobalt Group Nov 2017](https://blog.trendmicro.com/trendlabs-security-intelligence/cobalt-spam-runs-use-macros-cve-2017-8759-exploit/)
- [LOLBAS Odbcconf](https://lolbas-project.github.io/lolbas/Binaries/Odbcconf/)
- [Microsoft odbcconf.exe](https://docs.microsoft.com/en-us/sql/odbc/odbcconf-exe?view=sql-server-2017)
