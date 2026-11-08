# T1137 - Office Application Startup

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may leverage Microsoft Office-based applications for persistence between startups. Microsoft Office is a fairly common application suite on Windows-based operating systems within an enterprise network. There are multiple mechanisms that can be used with Office for persistence when an Office-based application is started; this can include the use of Office Template Macros and add-ins.

A variety of features have been discovered in Outlook that can be abused to obtain persistence, such as Outlook rules, forms, and Home Page.(Citation: SensePost Ruler GitHub) These persistence mechanisms can work within Outlook or be used through Office 365.(Citation: TechNet O365 Outlook Rules)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1137)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Office Suite](../../../Platforms/Office%20Suite.md)

## Sub-techniques

- [T1137.006 - Add-ins](T1137.006%20-%20Add-ins/README.md)
- [T1137.001 - Office Template Macros](T1137.001%20-%20Office%20Template%20Macros/README.md)
- [T1137.002 - Office Test](T1137.002%20-%20Office%20Test/README.md)
- [T1137.003 - Outlook Forms](T1137.003%20-%20Outlook%20Forms/README.md)
- [T1137.004 - Outlook Home Page](T1137.004%20-%20Outlook%20Home%20Page/README.md)
- [T1137.005 - Outlook Rules](T1137.005%20-%20Outlook%20Rules/README.md)

## Detection strategies

- [DET0398 - Detect Office Startup-Based Persistence via Macros, Forms, and Registry Hooks](../../../Defenses/Detection%20Strategies/DET0398%20-%20Detect%20Office%20Startup-Based%20Persistence%20via%20Macros%2C%20Forms%2C%20and%20Registry%20Hooks.md)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, enable Attack Surface Reduction (ASR) rules to prevent Office applications from creating child processes and from writing potentially malicious executable content to disk. (Citation: win10_asr) [win10_asr](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)
- [M1042 - Disable or Remove Feature or Program](../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Follow Office macro security best practices suitable for your environment. Disable Office VBA macros from executing. Disable Office add-ins. If they are required, follow best practices for securing them by requiring them to be signed and disabling user notification for allowing add-ins. For some add-ins types (WLL, VBA) additional mitigation is likely required as disabling add-ins in the Office Trust Center does not disable WLL nor does it prevent VBA code from executing. (Citation: MRWLabs Office Persistence Add-ins) [MRWLabs Office Persistence Add-ins](https://web.archive.org/web/20190526112859/https://labs.mwrinfosecurity.com/blog/add-in-opportunities-for-office-persistence/)
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — For the Office Test method, create the Registry key used to execute it and set the permissions to "Read Control" to prevent easy access to the key without administrator permissions or requiring Privilege Escalation. (Citation: Palo Alto Office Test Sofacy) [Palo Alto Office Test Sofacy](https://researchcenter.paloaltonetworks.com/2016/07/unit42-technical-walkthrough-office-test-persistence-method-used-in-recent-sofacy-attacks/)
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — For the Outlook methods, blocking macros may be ineffective as the Visual Basic engine used for these features is separate from the macro scripting engine.(Citation: SensePost Outlook Forms) Microsoft has released patches to try to address each issue. Ensure KB3191938 which blocks Outlook Visual Basic and displays a malicious code warning, KB4011091 which disables custom forms by default, and KB4011162 which removes the legacy Home Page feature, are applied to systems.(Citation: SensePost Outlook Home Page) [SensePost Outlook Forms](https://sensepost.com/blog/2017/outlook-forms-and-shells/) · [SensePost Outlook Home Page](https://sensepost.com/blog/2017/outlook-home-page-another-ruler-vector/)

## Procedure examples

- [G0050 - APT32](../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) have replaced Microsoft Outlook's VbaProject.OTM file to install a backdoor macro for persistence.(Citation: Cybereason Oceanlotus May 2017)(Citation: Cybereason Cobalt Kitty 2017) [Cybereason Oceanlotus May 2017](https://www.cybereason.com/blog/operation-cobalt-kitty-apt) · [Cybereason Cobalt Kitty 2017](https://cdn2.hubspot.net/hubfs/3354902/Cybereason%20Labs%20Analysis%20Operation%20Cobalt%20Kitty.pdf)
- [G0047 - Gamaredon Group](../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has inserted malicious macros into existing documents, providing persistence when they are reopened. [Gamaredon Group](https://attack.mitre.org/groups/G0047) has loaded the group's previously delivered VBA project by relaunching Microsoft Outlook with the <code>/altvba</code> option, once the Application.Startup event is received.(Citation: ESET Gamaredon June 2020) [ESET Gamaredon June 2020](https://www.welivesecurity.com/2020/06/11/gamaredon-group-grows-its-game/)

## Sources

- [Microsoft Detect Outlook Forms](https://docs.microsoft.com/en-us/office365/securitycompliance/detect-and-remediate-outlook-rules-forms-attack)
- [TechNet O365 Outlook Rules](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)
- [CrowdStrike Outlook Forms](https://malware.news/t/using-outlook-forms-for-lateral-movement-and-persistence/13746)
- [SensePost Ruler GitHub](https://github.com/sensepost/ruler)
- [SensePost NotRuler](https://github.com/sensepost/notruler)
- [Outlook Today Home Page](https://medium.com/@bwtech789/outlook-today-homepage-persistence-33ea9b505943)
