# T1137.006 - Add-ins

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1137 - Office Application Startup](../README.md)

Adversaries may abuse Microsoft Office add-ins to obtain persistence on a compromised system. Office add-ins can be used to add functionality to Office programs.(Citation: Microsoft Office Add-ins) There are different types of add-ins that can be used by the various Office products; including Word/Excel add-in Libraries (WLL/XLL), VBA add-ins, Office Component Object Model (COM) add-ins, automation add-ins, VBA Editor (VBE), Visual Studio Tools for Office (VSTO) add-ins, and Outlook add-ins.(Citation: MRWLabs Office Persistence Add-ins)(Citation: FireEye Mail CDS 2018)

Add-ins can be used to obtain persistence because they can be set to execute code when an Office application starts.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1137/006)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent Office applications from creating child processes and from writing potentially malicious executable content to disk. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

## Procedure examples

- [S0268 - Bisonal](../../../../Threat%20Intelligence/Software/Malware/S0268%20-%20Bisonal.md) — [Bisonal](https://attack.mitre.org/software/S0268) has been loaded through a `.wll` extension added to the ` %APPDATA%\microsoft\word\startup\` repository.(Citation: Talos Bisonal Mar 2020) [Talos Bisonal Mar 2020](https://blog.talosintelligence.com/2020/03/bisonal-10-years-of-play.html)
- [S1143 - LunarLoader](../../../../Threat%20Intelligence/Software/Malware/S1143%20-%20LunarLoader.md) — [LunarLoader](https://attack.mitre.org/software/S1143) has the ability to use Microsoft Outlook add-ins to establish persistence. (Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [S1142 - LunarMail](../../../../Threat%20Intelligence/Software/Malware/S1142%20-%20LunarMail.md) — [LunarMail](https://attack.mitre.org/software/S1142) has the ability to use Outlook add-ins for persistence.(Citation: ESET Turla Lunar toolset May 2024) [ESET Turla Lunar toolset May 2024](https://www.welivesecurity.com/en/eset-research/moon-backdoors-lunar-landing-diplomatic-missions/)
- [G0019 - Naikon](../../../../Threat%20Intelligence/Groups/G0019%20-%20Naikon.md) — [Naikon](https://attack.mitre.org/groups/G0019) has used the RoyalRoad exploit builder to drop a second stage loader, intel.wll, into the Word Startup folder on the compromised host.(Citation: CheckPoint Naikon May 2020) [CheckPoint Naikon May 2020](https://research.checkpoint.com/2020/naikon-apt-cyber-espionage-reloaded/)

## Detection strategies

- [DET0050 - Detect Persistence via Malicious Office Add-ins](../../../../Defenses/Detection%20Strategies/DET0050%20-%20Detect%20Persistence%20via%20Malicious%20Office%20Add-ins.md)

## Sources

- [FireEye Mail CDS 2018](https://web.archive.org/web/20190508170121/https://summit.fireeye.com/content/dam/fireeye-www/summit/cds-2018/presentations/cds18-technical-s03-youve-got-mail.pdf)
- [MRWLabs Office Persistence Add-ins](https://web.archive.org/web/20190526112859/https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/)
- [Microsoft Office Add-ins](https://support.office.com/article/Add-or-remove-add-ins-0af570c4-5cf3-4fa9-9b88-403625a0b460)
