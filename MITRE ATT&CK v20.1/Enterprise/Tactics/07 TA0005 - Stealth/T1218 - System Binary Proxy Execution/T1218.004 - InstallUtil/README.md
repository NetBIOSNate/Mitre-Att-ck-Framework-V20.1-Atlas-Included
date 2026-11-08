# T1218.004 - InstallUtil

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may use InstallUtil to proxy execution of code through a trusted Windows utility. InstallUtil is a command-line utility that allows for installation and uninstallation of resources by executing specific installer components specified in .NET binaries.(Citation: MSDN InstallUtil) The InstallUtil binary may also be digitally signed by Microsoft and located in the .NET directories on a Windows system: <code>C:\Windows\Microsoft.NET\Framework\v<version>\InstallUtil.exe</code> and <code>C:\Windows\Microsoft.NET\Framework64\v<version>\InstallUtil.exe</code>.

InstallUtil may also be used to bypass application control through use of attributes within the binary that execute the class decorated with the attribute <code>[System.ComponentModel.RunInstaller(true)]</code>.(Citation: LOLBAS Installutil)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/004)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — InstallUtil may not be necessary within a given environment.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use application control configured to block execution of InstallUtil.exe if it is not required for a given system or network to prevent potential misuse by adversaries.

## Procedure examples

- [S0631 - Chaes](../../../../Threat%20Intelligence/Software/Malware/S0631%20-%20Chaes.md) — [Chaes](https://attack.mitre.org/software/S0631) has used Installutill to download content.(Citation: Cybereason Chaes Nov 2020) [Cybereason Chaes Nov 2020](https://www.cybereason.com/hubfs/dam/collateral/reports/11-2020-Chaes-e-commerce-malware-research.pdf)
- [S1155 - Covenant](../../../../Threat%20Intelligence/Software/Tools/S1155%20-%20Covenant.md) — [Covenant](https://attack.mitre.org/software/S1155) can create launchers via an InstallUtil XML file to install new Grunt listeners.(Citation: Github Covenant) [Github Covenant](https://github.com/cobbr/Covenant)
- [G0045 - menuPass](../../../../Threat%20Intelligence/Groups/G0045%20-%20menuPass.md) — [menuPass](https://attack.mitre.org/groups/G0045) has used <code>InstallUtil.exe</code> to execute malicious software.(Citation: PWC Cloud Hopper Technical Annex April 2017) [PWC Cloud Hopper Technical Annex April 2017](https://www.pwc.co.uk/cyber-security/pdf/pwc-uk-operation-cloud-hopper-technical-annex-april-2017.pdf)
- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used <code>InstallUtil.exe</code> to execute a malicious Beacon stager.(Citation: Anomali MUSTANG PANDA October 2019) [Anomali MUSTANG PANDA October 2019](https://www.anomali.com/blog/china-based-apt-mustang-panda-targets-minority-groups-public-and-private-sector-organizations)
- [S1018 - Saint Bot](../../../../Threat%20Intelligence/Software/Malware/S1018%20-%20Saint%20Bot.md) — [Saint Bot](https://attack.mitre.org/software/S1018) had used `InstallUtil.exe` to download and deploy executables.(Citation: Malwarebytes Saint Bot April 2021) [Malwarebytes Saint Bot April 2021](https://blog.malwarebytes.com/threat-intelligence/2021/04/a-deep-dive-into-saint-bot-downloader/)
- [S0689 - WhisperGate](../../../../Threat%20Intelligence/Software/Malware/S0689%20-%20WhisperGate.md) — [WhisperGate](https://attack.mitre.org/software/S0689) has used `InstallUtil.exe` as part of its process to disable Windows Defender.(Citation: Unit 42 WhisperGate January 2022) [Unit 42 WhisperGate January 2022](https://unit42.paloaltonetworks.com/ukraine-cyber-conflict-cve-2021-32648-whispergate/#whispergate-malware-family)

## Detection strategies

- [DET0138 - Detection of Malicious Code Execution via InstallUtil.exe](../../../../Defenses/Detection%20Strategies/DET0138%20-%20Detection%20of%20Malicious%20Code%20Execution%20via%20InstallUtil.exe.md)

## Sources

- [LOLBAS Installutil](https://lolbas-project.github.io/lolbas/Binaries/Installutil/)
- [MSDN InstallUtil](https://msdn.microsoft.com/en-us/library/50614e95.aspx)
