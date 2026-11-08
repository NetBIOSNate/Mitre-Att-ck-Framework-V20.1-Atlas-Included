# T1127 - Trusted Developer Utilities Proxy Execution

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may take advantage of trusted developer utilities to proxy execution of malicious payloads. There are many utilities used for software development related tasks that can be used to execute code in various forms to assist in development, debugging, and reverse engineering.(Citation: engima0x3 DNX Bypass)(Citation: engima0x3 RCSI Bypass)(Citation: Exploit Monday WinDbg)(Citation: LOLBAS Tracker) These utilities may often be signed with legitimate certificates that allow them to execute on a system and proxy execution of malicious code through a trusted process that effectively bypasses application control solutions.

Smart App Control is a feature of Windows that blocks applications it considers potentially malicious from running by verifying unsigned applications against a known safe list from a Microsoft cloud service before executing them.(Citation: Microsoft Smart App Control) However, adversaries may leverage "reputation hijacking" to abuse an operating system’s trust of safe, signed applications that support the execution of arbitrary code. By leveraging [Trusted Developer Utilities Proxy Execution](https://attack.mitre.org/techniques/T1127) to run their malicious code, adversaries may bypass Smart App Control protections.(Citation: Elastic Security Labs)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1127)

**Tactics**  [Execution](../../04%20TA0002%20-%20Execution/README.md), [Stealth](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1127.002 - ClickOnce](T1127.002%20-%20ClickOnce/README.md)
- [T1127.003 - JamPlus](T1127.003%20-%20JamPlus/README.md)
- [T1127.001 - MSBuild](T1127.001%20-%20MSBuild/README.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Specific developer utilities may not be necessary within a given environment and should be removed if not used.
- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Certain developer utilities should be blocked or restricted if not required.
- [M1021 - Restrict Web-Based Content](../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Consider disabling software installation or execution from the internet via developer utilities.

## Detection strategies

- [DET0172 - Behavior-chain, platform-aware detection strategy for T1127 Trusted Developer Utilities Proxy Execution (Windows)](../../../Defenses/Detection%20Strategies/DET0172%20-%20Behavior-chain%2C%20platform-aware%20detection%20strategy%20for%20T1127%20Trusted%20Developer%20Utiliti.md)

## Sources

- [Exploit Monday WinDbg](https://web.archive.org/web/20160816135945/http://www.exploit-monday.com/2016/08/windbg-cdb-shellcode-runner.html)
- [Elastic Security Labs](https://www.elastic.co/security-labs/dismantling-smart-app-control)
- [LOLBAS Tracker](https://lolbas-project.github.io/lolbas/OtherMSBinaries/Tracker/)
- [Microsoft Smart App Control](https://support.microsoft.com/en-us/windows/smart-app-control-frequently-asked-questions-285ea03d-fa88-4d56-882e-6698afdb7003)
- [engima0x3 RCSI Bypass](https://enigma0x3.net/2016/11/21/bypassing-application-whitelisting-by-using-rcsi-exe/)
- [engima0x3 DNX Bypass](https://enigma0x3.net/2016/11/17/bypassing-application-whitelisting-by-using-dnx-exe/)
