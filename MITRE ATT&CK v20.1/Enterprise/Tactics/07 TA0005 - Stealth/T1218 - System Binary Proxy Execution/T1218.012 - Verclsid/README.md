# T1218.012 - Verclsid

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse verclsid.exe to proxy execution of malicious code. Verclsid.exe is known as the Extension CLSID Verification Host and is responsible for verifying each shell extension before they are used by Windows Explorer or the Windows Shell.(Citation: WinOSBite verclsid.exe)

Adversaries may abuse verclsid.exe to execute malicious payloads. This may be achieved by running <code>verclsid.exe /S /C {CLSID}</code>, where the file is referenced by a Class ID (CLSID), a unique identification number used to identify COM objects. COM payloads executed by verclsid.exe may be able to perform various malicious actions, such as loading and executing COM scriptlets (SCT) from remote servers (similar to [Regsvr32](https://attack.mitre.org/techniques/T1218/010)). Since the binary may be signed and/or native on Windows systems, proxying execution via verclsid.exe may bypass application control solutions that do not account for its potential abuse.(Citation: LOLBAS Verclsid)(Citation: Red Canary Verclsid.exe)(Citation: BOHOPS Abusing the COM Registry)(Citation: Nick Tyrer GitHub)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/012)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0499 - Hancitor](../../../../Threat%20Intelligence/Software/Malware/S0499%20-%20Hancitor.md) — [Hancitor](https://attack.mitre.org/software/S0499) has used verclsid.exe to download and execute a malicious script.(Citation: Red Canary Verclsid.exe) [Red Canary Verclsid.exe](https://redcanary.com/blog/verclsid-exe-threat-detection/)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Consider removing verclsid.exe if it is not necessary within a given environment.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control configured to block execution of verclsid.exe if it is not required for a given system or network to prevent potential misuse by adversaries.
- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Consider modifying host firewall rules to prevent egress traffic from verclsid.exe.

## Detection strategies

- [DET0042 - Detection Strategy for T1218.012 Verclsid Abuse](../../../../Defenses/Detection%20Strategies/DET0042%20-%20Detection%20Strategy%20for%20T1218.012%20Verclsid%20Abuse.md)

## Sources

- [BOHOPS Abusing the COM Registry](https://bohops.com/2018/08/18/abusing-the-com-registry-structure-part-2-loading-techniques-for-evasion-and-persistence/)
- [Red Canary Verclsid.exe](https://redcanary.com/blog/verclsid-exe-threat-detection/)
- [LOLBAS Verclsid](https://lolbas-project.github.io/lolbas/Binaries/Verclsid/)
- [Nick Tyrer GitHub](https://gist.github.com/NickTyrer/0598b60112eaafe6d07789f7964290d5)
- [WinOSBite verclsid.exe](https://winosbite.com/verclsid-exe/)
