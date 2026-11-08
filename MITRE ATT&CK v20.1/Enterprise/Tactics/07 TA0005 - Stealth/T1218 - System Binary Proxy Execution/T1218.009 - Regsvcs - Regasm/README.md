# T1218.009 - Regsvcs/Regasm

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse Regsvcs and Regasm to proxy execution of code through a trusted Windows utility. Regsvcs and Regasm are Windows command-line utilities that are used to register .NET [Component Object Model](https://attack.mitre.org/techniques/T1559/001) (COM) assemblies. Both are binaries that may be digitally signed by Microsoft.(Citation: MSDN Regsvcs)(Citation: MSDN Regasm)

Both utilities may be used to bypass application control through use of attributes within the binary to specify code that should be run before registration or unregistration: <code>[ComRegisterFunction]</code> or <code>[ComUnregisterFunction]</code> respectively. The code with the registration and unregistration attributes will be executed even if the process is run under insufficient privileges and fails to execute.(Citation: LOLBAS Regsvcs)(Citation: LOLBAS Regasm)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/009)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0361 - Detecting .NET COM Registration Abuse via Regsvcs/Regasm](../../../../Defenses/Detection%20Strategies/DET0361%20-%20Detecting%20.NET%20COM%20Registration%20Abuse%20via%20Regsvcs%20-%20Regasm.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Regsvcs and Regasm may not be necessary within a given environment.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Block execution of Regsvcs.exe and Regasm.exe if they are not required for a given system or network to prevent potential misuse by adversaries.

## Procedure examples

- [S0331 - Agent Tesla](../../../../Threat%20Intelligence/Software/Malware/S0331%20-%20Agent%20Tesla.md) — [Agent Tesla](https://attack.mitre.org/software/S0331) has dropped RegAsm.exe onto systems for performing malicious activity.(Citation: SentinelLabs Agent Tesla Aug 2020) [SentinelLabs Agent Tesla Aug 2020](https://labs.sentinelone.com/agent-tesla-old-rat-uses-new-tricks-to-stay-on-top/)

## Sources

- [LOLBAS Regasm](https://lolbas-project.github.io/lolbas/Binaries/Regasm/)
- [LOLBAS Regsvcs](https://lolbas-project.github.io/lolbas/Binaries/Regsvcs/)
- [MSDN Regasm](https://msdn.microsoft.com/en-us/library/tzat5yw6.aspx)
- [MSDN Regsvcs](https://msdn.microsoft.com/en-us/library/04za0hca.aspx)
