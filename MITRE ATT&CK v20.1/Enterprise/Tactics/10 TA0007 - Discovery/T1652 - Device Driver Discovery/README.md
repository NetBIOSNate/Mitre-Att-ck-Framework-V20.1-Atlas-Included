# T1652 - Device Driver Discovery

[Enterprise](../../../README.md) / [Discovery](../README.md)

Adversaries may attempt to enumerate local device drivers on a victim host. Information about device drivers may highlight various insights that shape follow-on behaviors, such as the function/purpose of the host, present security tools (i.e. [Security Software Discovery](https://attack.mitre.org/techniques/T1518/001)) or other defenses (e.g., [Virtualization/Sandbox Evasion](https://attack.mitre.org/techniques/T1497)), as well as potential exploitable vulnerabilities (e.g., [Exploitation for Privilege Escalation](https://attack.mitre.org/techniques/T1068)).

Many OS utilities may provide information about local device drivers, such as `driverquery.exe` and the `EnumDeviceDrivers()` API function on Windows.(Citation: Microsoft Driverquery)(Citation: Microsoft EnumDeviceDrivers) Information about device drivers (as well as associated services, i.e., [System Service Discovery](https://attack.mitre.org/techniques/T1007)) may also be available in the Registry.(Citation: Microsoft Registry Drivers)

On Linux/macOS, device drivers (in the form of kernel modules) may be visible within `/dev` or using utilities such as `lsmod` and `modinfo`.(Citation: Linux Kernel Programming)(Citation: lsmod man)(Citation: modinfo man)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1652)

**Tactics**  [Discovery](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S0376 - HOPLIGHT](../../../Threat%20Intelligence/Software/Malware/S0376%20-%20HOPLIGHT.md) — [HOPLIGHT](https://attack.mitre.org/software/S0376) can enumerate device drivers located in the registry at `HKLM\Software\WBEM\WDM`.(Citation: US-CERT HOPLIGHT Apr 2019) [US-CERT HOPLIGHT Apr 2019](https://www.us-cert.gov/ncas/analysis-reports/AR19-100A)
- [S1139 - INC Ransomware](../../../Threat%20Intelligence/Software/Malware/S1139%20-%20INC%20Ransomware.md) — [INC Ransomware](https://attack.mitre.org/software/S1139) can verify the presence of specific drivers on compromised hosts including Microsoft Print to PDF and Microsoft XPS Document Writer.(Citation: Cybereason INC Ransomware November 2023) [Cybereason INC Ransomware November 2023](https://web.archive.org/web/20231202022946/https://www.cybereason.com/hubfs/dam/collateral/reports/threat-alert-inc-ransomware.pdf)
- [G1051 - Medusa Group](../../../Threat%20Intelligence/Groups/G1051%20-%20Medusa%20Group.md) — [Medusa Group](https://attack.mitre.org/groups/G1051) has queried drivers on the victim device through the command `driverquery`.(Citation: CISA Medusa Group Medusa Ransomware March 2025) [CISA Medusa Group Medusa Ransomware March 2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-071a)
- [S0125 - Remsec](../../../Threat%20Intelligence/Software/Malware/S0125%20-%20Remsec.md) — [Remsec](https://attack.mitre.org/software/S0125) has a plugin to detect active drivers of some security products.(Citation: Kaspersky ProjectSauron Technical Analysis) [Kaspersky ProjectSauron Technical Analysis](https://securelist.com/files/2016/07/The-ProjectSauron-APT_Technical_Analysis_KL.pdf)

## Detection strategies

- [DET0579 - Detection Strategy for Device Driver Discovery](../../../Defenses/Detection%20Strategies/DET0579%20-%20Detection%20Strategy%20for%20Device%20Driver%20Discovery.md)

## Sources

- [lsmod man](https://man7.org/linux/man-pages/man8/lsmod.8.html)
- [Microsoft Registry Drivers](https://learn.microsoft.com/windows-hardware/drivers/install/overview-of-registry-trees-and-keys)
- [Microsoft EnumDeviceDrivers](https://learn.microsoft.com/windows/win32/api/psapi/nf-psapi-enumdevicedrivers)
- [Microsoft Driverquery](https://learn.microsoft.com/windows-server/administration/windows-commands/driverquery)
- [Linux Kernel Programming](https://www.tldp.org/LDP/lkmpg/2.4/lkmpg.pdf)
- [modinfo man](https://linux.die.net/man/8/modinfo)
