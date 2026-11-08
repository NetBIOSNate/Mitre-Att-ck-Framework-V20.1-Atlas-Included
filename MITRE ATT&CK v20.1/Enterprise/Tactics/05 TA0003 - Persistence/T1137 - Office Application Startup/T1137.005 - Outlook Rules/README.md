# T1137.005 - Outlook Rules

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1137 - Office Application Startup](../README.md)

Adversaries may abuse Microsoft Outlook rules to obtain persistence on a compromised system. Outlook rules allow a user to define automated behavior to manage email messages. A benign rule might, for example, automatically move an email to a particular folder in Outlook if it contains specific words from a specific sender. Malicious Outlook rules can be created that can trigger code execution when an adversary sends a specifically crafted email to that user.(Citation: SilentBreak Outlook Rules)

Once malicious rules have been added to the user’s mailbox, they will be loaded when Outlook is started. Malicious rules will execute when an adversary sends a specifically crafted email to the user.(Citation: SilentBreak Outlook Rules)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1137/005)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Office Suite](../../../../Platforms/Office%20Suite.md)

## Procedure examples

- [S0358 - Ruler](../../../../Threat%20Intelligence/Software/Tools/S0358%20-%20Ruler.md) — [Ruler](https://attack.mitre.org/software/S0358) can be used to automate the abuse of Outlook Rules to establish persistence.(Citation: SensePost Ruler GitHub) [SensePost Ruler GitHub](https://github.com/sensepost/ruler)

## Detection strategies

- [DET0095 - Detect Persistence via Malicious Outlook Rules](../../../../Defenses/Detection%20Strategies/DET0095%20-%20Detect%20Persistence%20via%20Malicious%20Outlook%20Rules.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent Office applications from creating child processes and from writing potentially malicious executable content to disk. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — For the Outlook methods, blocking macros may be ineffective as the Visual Basic engine used for these features is separate from the macro scripting engine.(Citation: SensePost Outlook Forms) Microsoft has released patches to try to address each issue. Ensure KB3191938 which blocks Outlook Visual Basic and displays a malicious code warning, KB4011091 which disables custom forms by default, and KB4011162 which removes the legacy Home Page feature, are applied to systems.(Citation: SensePost Outlook Home Page) [SensePost Outlook Forms](https://sensepost.com/blog/2017/outlook-forms-and-shells/) · [SensePost Outlook Home Page](https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/)

## Sources

- [Pfammatter - Hidden Inbox Rules](https://blog.compass-security.com/2018/09/hidden-inbox-rules-in-microsoft-exchange/)
- [Microsoft Detect Outlook Forms](https://docs.microsoft.com/en-us/office365/securitycompliance/detect-and-remediate-outlook-rules-forms-attack)
- [SilentBreak Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/)
- [SensePost NotRuler](https://github.com/sensepost/notruler)
