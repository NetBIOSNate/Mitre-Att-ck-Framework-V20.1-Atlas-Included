# T1202 - Indirect Command Execution

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may abuse utilities that allow for command execution to bypass security restrictions that limit the use of command-line interpreters. Various Windows utilities may be used to execute commands, possibly without invoking [cmd](https://attack.mitre.org/software/S0106). For example, [Forfiles](https://attack.mitre.org/software/S0193), the Program Compatibility Assistant (`pcalua.exe`), components of the Windows Subsystem for Linux (WSL), `Scriptrunner.exe`, as well as other utilities may invoke the execution of programs and commands from a [Command and Scripting Interpreter](https://attack.mitre.org/techniques/T1059), Run window, or via scripts.(Citation: VectorSec ForFiles Aug 2017)(Citation: Evi1cg Forfiles Nov 2017)(Citation: Secure Team - Scriptrunner.exe)(Citation: SS64)(Citation: Bleeping Computer - Scriptrunner.exe) Adversaries may also abuse the `ssh.exe` binary to execute malicious commands via the `ProxyCommand` and `LocalCommand` options, which can be invoked via the `-o` flag or by modifying the SSH config file.(Citation: Threat Actor Targets the Manufacturing industry with Lumma Stealer and Amadey Bot)

Adversaries may abuse these features for [Stealth](https://attack.mitre.org/tactics/TA0005), specifically to perform arbitrary execution while subverting detections and/or mitigation controls (such as Group Policy) that limit/prevent the usage of [cmd](https://attack.mitre.org/software/S0106) or file extensions more commonly associated with malicious payloads.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1202)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S0193 - Forfiles](../../../Threat%20Intelligence/Software/Tools/S0193%20-%20Forfiles.md) — [Forfiles](https://attack.mitre.org/software/S0193) can be used to subvert controls and possibly conceal command execution by not directly invoking [cmd](https://attack.mitre.org/software/S0106).(Citation: VectorSec ForFiles Aug 2017)(Citation: Evi1cg Forfiles Nov 2017) [Evi1cg Forfiles Nov 2017](https://x.com/Evi1cg/status/935027922397573120) · [VectorSec ForFiles Aug 2017](https://x.com/vector_sec/status/896049052642533376)
- [G0032 - Lazarus Group](../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) persistence mechanisms have used <code>forfiles.exe</code> to execute .htm files.(Citation: Qualys LolZarus) [Qualys LolZarus](https://blog.qualys.com/vulnerabilities-threat-research/2022/02/08/lolzarus-lazarus-group-incorporating-lolbins-into-campaigns)
- [G1039 - RedCurl](../../../Threat%20Intelligence/Groups/G1039%20-%20RedCurl.md) — [RedCurl](https://attack.mitre.org/groups/G1039) has used pcalua.exe to obfuscate binary execution and remote connections.(Citation: trendmicro_redcurl) [trendmicro_redcurl](https://www.trendmicro.com/en_us/research/24/c/unveiling-earth-kapre-aka-redcurls-cyberespionage-tactics-with-t.html)
- [S0379 - Revenge RAT](../../../Threat%20Intelligence/Software/Malware/S0379%20-%20Revenge%20RAT.md) — [Revenge RAT](https://attack.mitre.org/software/S0379) uses the [Forfiles](https://attack.mitre.org/software/S0193) utility to execute commands on the system.(Citation: Cofense RevengeRAT Feb 2019) [Cofense RevengeRAT Feb 2019](https://web.archive.org/web/20200428173819/https://cofense.com/upgrades-delivery-support-infrastructure-revenge-rat-malware-bigger-threat/)

## Detection strategies

- [DET0200 - Indirect Command Execution – Windows utility abuse behavior chain](../../../Defenses/Detection%20Strategies/DET0200%20-%20Indirect%20Command%20Execution%20%E2%80%93%20Windows%20utility%20abuse%20behavior%20chain.md)

## Sources

- [Bleeping Computer - Scriptrunner.exe](https://www.bleepingcomputer.com/news/security/hackers-abuse-windows-error-reporting-tool-to-deploy-malware/)
- [Threat Actor Targets the Manufacturing industry with Lumma Stealer and Amadey Bot](https://cyble.com/blog/threat-actor-targets-manufacturing-industry-with-malware/)
- [Evi1cg Forfiles Nov 2017](https://x.com/Evi1cg/status/935027922397573120)
- [Secure Team - Scriptrunner.exe](https://secureteam.co.uk/2023/01/08/windows-error-reporting-tool-abused-to-load-malware/)
- [SS64](https://ss64.com/nt/scriptrunner.html)
- [VectorSec ForFiles Aug 2017](https://x.com/vector_sec/status/896049052642533376)
