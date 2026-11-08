# T1547.012 - Print Processors

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may abuse print processors to run malicious DLLs during system boot for persistence and/or privilege escalation. Print processors are DLLs that are loaded by the print spooler service, `spoolsv.exe`, during boot.(Citation: Microsoft Intro Print Processors)

Adversaries may abuse the print spooler service by adding print processors that load malicious DLLs at startup. A print processor can be installed through the <code>AddPrintProcessor</code> API call with an account that has <code>SeLoadDriverPrivilege</code> enabled. Alternatively, a print processor can be registered to the print spooler service by adding the <code>HKLM\SYSTEM\\[CurrentControlSet or ControlSet001]\Control\Print\Environments\\[Windows architecture: e.g., Windows x64]\Print Processors\\[user defined]\Driver</code> Registry key that points to the DLL.

For the malicious print processor to be correctly installed, the payload must be located in the dedicated system print-processor directory, that can be found with the <code>GetPrintProcessorDirectory</code> API call, or referenced via a relative path from this directory.(Citation: Microsoft AddPrintProcessor May 2018) After the print processors are installed, the print spooler service, which starts during boot, must be restarted in order for them to run.(Citation: ESET PipeMon May 2020)

The print spooler service runs under SYSTEM level permissions; therefore, print processors installed by an adversary may run under elevated privileges.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/012)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0026 - Windows Detection Strategy for T1547.012 - Print Processor DLL Persistence](../../../../Defenses/Detection%20Strategies/DET0026%20-%20Windows%20Detection%20Strategy%20for%20T1547.012%20-%20Print%20Processor%20DLL%20Persistence.md)

## Procedure examples

- [G1006 - Earth Lusca](../../../../Threat%20Intelligence/Groups/G1006%20-%20Earth%20Lusca.md) — [Earth Lusca](https://attack.mitre.org/groups/G1006) has added the Registry key `HKLM\SYSTEM\ControlSet001\Control\Print\Environments\Windows x64\Print Processors\UDPrint” /v Driver /d “spool.dll /f` to load malware as a Print Processor.(Citation: TrendMicro EarthLusca 2022) [TrendMicro EarthLusca 2022](https://www.trendmicro.com/content/dam/trendmicro/global/en/research/22/a/earth-lusca-employs-sophisticated-infrastructure-varied-tools-and-techniques/technical-brief-delving-deep-an-analysis-of-earth-lusca-operations.pdf)
- [S0666 - Gelsemium](../../../../Threat%20Intelligence/Software/Malware/S0666%20-%20Gelsemium.md) — [Gelsemium](https://attack.mitre.org/software/S0666) can drop itself in <code>C:\Windows\System32\spool\prtprocs\x64\winprint.dll</code> to be loaded automatically by the spoolsv Windows service.(Citation: ESET Gelsemium June 2021) [ESET Gelsemium June 2021](https://www.welivesecurity.com/wp-content/uploads/2021/06/eset_gelsemium.pdf)
- [S0501 - PipeMon](../../../../Threat%20Intelligence/Software/Malware/S0501%20-%20PipeMon.md) — The [PipeMon](https://attack.mitre.org/software/S0501) installer has modified the Registry key <code>HKLM\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows x64\Print Processors</code> to install [PipeMon](https://attack.mitre.org/software/S0501) as a Print Processor.(Citation: ESET PipeMon May 2020) [ESET PipeMon May 2020](https://www.welivesecurity.com/2020/05/21/no-game-over-winnti-group/)

## Mitigations

- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Limit user accounts that can load or unload device drivers by disabling <code>SeLoadDriverPrivilege</code>.

## Sources

- [Microsoft AddPrintProcessor May 2018](https://docs.microsoft.com/en-us/windows/win32/printdocs/addprintprocessor)
- [Microsoft Intro Print Processors](https://learn.microsoft.com/windows-hardware/drivers/print/introduction-to-print-processors)
- [ESET PipeMon May 2020](https://www.welivesecurity.com/2020/05/21/no-game-over-winnti-group/)
