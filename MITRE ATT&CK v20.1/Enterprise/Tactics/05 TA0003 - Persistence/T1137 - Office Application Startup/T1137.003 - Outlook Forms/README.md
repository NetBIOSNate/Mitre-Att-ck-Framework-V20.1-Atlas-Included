# T1137.003 - Outlook Forms

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1137 - Office Application Startup](../README.md)

Adversaries may abuse Microsoft Outlook forms to obtain persistence on a compromised system. Outlook forms are used as templates for presentation and functionality in Outlook messages. Custom Outlook forms can be created that will execute code when a specifically crafted email is sent by an adversary utilizing the same custom Outlook form.(Citation: SensePost Outlook Forms)

Once malicious forms have been added to the user’s mailbox, they will be loaded when Outlook is started. Malicious forms will execute when an adversary sends a specifically crafted email to the user.(Citation: SensePost Outlook Forms)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1137/003)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Procedure examples

- [S0358 - Ruler](../../../../Threat%20Intelligence/Software/Tools/S0358%20-%20Ruler.md) — [Ruler](https://attack.mitre.org/software/S0358) can be used to automate the abuse of Outlook Forms to establish persistence.(Citation: SensePost Ruler GitHub) [SensePost Ruler GitHub](https://github.com/sensepost/ruler)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent Office applications from creating child processes and from writing potentially malicious executable content to disk. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — For the Outlook methods, blocking macros may be ineffective as the Visual Basic engine used for these features is separate from the macro scripting engine.(Citation: SensePost Outlook Forms) Microsoft has released patches to try to address each issue. Ensure KB3191938 which blocks Outlook Visual Basic and displays a malicious code warning, KB4011091 which disables custom forms by default, and KB4011162 which removes the legacy Home Page feature, are applied to systems.(Citation: SensePost Outlook Home Page) [SensePost Outlook Forms](https://sensepost.com/blog/2017/outlook-forms-and-shells/) · [SensePost Outlook Home Page](https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/)

## Detection strategies

- [DET0029 - Detect Persistence via Outlook Custom Forms Triggered by Malicious Email](../../../../Defenses/Detection%20Strategies/DET0029%20-%20Detect%20Persistence%20via%20Outlook%20Custom%20Forms%20Triggered%20by%20Malicious%20Email.md)

## Sources

- [Microsoft Detect Outlook Forms](https://docs.microsoft.com/en-us/office365/securitycompliance/detect-and-remediate-outlook-rules-forms-attack)
- [SensePost NotRuler](https://github.com/sensepost/notruler)
- [SensePost Outlook Forms](https://sensepost.com/blog/2017/outlook-forms-and-shells/)
