# T1137.001 - Office Template Macros

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1137 - Office Application Startup](../README.md)

Adversaries may abuse Microsoft Office templates to obtain persistence on a compromised system. Microsoft Office contains templates that are part of common Office applications and are used to customize styles. The base templates within the application are used each time an application starts.(Citation: Microsoft Change Normal Template)

Office Visual Basic for Applications (VBA) macros(Citation: MSDN VBA in Office) can be inserted into the base template and used to execute code when the respective Office application starts in order to obtain persistence. Examples for both Word and Excel have been discovered and published. By default, Word has a Normal.dotm template created that can be modified to include a malicious macro. Excel does not have a template file created by default, but one can be added that will automatically be loaded.(Citation: enigma0x3 normal.dotm)(Citation: Hexacorn Office Template Macros) Shared templates may also be stored and pulled from remote locations.(Citation: GlobalDotName Jun 2019) 

Word Normal.dotm location:<br>
<code>C:\Users\&lt;username&gt;\AppData\Roaming\Microsoft\Templates\Normal.dotm</code>

Excel Personal.xlsb location:<br>
<code>C:\Users\&lt;username&gt;\AppData\Roaming\Microsoft\Excel\XLSTART\PERSONAL.XLSB</code>

Adversaries may also change the location of the base template to point to their own by hijacking the application's search order, e.g. Word 2016 will first look for Normal.dotm under <code>C:\Program Files (x86)\Microsoft Office\root\Office16\</code>, or by modifying the GlobalDotName registry key. By modifying the GlobalDotName registry key an adversary can specify an arbitrary location, file name, and file extension to use for the template that will be loaded on application startup. To abuse GlobalDotName, adversaries may first need to register the template as a trusted document or place it in a trusted location.(Citation: GlobalDotName Jun 2019) 

An adversary may need to enable macros to execute unrestricted depending on the system or enterprise security policy on use of macros.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1137/001)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Office Suite](../../../../Platforms/Office%20Suite.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0519 - Detect Persistence via Office Template Macro Injection or Registry Hijack](../../../../Defenses/Detection%20Strategies/DET0519%20-%20Detect%20Persistence%20via%20Office%20Template%20Macro%20Injection%20or%20Registry%20Hijack.md)

## Procedure examples

- [S0475 - BackConfig](../../../../Threat%20Intelligence/Software/Malware/S0475%20-%20BackConfig.md) — [BackConfig](https://attack.mitre.org/software/S0475) has the ability to use hidden columns in Excel spreadsheets to store executable files or commands for VBA macros.(Citation: Unit 42 BackConfig May 2020) [Unit 42 BackConfig May 2020](https://unit42.paloaltonetworks.com/updated-backconfig-malware-targeting-government-and-military-organizations/)
- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) has the ability to use an Excel Workbook to execute additional code by enabling Office to trust macros and execute code without user permission.(Citation: Talos Cobalt Strike September 2020) [Talos Cobalt Strike September 2020](https://web.archive.org/web/20210219195905/https://talos-intelligence-site.s3.amazonaws.com/production/document_files/files/000/095/031/original/Talos_Cobalt_Strike.pdf)
- [G0069 - MuddyWater](../../../../Threat%20Intelligence/Groups/G0069%20-%20MuddyWater.md) — [MuddyWater](https://attack.mitre.org/groups/G0069) has used a Word Template, Normal.dotm, for persistence.(Citation: Reaqta MuddyWater November 2017) [Reaqta MuddyWater November 2017](https://reaqta.com/2017/11/muddywater-apt-targeting-middle-east/)
- [C0060 - Operation AkaiRyū](../../../../Threat%20Intelligence/Campaigns/C0060%20-%20Operation%20AkaiRy%C5%AB.md) — During [Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060), [MirrorFace](https://attack.mitre.org/groups/G1054) loaded malicious Word templates containing VBA code leading to installation of [UPPERCUT](https://attack.mitre.org/software/S0275).(Citation: ESET MirrorFace 2025) [ESET MirrorFace 2025](https://www.welivesecurity.com/en/eset-research/operation-akairyu-mirrorface-invites-europe-expo-2025-revives-anel-backdoor/)
- [S9026 - ROAMINGHOUSE](../../../../Threat%20Intelligence/Software/Malware/S9026%20-%20ROAMINGHOUSE.md) — [ROAMINGHOUSE](https://attack.mitre.org/software/S9026) has been loaded as a Word Template file when victims opened a decoy document placed in `%APPDATA%\Microsoft\Templates` alongside a [ROAMINGHOUSE](https://attack.mitre.org/software/S9026) macro.(Citation: Trend Micro Earth Kasha Anel NOV 2024) [Trend Micro Earth Kasha Anel NOV 2024](https://www.trendmicro.com/en_us/research/24/k/return-of-anel-in-the-recent-earth-kasha-spearphishing-campaign.html)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent Office applications from creating child processes and from writing potentially malicious executable content to disk. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)
- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Follow Office macro security best practices suitable for your environment. Disable Office VBA macros from executing. Disable Office add-ins. If they are required, follow best practices for securing them by requiring them to be signed and disabling user notification for allowing add-ins. For some add-ins types (WLL, VBA) additional mitigation is likely required as disabling add-ins in the Office Trust Center does not disable WLL nor does it prevent VBA code from executing. (Citation: MRWLabs Office Persistence Add-ins) [MRWLabs Office Persistence Add-ins](https://web.archive.org/web/20190526112859/https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/)

## Sources

- [MSDN VBA in Office](https://msdn.microsoft.com/en-us/vba/office-shared-vba/articles/getting-started-with-vba-in-office)
- [Hexacorn Office Template Macros](http://www.hexacorn.com/blog/2017/04/19/beyond-good-ol-run-key-part-62/)
- [Microsoft Change Normal Template](https://support.office.com/article/Change-the-Normal-template-Normal-dotm-06de294b-d216-47f6-ab77-ccb5166f98ea)
- [enigma0x3 normal.dotm](https://enigma0x3.net/2014/01/23/maintaining-access-with-normal-dotm/comment-page-1/)
- [GlobalDotName Jun 2019](https://www.221bluestreet.com/post/office-templates-and-globaldotname-a-stealthy-office-persistence-technique)
