# T1137.004 - Outlook Home Page

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1137 - Office Application Startup](../README.md)

Adversaries may abuse Microsoft Outlook's Home Page feature to obtain persistence on a compromised system. Outlook Home Page is a legacy feature used to customize the presentation of Outlook folders. This feature allows for an internal or external URL to be loaded and presented whenever a folder is opened. A malicious HTML page can be crafted that will execute code when loaded by Outlook Home Page.(Citation: SensePost Outlook Home Page)

Once malicious home pages have been added to the user’s mailbox, they will be loaded when Outlook is started. Malicious Home Pages will execute when the right Outlook folder is loaded/reloaded.(Citation: SensePost Outlook Home Page)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1137/004)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent Office applications from creating child processes and from writing potentially malicious executable content to disk. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — For the Outlook methods, blocking macros may be ineffective as the Visual Basic engine used for these features is separate from the macro scripting engine.(Citation: SensePost Outlook Forms) Microsoft has released patches to try to address each issue. Ensure KB3191938 which blocks Outlook Visual Basic and displays a malicious code warning, KB4011091 which disables custom forms by default, and KB4011162 which removes the legacy Home Page feature, are applied to systems.(Citation: SensePost Outlook Home Page) [SensePost Outlook Forms](https://sensepost.com/blog/2017/outlook-forms-and-shells/) · [SensePost Outlook Home Page](https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/)

## Procedure examples

- [G0049 - OilRig](../../../../Threat%20Intelligence/Groups/G0049%20-%20OilRig.md) — [OilRig](https://attack.mitre.org/groups/G0049) has abused the Outlook Home Page feature for persistence. [OilRig](https://attack.mitre.org/groups/G0049) has also used CVE-2017-11774 to roll back the initial patch designed to protect against Home Page abuse.(Citation: FireEye Outlook Dec 2019) [FireEye Outlook Dec 2019](https://www.fireeye.com/blog/threat-research/2019/12/breaking-the-rules-tough-outlook-for-home-page-attacks.html)
- [S0358 - Ruler](../../../../Threat%20Intelligence/Software/Tools/S0358%20-%20Ruler.md) — [Ruler](https://attack.mitre.org/software/S0358) can be used to automate the abuse of Outlook Home Pages to establish persistence.(Citation: SensePost Ruler GitHub) [SensePost Ruler GitHub](https://github.com/sensepost/ruler)

## Detection strategies

- [DET0177 - Detect Persistence via Outlook Home Page Exploitation](../../../../Defenses/Detection%20Strategies/DET0177%20-%20Detect%20Persistence%20via%20Outlook%20Home%20Page%20Exploitation.md)

## Sources

- [Microsoft Detect Outlook Forms](https://docs.microsoft.com/en-us/office365/securitycompliance/detect-and-remediate-outlook-rules-forms-attack)
- [SensePost NotRuler](https://github.com/sensepost/notruler)
- [SensePost Outlook Home Page](https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/)
