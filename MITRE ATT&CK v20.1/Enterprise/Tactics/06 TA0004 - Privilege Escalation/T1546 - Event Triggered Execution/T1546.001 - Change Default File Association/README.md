# T1546.001 - Change Default File Association

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence by executing malicious content triggered by a file type association. When a file is opened, the default program used to open the file (also called the file association or handler) is checked. File association selections are stored in the Windows Registry and can be edited by users, administrators, or programs that have Registry access or by administrators using the built-in assoc utility.(Citation: Microsoft Change Default Programs)(Citation: Microsoft File Handlers)(Citation: Microsoft Assoc Oct 2017) Applications can modify the file association for a given file extension to call an arbitrary program when a file with the given extension is opened.

System file associations are listed under <code>HKEY_CLASSES_ROOT\.[extension]</code>, for example <code>HKEY_CLASSES_ROOT\.txt</code>. The entries point to a handler for that extension located at <code>HKEY_CLASSES_ROOT\\[handler]</code>. The various commands are then listed as subkeys underneath the shell key at <code>HKEY_CLASSES_ROOT\\[handler]\shell\\[action]\command</code>. For example: 

* <code>HKEY_CLASSES_ROOT\txtfile\shell\open\command</code>
* <code>HKEY_CLASSES_ROOT\txtfile\shell\print\command</code>
* <code>HKEY_CLASSES_ROOT\txtfile\shell\printto\command</code>

The values of the keys listed are commands that are executed when the handler opens the file extension. Adversaries can modify these values to continually execute arbitrary commands.(Citation: TrendMicro TROJ-FAKEAV OCT 2012)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/001)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has a HWP document stealer module which changes the default program association in the registry to open HWP documents.(Citation: Securelist Kimsuky Sept 2013) [Securelist Kimsuky Sept 2013](https://securelist.com/the-kimsuky-operation-a-north-korean-apt/57915/)
- [S0692 - SILENTTRINITY](../../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) can conduct an image hijack of an `.msc` file extension as part of its UAC bypass process.(Citation: GitHub SILENTTRINITY Modules July 2019) [GitHub SILENTTRINITY Modules July 2019](https://github.com/byt3bl33d3r/SILENTTRINITY/tree/master/silenttrinity/core/teamserver/modules/boo)

## Detection strategies

- [DET0061 - Detect Default File Association Hijack via Registry & Execution Correlation on Windows](../../../../Defenses/Detection%20Strategies/DET0061%20-%20Detect%20Default%20File%20Association%20Hijack%20via%20Registry%20%26%20Execution%20Correlation%20on%20Window.md)

## Sources

- [Microsoft Change Default Programs](https://support.microsoft.com/en-us/help/18539/windows-7-change-default-programs)
- [Microsoft File Handlers](https://learn.microsoft.com/en-us/previous-versions/visualstudio/visual-studio-2015/extensibility/specifying-file-handlers-for-file-name-extensions?view=vs-2015)
- [Microsoft Assoc Oct 2017](https://docs.microsoft.com/windows-server/administration/windows-commands/assoc)
- [TrendMicro TROJ-FAKEAV OCT 2012](https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/troj_fakeav.gzd)
