# T1027.012 - LNK Icon Smuggling

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may smuggle commands to download malicious payloads past content filters by hiding them within otherwise seemingly benign windows shortcut files. Windows shortcut files (.LNK) include many metadata fields, including an icon location field (also known as the `IconEnvironmentDataBlock`) designed to specify the path to an icon file that is to be displayed for the LNK file within a host directory. 

Adversaries may abuse this LNK metadata to download malicious payloads. For example, adversaries have been observed using LNK files as phishing payloads to deliver malware. Once invoked (e.g., [Malicious File](https://attack.mitre.org/techniques/T1204/002)), payloads referenced via external URLs within the LNK icon location field may be downloaded. These files may also then be invoked by [Command and Scripting Interpreter](https://attack.mitre.org/techniques/T1059)/[System Binary Proxy Execution](https://attack.mitre.org/techniques/T1218) arguments within the target path field of the LNK.(Citation: Unprotect Shortcut)(Citation: Booby Trap Shortcut 2017)

LNK Icon Smuggling may also be utilized post compromise, such as malicious scripts executing an LNK on an infected host to download additional malicious payloads.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/012)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0405 - Detection Strategy for LNK Icon Smuggling](../../../../Defenses/Detection%20Strategies/DET0405%20-%20Detection%20Strategy%20for%20LNK%20Icon%20Smuggling.md)

## Mitigations

- [M1049 - Antivirus/Antimalware](../../../../Defenses/Mitigations/M1049%20-%20Antivirus%20-%20Antimalware.md) — Use signatures or heuristics to detect malicious LNK and subsequently downloaded files.
- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent execution of potentially obfuscated scripts or payloads.

## Procedure examples

- [G0047 - Gamaredon Group](../../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used LNK files to hide malicious scripts for execution.(Citation: SymantecCarbonBlack_ShuckwormUSB_Apr2025)(Citation: VenereCiscoTalos_Gamaredon_Mar2025) [SymantecCarbonBlack_ShuckwormUSB_Apr2025](https://www.security.com/threat-intelligence/shuckworm-ukraine-gammasteel) · [VenereCiscoTalos_Gamaredon_Mar2025](https://blog.talosintelligence.com/gamaredon-campaign-distribute-remcos/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used the LNK icon location to execute malicious scripts.(Citation: Aryaka Kimsuky July 2025) [Kimsuky](https://attack.mitre.org/groups/G0094) has also padded the LNK target field properties with extra spaces to obscure the script.(Citation: Securonix Kimsuky February 2025) [Securonix Kimsuky February 2025](https://www.securonix.com/blog/analyzing-deepdrive-north-korean-threat-actors-observed-exploiting-trusted-platforms-for-targeted-attacks/) · [Aryaka Kimsuky July 2025](https://www.aryaka.com/docs/reports/aryaka-kimsuky-apt-operational-blueprint.pdf)
- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has utilized LNK files to hide malicious scripts for execution.(Citation: Cisco Talos MUSTANG PANDA PLUGX PUBLOAD MAY 2022)(Citation: Sophos Mustang Panda PLUGX) [Mustang Panda](https://attack.mitre.org/groups/G0129) has also leveraged LNK files that were programmed to display a PDF icon to entice the victim to click on the file to execute an office.exe binary.(Citation: CSIRT CTI MUSTANG PANDA PUBLOAD TONESHELL JAN 2024) [Cisco Talos MUSTANG PANDA PLUGX PUBLOAD MAY 2022](https://blog.talosintelligence.com/mustang-panda-targets-europe/) · [CSIRT CTI MUSTANG PANDA PUBLOAD TONESHELL JAN 2024](https://csirt-cti.net/2024/01/23/stately-taurus-targets-myanmar/) · [Sophos Mustang Panda PLUGX](https://www.secureworks.com/blog/bronze-president-targets-government-officials)
- [S1239 - TONESHELL](../../../../Threat%20Intelligence/Software/Malware/S1239%20-%20TONESHELL.md) — [TONESHELL](https://attack.mitre.org/software/S1239) has been initiated using LNK files that were programmed to display a PDF icon to entice the victim to click on the file to execute an office.exe binary.(Citation: CSIRT CTI MUSTANG PANDA PUBLOAD TONESHELL JAN 2024) [CSIRT CTI MUSTANG PANDA PUBLOAD TONESHELL JAN 2024](https://csirt-cti.net/2024/01/23/stately-taurus-targets-myanmar/)

## Sources

- [Unprotect Shortcut](https://unprotect.it/technique/shortcut-hiding/)
- [Booby Trap Shortcut 2017](https://web.archive.org/web/20171225152553/https://www.uperesia.com/booby-trapped-shortcut)
