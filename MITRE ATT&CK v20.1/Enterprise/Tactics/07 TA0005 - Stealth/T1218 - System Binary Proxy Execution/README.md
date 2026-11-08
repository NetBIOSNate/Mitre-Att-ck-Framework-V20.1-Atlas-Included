# T1218 - System Binary Proxy Execution

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may bypass process and/or signature-based defenses by proxying execution of malicious content with signed, or otherwise trusted, binaries. Binaries used in this technique are often Microsoft-signed files, indicating that they have been either downloaded from Microsoft or are already native in the operating system.(Citation: LOLBAS Project) Binaries signed with trusted digital certificates can typically execute on Windows systems protected by digital signature validation. Several Microsoft signed binaries that are default on Windows installations can be used to proxy execution of other files or commands.

Similarly, on Linux systems adversaries may abuse trusted binaries such as <code>split</code> to proxy execution of malicious commands.(Citation: split man page)(Citation: GTFO split)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1218.003 - CMSTP](T1218.003%20-%20CMSTP/README.md)
- [T1218.001 - Compiled HTML File](T1218.001%20-%20Compiled%20HTML%20File/README.md)
- [T1218.002 - Control Panel](T1218.002%20-%20Control%20Panel/README.md)
- [T1218.015 - Electron Applications](T1218.015%20-%20Electron%20Applications/README.md)
- [T1218.004 - InstallUtil](T1218.004%20-%20InstallUtil/README.md)
- [T1218.013 - Mavinject](T1218.013%20-%20Mavinject/README.md)
- [T1218.014 - MMC](T1218.014%20-%20MMC/README.md)
- [T1218.005 - Mshta](T1218.005%20-%20Mshta/README.md)
- [T1218.007 - Msiexec](T1218.007%20-%20Msiexec/README.md)
- [T1218.008 - Odbcconf](T1218.008%20-%20Odbcconf/README.md)
- [T1218.009 - Regsvcs/Regasm](T1218.009%20-%20Regsvcs%20-%20Regasm/README.md)
- [T1218.010 - Regsvr32](T1218.010%20-%20Regsvr32/README.md)
- [T1218.011 - Rundll32](T1218.011%20-%20Rundll32/README.md)
- [T1218.012 - Verclsid](T1218.012%20-%20Verclsid/README.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Many native binaries may not be necessary within a given environment.
- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Consider using application control to prevent execution of binaries that are susceptible to abuse and not required for a given system or network.
- [M1050 - Exploit Protection](../../../Defenses/Mitigations/M1050%20-%20Exploit%20Protection.md) — Microsoft's Enhanced Mitigation Experience Toolkit (EMET) Attack Surface Reduction (ASR) feature can be used to block methods of using using trusted binaries to bypass application control.
- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Use network appliances to filter ingress or egress traffic and perform protocol-based filtering. Configure software on endpoints to filter network traffic.
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict execution of particularly vulnerable binaries to privileged accounts or groups that need to use it to lessen the opportunities for malicious usage.
- [M1021 - Restrict Web-Based Content](../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Restrict use of certain websites, block downloads/attachments, block Javascript, restrict browser extensions, etc.

## Procedure examples

- [G0032 - Lazarus Group](../../../Threat%20Intelligence/Groups/G0032%20-%20Lazarus%20Group.md) — [Lazarus Group](https://attack.mitre.org/groups/G0032) lnk files used for persistence have abused the Windows Update Client (<code>wuauclt.exe</code>) to execute a malicious DLL.(Citation: Lazarus APT January 2022)(Citation: Qualys LolZarus) [Lazarus APT January 2022](https://blog.malwarebytes.com/threat-intelligence/2022/01/north-koreas-lazarus-apt-leverages-windows-update-client-github-in-latest-campaign/) · [Qualys LolZarus](https://blog.qualys.com/vulnerabilities-threat-research/2022/02/08/lolzarus-lazarus-group-incorporating-lolbins-into-campaigns)
- [G1017 - Volt Typhoon](../../../Threat%20Intelligence/Groups/G1017%20-%20Volt%20Typhoon.md) — [Volt Typhoon](https://attack.mitre.org/groups/G1017) has used native tools and processes including living off the land binaries or “LOLBins" to maintain and expand access to the victim networks.(Citation: CISA AA24-038A PRC Critical Infrastructure February 2024) [CISA AA24-038A PRC Critical Infrastructure February 2024](https://www.cisa.gov/sites/default/files/2024-03/aa24-038a_csa_prc_state_sponsored_actors_compromise_us_critical_infrastructure_3.pdf)

## Detection strategies

- [DET0081 - Detection of Proxy Execution via Trusted Signed Binaries Across Platforms](../../../Defenses/Detection%20Strategies/DET0081%20-%20Detection%20of%20Proxy%20Execution%20via%20Trusted%20Signed%20Binaries%20Across%20Platforms.md)

## Sources

- [GTFO split](https://gtfobins.github.io/gtfobins/split/)
- [LOLBAS Project](https://github.com/LOLBAS-Project/LOLBAS#criteria)
- [split man page](https://man7.org/linux/man-pages/man1/split.1.html)
